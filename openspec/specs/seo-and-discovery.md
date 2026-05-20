# Capability: SEO and Discovery

Search engine optimization and site discoverability.

## User Stories

- As a user, I want to find Tasky when searching for "encrypted task manager".
- As a user, I want the site to look good when I share the link on social media.

## Functional Requirements

- **SEO Meta Tags**:
    - Include `title`, `description`, and `keywords` in `index.html` and `faq.html`.
    - Include OpenGraph (`og:title`, `og:description`, `og:image`) and Twitter card meta tags.
- **Crawler Guidance**:
    - Provide a `robots.txt` file allowing all crawlers to index the site.
    - Provide a `sitemap.xml` file listing all public URLs.

## UI/UX

- Semantic HTML tags (h1, h2, etc.) to improve crawler understanding of page structure.
