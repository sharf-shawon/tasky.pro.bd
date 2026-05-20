## Why

Tasky is currently a single-file application with minimal web presence and poor discoverability. To make it a more robust and professional product, we need to improve its SEO, provide a proper FAQ for user trust and understanding, and enable a native-like experience on mobile devices via PWA. Additionally, adding Google Analytics will help track usage patterns (anonymously) to guide future development.

## What Changes

- **New FAQ Page**: Create `src/faq.html` as a dedicated page for SEO indexing and user education.
- **SEO Optimization**: Update `src/index.html` and `src/faq.html` with meta tags, OpenGraph data, and structured data.
- **PWA Support**: Add `src/manifest.json` and a service worker to enable app installation.
- **Robots & Sitemap**: Add `robots.txt` and `sitemap.xml` to guide search engine crawlers.
- **Google Analytics Integration**: Inject the Google Analytics tag into both HTML files.

## Capabilities

### New Capabilities
- `seo-and-discovery`: Meta tags, robots.txt, sitemap, and SEO optimization.
- `pwa-support`: App manifest and basic service worker for home screen installation.
- `google-analytics`: Tracking integration for usage metrics.
- `faq-content`: Documentation of features, security, and privacy (local-first explanation).

### Modified Capabilities
- `task-management`: The FAQ will detail how this core capability works under the hood.

## Impact

- **New Files**: `src/faq.html`, `src/manifest.json`, `src/sw.js`, `robots.txt`, `sitemap.xml`.
- **Modified Files**: `src/index.html` (meta tags, analytics script).
- **Dependencies**: No new external runtime dependencies (Google Analytics is a script injection).
