# Nevo24 Website Requirements Analysis
*(Based on provided German requirements document)*

## 1. System Overview
**Goal**: Develop a comprehensive web application for managing Energy and Insurance contracts, featuring high automation and AI integration.
**Platform**: Web Application (with potential PWA/App features like camera scanning).

## 2. Technical System Structure
*   **Core Verticals**:
    1.  **Energy** (Strom/Gas).
    2.  **Insurance** (Versicherungen).
    3.  **Contract Overview** (Unified dashboard).
*   **Language Support**:
    *   **AI Translation**: Automatic language detection and translation capabilities.
    *   **Supported Languages**: German (DE), English (EN), Turkish (TR), Italian (IT), Arabic (AR).

## 3. User Groups & Roles
### A. Commercial Users (Gewerblich)
*   **Roles**:
    *   **Self**: Broker/Owner managing own portfolio.
    *   **Employees**: Staff managing assigned clients.
    *   **Sales Partners**: Hierarchical access for partners.
    *   **External Freelancers**: Paid subscription tiers (Standard, Premium, Platinum).
*   **Key Needs**:
    *   Client management dashboard.
    *   Document control (reviewing client uploads before "approving").
    *   Communication tools with clients.

### B. Private Users (Privat)
*   **Roles**:
    *   **New Customers**: Onboarding flow.
    *   **Existing Customers**: Contract management.
    *   **External/Guest Users**: Limited access.
*   **Key Needs**:
    *   Simple dashboard for contracts.
    *   Easy document upload/scanning.
    *   Notifications for tasks (meter readings, etc.).

## 4. Functional Requirements (Website Scope)

### A. Document Management
*   **Upload Methods**:
    *   **Drag & Drop**: For desktop users.
    *   **Camera Scan**: Mobile-optimized scanning interface.
        *   *Features*: Multi-page scanning, page rotation, review/retake before submission.
        *   *No Photos*: Must convert to document format (PDF/scanned quality), not raw photos.
*   **Processing**:
    *   **Compression**: Auto-resize/compress files for storage efficiency.
    *   **AI Classification**: Automatically assign recognized documents to specific contracts.
    *   **Fallback**: If unrecognized, assign to generic "Client Folder" and notify commercial user for manual sorting.

### B. Communication & Messaging
*   **Chat Interface**:
    *   Direct channel between Commercial and Private users.
    *   **AI Analysis**: Analyzing attachments sent via chat to auto-file them to contracts.
    *   **Archiving**: Commercial users can "Save" chat threads (start/end marker) => Generates PDF protocol attached to contract.
*   **Visibility Control**:
    *   Documents added by commercial users are **hidden by default** from private users until approved/released.

### C. Automation & Intelligence
*   **Smart Email Integration (@nevo24)**:
    *   Every user/contract gets a unique email alias (e.g., contract123@nevo24.de).
    *   Emails sent to this alias are auto-processed by the system.
*   **To-Do Generation**:
    *   Incoming documents/emails trigger "To-Do" items for commercial users.
    *   AI detects keywords (Invoice, Meter Reading, Price Adjustment) to categorize tasks.
*   **Event-Driven Workflows**:
    *   **Meter Reading (Zählerstand)**:
        *   Notification window (e.g., 7 days before due date).
        *   If overdue: Force-popup on app launch until submitted.
        *   Auto-email to provider upon submission.
    *   **Relocation (Umzug)**:
        *   User submits move date & new address.
        *   System auto-notifies all providers.
        *   Reminder for final meter reading before move-out.

### D. Legal & Consent (AGB)
*   **Digital Signatures**:
    *   Data Protection (Datenschutz).
    *   Confidentiality Release (Schweigepflichtentbindung).
    *   Power of Attorney (Vollmacht).
*   **Logic**:
    *   Users *can* use the app without full Power of Attorney, but automation features (cancellation, changes) will be disabled.
    *   System must track signature status and prompt for missing signatures when user attempts restricted actions.

## 6. Website Architecture & Pages
This section maps the requirements to specific pages and components to be built.

### A. Public Website (Marketing)
*   **Home (`index.html`)**:
    *   Overview of services (Energy, Insurance).
    *   Value Proposition (Savings, Personal Support).
    *   Login/Register Buttons prominent.
*   **Services (`services.html`)**:
    *   Detailed explanation of Energy & Insurance products.
    *   Comparison tools teaser.
*   **Knowledge (`knowledge.html`)**:
    *   FAQs and articles.
*   **Contact (`contact.html`)**:
    *   General inquiries form.

### B. User Portal (Authentication)
*   **Login Page (`/login`)**:
    *   Unified login for Private & Commercial users (routed based on role).
*   **Registration Page (`/register`)**:
    *   Start as Private user. Commercial users likely invite-only or separate application flow.
*   **Password Reset (`/forgot-password`)**: Standard flow.

### C. Private User Dashboard (The "App")
*   **Dashboard Home (`/dashboard`)**:
    *   Summary of active contracts (Energy count, Insurance names).
    *   **Alerts Area**: "Submit Meter Reading", "Sign Document".
    *   **Quick Actions**: "Upload Document", "Report Move".
*   **Contract List (`/dashboard/contracts`)**:
    *   Filter by Energy / Insurance.
    *   Status badges (Active, Cancelled).
*   **Contract Details (`/dashboard/contract/[id]`)**:
    *   Metadata (Provider, Cost, End Date).
    *   **Document List**: Bills, Policies (only approved docs visible).
    *   **Upload Area**: Specific to this contract.
*   **Profile & Settings (`/dashboard/profile`)**:
    *   Personal Data (Name, Address).
    *   **Legal Data**: Signature status (Power of Attorney active?).
    *   Bank details.

### D. Commercial User Dashboard (CRM)
*   **CRM Home (`/crm`)**:
    *   **Inbox/To-Do List**: Generated from emails/uploads (e.g., "New unassigned document from Client X").
    *   Recent Client Activity feed.
*   **Client Management (`/crm/clients`)**:
    *   Search/Filter clients.
    *   Add new client.
*   **Client View (`/crm/client/[id]`)**:
    *   See client's view + hidden internal notes.
    *   **Document Approval Queue**: Approve docs uploaded by client.
    *   **Chat History**: View/Archive chats.

### E. Shared Components / Modals
*   **Document Scanner Modal**:
    *   Interface for Camera access (Mobile) or File Picker (Desktop).
    *   Image processing (Crop/Rotate) before upload.
*   **Chat Widget**:
    *   Floating widget for direct communication (Client <-> Agent).
*   **Notification Center**:
    *   Bell icon with dropdown updates.

## 7. Next Steps for Development (Immediate)
1.  **Refine Public Pages**: Ensure the existing `index.html`, `services.html` match the brand tone (Trust/Savings).
2.  **Build Auth Pages**: Create Login/Register mockups.
3.  **Prototype Private Dashboard**: Focus on the Contract List and Upload flow first.
4.  **Implement Logic**: Start with the "Meter Reading" workflow mockup.
