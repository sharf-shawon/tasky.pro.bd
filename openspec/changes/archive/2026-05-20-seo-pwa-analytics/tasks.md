## 1. SEO & Discovery Foundation

- [x] 1.1 Add meta tags (description, keywords, OpenGraph) to `src/index.html`
- [x] 1.2 Create `src/robots.txt` at the repository root
- [x] 1.3 Create `src/sitemap.xml` at the repository root

## 2. FAQ Page Implementation

- [x] 2.1 Create `src/faq.html` with a modern dark theme consistent with the main app
- [x] 2.2 Add content to `src/faq.html` covering features, security (AES-GCM), and privacy (local-first)
- [x] 2.3 Add navigation links between `src/index.html` and `src/faq.html`

## 3. PWA Support

- [x] 3.1 Create `src/manifest.json` with app icons, theme color, and display mode
- [x] 3.2 Create a basic `src/sw.js` for "Cache First" storage of core assets
- [x] 3.3 Register the service worker in `src/index.html` and `src/faq.html`

## 4. Google Analytics Integration

- [x] 4.1 Add Google Analytics (GA4) Global Site Tag to the `<head>` of `src/index.html`
- [x] 4.2 Add Google Analytics (GA4) Global Site Tag to the `<head>` of `src/faq.html`

## 5. Deployment & Self-Hosting

- [x] 5.1 Add GitHub Actions workflow (`.github/workflows/deploy.yml`) to build and publish to GitHub Pages
- [x] 5.2 Create a `Dockerfile` using `nginx:alpine` for minimal-footprint self-hosting
- [x] 5.3 Create `docker-compose.yml` with basic labels for Coolify/Dockge/CasaOS compatibility
- [x] 5.4 Research and add Coolify app template files (e.g., `coolify.yaml` if applicable)

## 6. Verification & Polish

- [x] 6.1 Validate SEO meta tags using an online validator (or manual inspection)
- [x] 6.2 Test PWA installation on a mobile device or simulator
- [x] 6.3 Verify Google Analytics events are firing (using Real-Time view)
- [x] 6.4 Perform a final responsive UI check for the new FAQ page
