# RCMSoft.com — Claude Code Project Notes

## Project Overview

**Site:** rcmsoft.com
**Purpose:** Business website for RCMSoft LLC — Atlanta-area software development, automation, Shopify, and forms processing services
**Owner:** Robert Martin (rodj)
**Tech Stack:** Plain HTML/CSS, no build tools, no frameworks
**Hosting:** GitHub Pages (free), served from `main` branch root
**Repository:** `github.com/rodj/rcmsoft.com` *(to be created)*
**Domain:** rcmsoft.com *(domain registrar: TBD)*

## Work Log

Use `doc/worklog.md` for this project (not the global Personal_Work_Log.md).
New entries at the top.

## Coding Standards

- Follow Rodj's global coding standards: `/rjmono/RJ_CODING_STANDARDS_RODJ.md`
- Indentation: TABS in HTML and CSS
- No JavaScript beyond Google Analytics
- No build tools (no npm, no webpack, no Jekyll)
- Single stylesheet: `style.css` in the root

## Directory Structure

```
rcmsoft.com/
├── index.html          Main homepage
├── about.html          About page (Robert Martin / solo positioning)
├── contact.html        Contact form (Formspree)
├── articles.html       Article index
├── style.css           Single stylesheet for entire site
├── CNAME               rcmsoft.com (for GitHub Pages custom domain)
├── robots.txt          Disallows /articles/drafts/
├── sitemap.xml         Update when publishing articles
├── articles/
│   ├── *.html          Published articles (live)
│   └── drafts/         *.html files not yet published
├── doc/
│   ├── worklog.md      Project work log
│   └── *.md            Other project documentation
└── util/               Utilities (e.g., scripts to help with publishing)
```

## Color Scheme (defined in style.css CSS variables)

| Variable        | Value     | Use                         |
|-----------------|-----------|-----------------------------|
| `--primary`     | `#0f2c4a` | Deep navy — headings, header background |
| `--accent`      | `#0077cc` | Blue — links, tag badges    |
| `--accent-light`| `#e8f4fd` | Very light blue — tip boxes |
| `--gold`        | `#f5a623` | Amber — CTA buttons, brand accent |
| `--bg`          | `#f9fafb` | Near-white — section backgrounds |
| `--text-muted`  | `#4a5568` | Gray — supporting copy      |

## Navigation (5 items, same on all pages)

Home | Services | Articles | About | Contact

Nav links use root-relative paths from each page's depth:
- Root pages (`index.html`, `about.html`, etc.): `index.html`, `about.html`, etc.
- Articles in `articles/`: `../index.html`, `../about.html`, etc.
- Drafts in `articles/drafts/`: `../../index.html`, `../../about.html`, etc.

## Article Format

### Tags (used in article cards and article headers)
- `AI Tools` — Claude, LLMs, AI-powered development
- `Automation` — Python scripts, PowerShell, workflow automation
- `Shopify` — Theme dev, app dev, Shopify integrations
- `Development` — General software development topics
- `Database` — SQL, reporting, data topics

### Article file naming
Use lowercase kebab-case: `getting-started-with-claude-code.html`

### Stylesheet path
- Published articles in `articles/`: `../style.css`
- Drafts in `articles/drafts/`: `../../style.css`

### Article structure
```html
<div class="article-header">
    <span class="tag">Category</span>
    <h1>Article Title</h1>
    <p class="article-meta">By Robert Martin — RCMSoft — Month D, 2026</p>
</div>
<article class="content">
    <!-- content: p, h2, h3, ul, ol, pre>code, .tip-box -->
</article>
<div class="callout-strip">
    <!-- CTA at the bottom of every article -->
</div>
```

## Contact Form (Formspree)

Contact form at `contact.html` uses Formspree.
**TODO:** Create Formspree account at formspree.io, create a form for robert@rcmsoft.com, and replace `YOUR_FORM_ID` in `contact.html` with the actual form ID.
The action URL format: `https://formspree.io/f/YOUR_FORM_ID`

## Google Analytics

**TODO:** Create GA4 property for rcmsoft.com at analytics.google.com.
All pages have the GA snippet commented out. Once the measurement ID is known (format: `G-XXXXXXXXXX`), uncomment and replace the placeholder in all HTML files.

## GitHub Pages Setup

**TODO: Complete these steps to go live:**

1. Create repo at github.com/rodj/rcmsoft.com (or rcmsoft-com)
2. Push this directory to the repo's `main` branch
3. Go to repo Settings → Pages → set Source to `main` branch, root folder
4. Add custom domain `rcmsoft.com` in the Pages settings
5. At domain registrar, set DNS A records to GitHub Pages IPs:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
6. Also add CNAME record: `www` → `rodj.github.io`
7. Wait for DNS propagation, then enable "Enforce HTTPS" in Pages settings
8. Optional: Move DNS to Cloudflare for CDN + free SSL (as done with pointe.com)

## Sitemap Maintenance

Update `sitemap.xml` whenever a new article is published.
Add an entry with:
- `<loc>https://rcmsoft.com/articles/filename.html</loc>`
- `<lastmod>YYYY-MM-DD</lastmod>`
- `<priority>0.8</priority>`

Also submit the sitemap URL to Google Search Console once the site is live.

## Brand / Voice Notes

- **Positioning:** Honest solo developer running a professional company. Use "I" not "we" in copy. Frame the solo nature as a benefit ("you work directly with the developer").
- **Tone:** Direct, practical, no marketing fluff. Write for business owners, not developers.
- **Location:** Always mention "Atlanta" — local is a key differentiator.
- **Services:** Custom software, automation, Shopify, forms processing, database/reporting, API integration.

## Publishing Checklist (article → production)

See `doc/worklog.md` for the full checklist.
