# Plan: Copy to Clipboard for ag-Grid with CSV Injection Protection

## Context

This implementation is for the Insights Copilot React frontend, specifically for the Tables & Charts feature (WIP) mentioned in the product documentation. The feature allows users to copy table data to clipboard in CSV format for pasting into Excel or other spreadsheet applications.

**Requirements:**
- Copy all visible table data (not just selected rows)
- No data formatting (use raw values)
- Sanitize cells to prevent CSV injection attacks
- Community edition only (no enterprise features)

**Tech Stack:**
- React web app
- ag-grid-community (not ag-grid-enterprise)
- Browser Clipboard API with fallback

## Implementation Steps

### Step 1: Create CSV Injection Sanitization Function

Create a utility function to prevent CSV injection attacks by prepending a single quote to dangerous values.

```javascript
/**
 * Sanitizes cell values to prevent CSV injection attacks in Excel and other spreadsheet applications.
 * According to OWASP, cells starting with =, +, -, @, Tab, or Carriage Return can be executed as formulas.
 * 
 * @param {any} value - The cell value to sanitize
 * @returns {string} - Sanitized value safe for CSV export
 */
const sanitizeForCsv = (value) => {
  if (value == null || value === '') {
    return value;
  }
  
  const stringValue = String(value);
  const dangerousChars = ['=', '+', '-', '@', '\t', '\r'];
  
  // Check if the first character is dangerous
  if (dangerousChars.includes(stringValue.charAt(0))) {
    // Prepend single quote to prevent formula execution
    return `'${stringValue}`;
  }
  
  return stringValue;
};
```

**Reference:** [OWASP CSV Injection](https://owasp.org/www-community/attacks/CSV_Injection)

### Step 2: Implement Copy to Clipboard Handler

Create the main handler function that uses ag-grid's CSV export API.

```javascript
/**
 * Copies all visible grid data to clipboard as CSV format.
 * Handles both modern Clipboard API and legacy execCommand fallback.
 * 
 * @param {object} gridApi - The ag-grid API instance
 * @param {function} setFeedback - Optional callback for UI feedback (e.g., show "Copied!" message)
 * @returns {Promise<boolean>} - Success status
 */
const copyTableToClipboard = async (gridApi, setFeedback) => {
  if (!gridApi) {
    console.error('Grid API not available');
    return false;
  }

  try {
    // Configure CSV export parameters
    const csvExportParams = {
      // Export all filtered/sorted rows (not just selected)
      exportedRows: 'filteredAndSorted',
      
      // Only export visible columns
      allColumns: false,
      
      // Include column headers
      skipColumnHeaders: false,
      
      // Don't skip grouped headers
      skipColumnGroupHeaders: false,
      
      // Keep proper CSV quote escaping
      suppressQuotes: false,
      
      // Use comma as separator (Excel default)
      columnSeparator: ',',
      
      // Apply sanitization to each cell
      processCellCallback: (params) => {
        return sanitizeForCsv(params.value);
      }
    };

    // Get CSV data as string
    const csvData = gridApi.getDataAsCsv(csvExportParams);
    
    if (!csvData) {
      throw new Error('No data to copy');
    }

    // Try modern Clipboard API first
    if (navigator.clipboard && navigator.clipboard.writeText) {
      await navigator.clipboard.writeText(csvData);
    } else {
      // Fallback for older browsers
      copyToClipboardFallback(csvData);
    }

    // Show success feedback
    if (setFeedback) {
      setFeedback('Copied!');
      setTimeout(() => setFeedback(''), 2000);
    }

    return true;

  } catch (error) {
    console.error('Failed to copy table data:', error);
    
    // Show error feedback
    if (setFeedback) {
      setFeedback('Copy failed');
      setTimeout(() => setFeedback(''), 2000);
    }
    
    return false;
  }
};

/**
 * Fallback method for copying to clipboard in older browsers.
 * Uses deprecated execCommand API.
 * 
 * @param {string} text - Text to copy
 */
const copyToClipboardFallback = (text) => {
  const textArea = document.createElement('textarea');
  textArea.value = text;
  textArea.style.position = 'fixed';
  textArea.style.left = '-999999px';
  textArea.style.top = '-999999px';
  document.body.appendChild(textArea);
  textArea.focus();
  textArea.select();
  
  try {
    document.execCommand('copy');
  } finally {
    document.body.removeChild(textArea);
  }
};
```

### Step 3: Add Copy Button to UI

Add a button component near your ag-grid table. Example for a toolbar button:

```javascript
import React, { useState } from 'react';

const TableWithCopyButton = () => {
  const [gridApi, setGridApi] = useState(null);
  const [copyFeedback, setCopyFeedback] = useState('');

  const onGridReady = (params) => {
    setGridApi(params.api);
  };

  const handleCopyClick = () => {
    copyTableToClipboard(gridApi, setCopyFeedback);
  };

  return (
    <div>
      <div className="table-toolbar">
        <button 
          onClick={handleCopyClick}
          disabled={!gridApi}
          className="copy-button"
        >
          {copyFeedback || 'Copy Table'}
        </button>
      </div>
      
      <div className="ag-theme-alpine" style={{ height: 600, width: '100%' }}>
        <AgGridReact
          onGridReady={onGridReady}
          // ... other grid props
        />
      </div>
    </div>
  );
};
```

### Step 4: Add User Feedback (Optional Enhancement)

Consider using your existing toast notification system or a simple button state change:

```javascript
// Option 1: Button text change (shown in Step 3)

// Option 2: Toast notification (if you have a toast system)
const handleCopyClick = async () => {
  const success = await copyTableToClipboard(gridApi);
  if (success) {
    showToast('Table copied to clipboard', 'success');
  } else {
    showToast('Failed to copy table', 'error');
  }
};

// Option 3: Icon change
const [copied, setCopied] = useState(false);

const handleCopyClick = async () => {
  const success = await copyTableToClipboard(gridApi);
  if (success) {
    setCopied(true);
    setTimeout(() => setCopied(false), 2000);
  }
};

// In render:
<button onClick={handleCopyClick}>
  {copied ? <CheckIcon /> : <CopyIcon />}
  {copied ? 'Copied!' : 'Copy Table'}
</button>
```

## ag-Grid API Reference

### Key API Methods Used

**`gridApi.getDataAsCsv(params)`**
- Returns CSV export as a string (does not trigger download)
- Available in community edition
- [Documentation](https://www.ag-grid.com/javascript-data-grid/csv-export/)

### CsvExportParams Interface

```typescript
interface CsvExportParams {
  exportedRows?: 'all' | 'filteredAndSorted';  // Which rows to export
  allColumns?: boolean;                          // Include hidden columns?
  skipColumnHeaders?: boolean;                   // Exclude headers?
  skipColumnGroupHeaders?: boolean;              // Exclude grouped headers?
  suppressQuotes?: boolean;                      // Don't escape quotes?
  columnSeparator?: string;                      // Default: ','
  processCellCallback?: (params) => any;         // Transform cell values
  processHeaderCallback?: (params) => string;    // Transform headers
}
```

## Testing Checklist

- [ ] Test copying with empty grid
- [ ] Test copying with filtered data
- [ ] Test copying with sorted data
- [ ] Test cells with dangerous characters (`=`, `+`, `-`, `@`)
- [ ] Test cells with commas and quotes (CSV escaping)
- [ ] Test cells with newlines
- [ ] Test paste into Excel (verify no formula execution)
- [ ] Test paste into Google Sheets
- [ ] Test in Chrome, Firefox, Safari, Edge
- [ ] Test fallback on older browsers (IE11 if supported)
- [ ] Test with large datasets (performance)
- [ ] Test UI feedback displays correctly
- [ ] Test button disabled state when grid not ready

## Security Notes

**CSV Injection Prevention:**
- Cells starting with `=`, `+`, `-`, `@` are prepended with `'` 
- This prevents spreadsheet applications from executing them as formulas
- Tab (`\t`) and Carriage Return (`\r`) characters are also sanitized
- OWASP recommends this approach for CSV exports

**Browser Permissions:**
- Modern browsers may prompt user for clipboard permission on first use
- No sensitive data is logged or transmitted
- All processing happens client-side

## Integration with Insights Copilot

### Recommended Button Placement

Based on the product documentation, add the copy button in the **Response Actions** section alongside existing actions:

```
Response Actions:
├── Feedback (thumbs up/down)
├── Share (secure links)
├── Copy (existing - for text responses)
├── Copy Table (NEW - for tabular data) ← Add here
└── View Sources
```

### Styling Consistency

Match the existing button styles in your Response Actions component:
- Use the same button component/class
- Use consistent iconography (e.g., clipboard icon)
- Follow existing color scheme and hover states
- Maintain accessibility standards (aria-labels, keyboard navigation)

## Optional Enhancements

### 1. Include Hidden Columns Toggle

```javascript
const [includeHidden, setIncludeHidden] = useState(false);

const csvExportParams = {
  allColumns: includeHidden,  // Toggle hidden columns
  // ... other params
};

// UI:
<label>
  <input 
    type="checkbox" 
    checked={includeHidden}
    onChange={(e) => setIncludeHidden(e.target.checked)}
  />
  Include hidden columns
</label>
```

### 2. Custom Header Formatting

```javascript
const csvExportParams = {
  processHeaderCallback: (params) => {
    // Convert COLUMN_NAME to "Column Name"
    return params.column.getColDef().headerName || 
           params.column.getColId()
             .replace(/_/g, ' ')
             .replace(/\b\w/g, c => c.toUpperCase());
  },
  // ... other params
};
```

### 3. Export Selected Rows Only

```javascript
const copySelectedToClipboard = async (gridApi, setFeedback) => {
  const selectedRows = gridApi.getSelectedRows();
  
  if (selectedRows.length === 0) {
    setFeedback('No rows selected');
    return false;
  }

  const csvExportParams = {
    onlySelected: true,  // Only export selected rows
    // ... other params
  };
  
  // ... rest of implementation
};
```

## Dependencies

```json
{
  "dependencies": {
    "ag-grid-community": "^31.0.0",
    "ag-grid-react": "^31.0.0",
    "react": "^18.0.0"
  }
}
```

Note: No additional dependencies needed - uses native browser APIs.

## File Structure

```
src/
├── components/
│   ├── Table/
│   │   ├── TableGrid.jsx              (ag-grid component)
│   │   ├── TableToolbar.jsx           (toolbar with copy button)
│   │   └── ResponseActions.jsx        (existing response actions)
├── utils/
│   ├── csvUtils.js                    (sanitizeForCsv function)
│   └── clipboardUtils.js              (copy functions)
└── hooks/
    └── useTableCopy.js                (optional: custom hook)
```

## Questions for Product/Design Team

1. **Button placement?** Should the copy button be in the table toolbar, as a floating action button, or in the Response Actions section (alongside existing Copy, Share, View Sources buttons)?

2. **Include hidden columns?** Currently set to `allColumns: false` - do you want the option to include hidden columns by setting this to `true`?

3. **Header formatting?** The plan uses default headers - do you need `processHeaderCallback` to customize column header names when copied?

4. **Icon design?** What icon should be used for the copy button? (clipboard, download, copy icon?)

5. **Feedback mechanism?** Should we use toast notifications, button text change, or icon change to indicate success?

6. **Analytics tracking?** Should this action be tracked (e.g., "table_copied" event)?
