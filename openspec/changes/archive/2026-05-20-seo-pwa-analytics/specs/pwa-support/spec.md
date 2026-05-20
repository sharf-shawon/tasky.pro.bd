## ADDED Requirements

### Requirement: Web App Manifest
The system SHALL provide a `manifest.json` file defining app name, icons, and start URL.

#### Scenario: App is installable
- **WHEN** a user visits the site on a mobile device
- **THEN** the browser SHALL prompt the user to "Add to Home Screen" based on the manifest content

### Requirement: Service Worker
The system SHALL register a service worker to enable basic offline capability (caching the main UI).

#### Scenario: Offline loading
- **WHEN** a user opens the installed app without an internet connection
- **THEN** the system SHALL load the cached `index.html` and UI components
