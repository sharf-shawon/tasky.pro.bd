## ADDED Requirements

### Requirement: Google Analytics Integration
The system SHALL include the Google Analytics (GA4) script tag in all public HTML files.

#### Scenario: Page view tracking
- **WHEN** a user loads `index.html` or `faq.html`
- **THEN** the system SHALL send a page_view event to Google Analytics
