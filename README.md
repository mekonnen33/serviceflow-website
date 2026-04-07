# ServiceFlow Website — svc-flow.com

## Files
- `index.html` — Main site (logo embedded as base64)
- `blog.html` — Blog page
- `vercel.json` — Routes /blog cleanly
- `sitemap.xml` — For Google Search Console

## To Update the Logo
The logo is embedded as base64 in index.html and blog.html.
To swap it: search for `data:image/png;base64,` and replace the base64 string.

## Before Going Live
1. Replace `(your number here)` in modal success states with your actual phone
2. Add your Calendly link in the audit modal booking section
3. Add Google Analytics G-XXXXXXXXXX snippet to <head> of both files
