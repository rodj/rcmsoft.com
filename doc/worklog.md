# RCMSoft.com — Work Log

Project-specific log for rcmsoft.com. New entries at top.

---

## 2026-03-24

- Initial site creation
- Built full static site: index.html, about.html, contact.html, articles.html
- Created style.css (dark navy + gold color scheme)
- Created two draft articles in articles/drafts/:
  - getting-started-with-claude-code.html
  - mcp-server-python-word-automation.html
- Created CNAME, robots.txt, sitemap.xml, CLAUDE.md
- TODO: Create GitHub repo and enable GitHub Pages
- TODO: Set up Formspree account and update contact form endpoint
- TODO: Register Google Analytics property and add GA4 ID to all pages
- TODO: Configure DNS at domain registrar (A records for GitHub Pages apex domain)
- TODO: Submit sitemap to Google Search Console
- TODO: Publish first article (getting-started-with-claude-code): move from drafts/ to articles/, fix paths, add publish date, update sitemap, update articles.html links

---

## Publishing Checklist

When moving an article from drafts/ to production:

1. Copy from `articles/drafts/` to `articles/`
2. Update stylesheet path: `../../style.css` → `../style.css`
3. Update nav paths: `../../index.html` → `../index.html`, etc.
4. Update CTA links similarly
5. Add publish date in the article-meta line
6. Add Google Analytics snippet (uncomment and replace G-XXXXXXXXXX)
7. Add `<url>` entry to sitemap.xml with today's date
8. Verify article card on articles.html points to `articles/filename.html` (not drafts)
9. Verify article card on index.html home page points correctly
10. Commit and push

---

## Upcoming Articles

| Target Date | Title | Status |
|-------------|-------|--------|
| TBD         | Getting Started with Claude Code | Draft |
| TBD         | Creating an MCP Server for Python to Automate Microsoft Word | Draft |
