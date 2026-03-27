# New Site Checklist

Tasks and configuration needed when onboarding a new ERS site.

## SEO Setup

### Sitemaps
- [ ] ERS auto-generates `sitemap.xml` with all pages including low-value ones (cart, items, system pages)
- [ ] Create a curated `landing-pages-sitemap.xml` Classic page with only the pages you want indexed
- [ ] Consider creating a `robots.txt` Classic page pointing only at your curated sitemap
- [ ] Submit your curated sitemap in Google Search Console
- [ ] Remove or don't submit the auto-generated `sitemap.xml` until the site is well-established

### Canonical Tags & Noindex
- [ ] Add self-referencing `<link rel="canonical">` to all pages via Script Insert always (head start area)
- [ ] Canonical should always use `https://www.` to consolidate www/non-www and http/https variants
- [ ] Check for ERS page aliases (e.g., `/faq/` → `/frequently_asked_questions/`). ERS serves aliases at 200 with no redirect, so the canonical script must map aliases to their primary paths. Add an alias map in the canonical script.
- [ ] Add `<meta name="robots" content="noindex, nofollow"/>` for these paths:
  - `/cp/` — ERS Control Panel
  - `/cart/` — Shopping cart
  - `?render_frame=` — ERS internal rendering URLs
- [ ] Verify by checking page source on the live site after pushing

### Google Search Console
- [ ] Set up GSC property for `https://www.` version of the domain
- [ ] Submit curated sitemap
- [ ] Monitor coverage report for 404s, noindex issues, and crawl status
- [ ] Use URL Inspection to request indexing for high-priority pages

## Content

### Landing Pages
- [ ] Hub pages (city-level) and spoke pages (city/category) need genuinely unique local content
- [ ] Google's helpful content system targets mass-produced location pages — differentiate beyond city name swaps
- [ ] Include local references: venue links, delivery details, area-specific FAQs
- [ ] Cross-link between hubs and spokes, and across cities via the service area section

## Legacy Site Migration
- [ ] Check for 404s from old site URLs (WordPress paths, old URL conventions)
- [ ] Old URLs will 404 indefinitely — ERS doesn't support server-level redirects
- [ ] Common old-to-new path differences: `/contact-us/` vs `/contact_us/`, `/about-us/` vs `/about_us/`, `/faqs/` vs `/frequently_asked_questions/`
- [ ] These 404s are low priority — Google will eventually drop them, but they waste crawl budget
