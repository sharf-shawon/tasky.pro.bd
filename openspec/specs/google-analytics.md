# Capability: Google Analytics

Usage tracking and analytics for the application.

## User Stories

- As a maintainer, I want to see how many people are using the site to understand its reach.
- As a maintainer, I want to know which pages (Home vs FAQ) are most visited.

## Functional Requirements

- **GA4 Integration**:
    - Include the Google Analytics (GA4) script tag in `index.html` and `faq.html`.
    - Configure the tracking ID appropriately.
- **Event Tracking**:
    - Automatically track page views for all public routes.

## Non-Functional Requirements

- **Privacy**: Ensure GA tracking respects basic privacy and doesn't capture any encrypted task data.
