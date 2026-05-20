## Context

Tasky is a standalone `index.html` file. We want to expand its presence to multiple files (`faq.html`, `manifest.json`, etc.) and add SEO/Analytics while keeping the core app logic localized in the main file.

## Goals / Non-Goals

**Goals:**
- Improve search engine rankings for Tasky.
- Provide a clear explanation of security and privacy to users.
- Enable app-like experience (PWA) on mobile devices.
- Track usage (anonymously) via Google Analytics.
- Add Docker support for easy self-hosting.

**Non-Goals:**
- Backend development (remain static/local-first).
- Complex offline sync (basic PWA caching only).
- Multi-language support (English only for now).

## Decisions

### 1. Dedicated FAQ Page
**Decision**: Create a separate `src/faq.html` instead of an overlay in `src/index.html`.
**Rationale**: Search engines index separate HTML files much better than dynamically rendered content within a single SPA. It also makes the content more shareable via direct links.
**Alternatives**: Modal overlay in main app (poor SEO).

### 2. Basic PWA Service Worker
**Decision**: Implement a "Cache First" strategy for core assets (`index.html`, `faq.html`, fonts).
**Rationale**: Tasky is a local-first app, so the UI should always be available even without a connection.
**Alternatives**: Network-first (requires internet for initial load, less "app-like").

### 3. Google Analytics Integration
**Decision**: Use standard script injection in both HTML files.
**Rationale**: Simple to implement and reliable for tracking basic page views and interactions in a static environment.
**Alternatives**: Custom self-hosted analytics (more complex to maintain).

### 4. Dockerization
**Decision**: Use `nginx:alpine` as the base image.
**Rationale**: Extremely lightweight (~5MB) and perfect for serving static HTML files.
**Alternatives**: Apache (heavier), Node.js server (unnecessary for static files).

## Risks / Trade-offs

- **[Risk]** → SEO meta tags might become outdated if features change.
- **[Mitigation]** → Keep meta descriptions focused on high-level value propositions (privacy, encryption).
- **[Risk]** → Service worker might cache an old version of the app.
- **[Mitigation]** → Implement a simple cache-busting strategy (e.g., versioned cache names).
- **[Risk]** → Google Analytics might be blocked by privacy-focused browsers.
- **[Mitigation]** → Accept as a known limitation; the app remains fully functional without analytics.
