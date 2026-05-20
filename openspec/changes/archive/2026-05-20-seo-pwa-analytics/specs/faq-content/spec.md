## ADDED Requirements

### Requirement: FAQ Page Content
The system SHALL provide a `src/faq.html` page that clearly explains features, security, and privacy.

#### Scenario: Security explanation
- **WHEN** a user visits `/faq.html`
- **THEN** they SHALL find a section explaining that data is encrypted locally and never leaves their machine

### Requirement: Navigation to FAQ
The system SHALL provide a link to the FAQ page from the main application UI.

#### Scenario: Accessing FAQ from home
- **WHEN** a user clicks the "FAQ" link in the footer or header of the main app
- **THEN** the system SHALL navigate to the FAQ page
