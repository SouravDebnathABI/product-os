# Product Overview

## Product Description
**Insights Copilot** is AB InBev's proprietary AI-powered decision thought partner that helps managers and executives derive insights from their own business data using natural language questions and brainstorm iteratively or deep dive into concerns according to their existing workflow to take faster data-driven decisions.

## Target Customers
All AB InBev employees can access Insights Copilot through SSO login, but access to specific use cases depends on role and permissions.

**Primary User Personas:**
- **Managers** seeking data-driven insights for operational decisions
- **Executives** requiring strategic analysis and reporting
- **Business analysts** looking to accelerate their analytical workflows

**Secondary User Persona:**
- **Use Case Developers** customizing each use case to include business domain specific prompts and workflows to match user expectations

## Core Features

### Chat
The core of Insights Copilot is its chat-based interface, enabling users to ask business questions in natural language and receive instant, data-driven responses. Insights Copilot can interpret follow-ups based on prior exchanges, making iterative exploration easy and natural. Response formats include summaries, tables, and charts (where supported), and users can clarify or refine questions seamlessly.

### Response Actions
- **Feedback**: Instantly provide thumbs up/down and add comments for every response, feeding into product improvement and training
- **Share**: Share insights or chat segments with colleagues via secure links or export, supporting collaboration and knowledge transfer
- **Copy**: Copy results, tables, or summaries to clipboard for use in emails, presentations, or external reports
- **View Sources**: Inspect data sources or documentation supporting a given answer for trust and compliance
- **Tables & Charts (WIP)**: Insights Copilot is piloting advanced data visualization directly within chat, allowing users to render and interact with tables (sort, filter, paginated) and charts (zoom, pan, download) as part of their analytical workflow

### Smartflows
Smartflows are guided analytical workflows designed to produce precise, business-ready reports with structured workflows. Questions are presented to the user as a fill in the blanks format with dropdowns from datasets for each blank, making it easy for any user to arrive at business deep-dives, even without deep technical knowledge. Smartflows also enforce high reproducibility and support best-practice reporting formats.

### Chat History
Everything you discuss with Insights Copilot is automatically stored in your chat history, allowing you to revisit, review, and build upon previous conversations. Chats are organized by date and use case context. This enables quick retrieval of past insights, supports regulatory and audit requirements, and helps new users learn from prior successful queries.

### Know Your Data
The "Know Your Data" feature gives users transparency into the underlying datasets powering Insights Copilot's responses. At any time, you can inspect the source, freshness, and lineage of data used in your analysis. This builds trust in Insights Copilot outputs and supports data governance objectives by providing context, definitions, and direct access to data dictionaries or relevant business glossaries.

### Use Case Switch
With a single click, users can switch between different configured use cases (e.g., Marketing, Supply Chain, Procurement). The conversation context and analysis options automatically adjust to the selected domain. This flexibility helps users access relevant data, templates, and workflows without additional logins or navigation complexity, ensuring security and minimizing manual configuration errors.

### User Settings
The user settings panel allows for preferences and customization. Users can manage their display language (English, Spanish, Portuguese), notification preferences, and analytics/reporting defaults. Soon, it will also support response personalization and memory, helping users tailor Insights Copilot to their work style or business priorities.

## Tech Stack
- **Core LLM engine**: Langchain
- **Service layer**: Asynchronous REST-based services built on FastAPI framework
- **Response parser**: Python-based with Azure Functions
- **Frontend**: React web app for conversation interface
- **Databases**:
  - Databricks for storing use case data (direct/cleaned copy from BrewDat, AB InBev's internal data management system)
  - Postgres for storing app and user data
  - Redis for caching
  - Redis vector database for storing use case embeddings
- **Storage**: Azure blob storage for use case related documents
- **Infrastructure**: Publicly hosted with SSO login using Azure Cloud infrastructure

## Current Metrics
- **Activated users**: 5K (2025) → Target 10K+ (2026)
- **Monthly Active Users (MAU)**: Tracked and targeted for growth
- **NPS**: Currently tracked

## Pricing Model
Currently free for select AB InBev business users since it is internal, but soon it will be charged back to each business domain. No usage limits established yet.

## Competitive Landscape

**Direct Competitors:**
- Databricks Genie
- Max.AI by AnswerRocket
- Microsoft Copilot

**Indirect Competitors:**
- Power BI

**Internal Tools:**
- **Stellar**: For asking queries on IT documents and employee policies
- **GPTAP**: A ChatGPT wrapper routing employee queries to ChatGPT API with encryption

These internal tools address generic enterprise search needs for all employees on data public to enterprise (such as IT documents), however Insights Copilot caters to a targeted customer segment with secure business datasets.

**Differentiation:**
Insights Copilot's right to win comes from its readily available access to the company's internal data since it is built in-house and has all credentials and security to be bounded within the company network which other platforms do not have or need to be purchased and setup by a third party. Moreover, the product has complete flexibility to be built for its users and not bounded by the product architecture which is a common limitation with the competitors.
