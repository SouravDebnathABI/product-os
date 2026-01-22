# Insights Copilot User Login Flow

```mermaid
flowchart TD
    Start([User Opens Insights Copilot Link]) --> EntryPoint{Entry Method}
    
    EntryPoint -->|Email/Teams Link| LoginPage[User Arrives at Login Page]
    EntryPoint -->|Admin Direct Registration| LoginPage
    
    LoginPage --> ClickLogin[User Clicks 'Login' Button]
    ClickLogin --> SSO[Microsoft SSO Authentication]
    
    SSO --> SSOSuccess{SSO Successful?}
    SSOSuccess -->|No| SSOError[Show Authentication Error]
    SSOError --> LoginPage
    
    SSOSuccess -->|Yes| CheckAccess{User Has Access<br/>to Any Usecase?}
    
    CheckAccess -->|No Access| RegPage[Land on Registration Page]
    RegPage --> RaiseRequest[User Raises Access Request<br/>for Relevant Usecase]
    RaiseRequest --> AwaitApproval[Await Admin Approval]
    AwaitApproval --> NotifyUser[User Notified via Email]
    NotifyUser --> ReturnLater([User Returns Later])
    ReturnLater --> LoginPage
    
    CheckAccess -->|Has Access| DetermineLanding{First Time<br/>or Returning User?}
    
    DetermineLanding -->|First Time User| LastRegistered[Land on Last Registered<br/>Usecase Page]
    DetermineLanding -->|Returning User| LastAccessed[Land on Last Accessed<br/>Usecase Page]
    
    LastRegistered --> LandingPage[Usecase Landing Page]
    LastAccessed --> LandingPage
    
    LandingPage --> UseApp[User Uses Insights Copilot]
    UseApp --> ActiveSession{Session Active?}
    
    ActiveSession -->|Active - Within 48hrs| UseApp
    ActiveSession -->|Token Expired - ~48hrs| SessionExpired[Access Token Expired]
    
    SessionExpired --> ForceRelogin[Force Re-authentication]
    ForceRelogin --> LoginPage
    
    UseApp --> UserLogout{User Manually<br/>Logs Out? }
    UserLogout -->|Yes| Logout[Logout Successful]
    Logout --> End([End Session])
    UserLogout -->|No| UseApp
    
    style Start fill:#e1f5e1
    style End fill:#ffe1e1
    style SSOError fill:#ffcccc
    style RegPage fill:#fff4cc
    style SessionExpired fill:#ffcccc
    style LandingPage fill:#ccf0ff
    style UseApp fill:#ccf0ff
```

## Flow Description

### Happy Path Flow
1. **Entry**:  User opens Insights Copilot via email/Teams link or after admin registration
2. **Login**:  User clicks "Login" button on login page
3. **Authentication**: User completes Microsoft SSO authentication successfully
4. **Access Check**: System verifies user has access to at least one usecase
5. **Landing**: User lands on appropriate page (last accessed for returning users, last registered for first-time users)
6. **Usage**: User successfully uses Insights Copilot

### Unhappy Path - No Access
1. **Entry → Authentication**: Same as happy path (steps 1-3)
2. **No Access Detected**: System finds user has no usecase access
3. **Registration Page**: User redirected to registration page
4. **Request Access**: User raises access request for relevant usecase
5. **Awaiting Approval**: Request pending admin approval
6. **Return**:  User notified and returns later to login again

### Relogin Flow (Token Expiration)
1. **Active Session**: User actively using Insights Copilot
2. **Token Expiry**: After ~48 hours, access token expires
3. **Force Relogin**: System forces re-authentication
4. **Back to Login**: User redirected to login page
5. **Repeat Flow**: User goes through authentication flow again

### Edge Cases Covered
- **SSO Authentication Failure**: User returned to login page with error
- **Manual Logout**: User can manually end session
- **Unknown User**:  Directed to registration page (no access path)
- **Multiple Usecases**: System determines correct landing page based on user history