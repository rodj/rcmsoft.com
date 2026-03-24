# RCMSoft.com — Work Log

Project-specific log for rcmsoft.com. New entries at top.
**Note:** This project uses this file as its work log. The global Personal_Work_Log.md is NOT used for this project.

---

## 2026-03-24 — Email setup (robert@rcmsoft.com)

Broke when DNS was switched from Winhost nameservers to Namecheap BasicDNS — the MX record
that Winhost had been providing automatically was lost. Fixed and fully working as of 2026-03-24.

### Architecture (mirrors robert@rodj.me setup)
- **Mail server:** Winhost SmarterMail at `m02.internetmailserver.net`
- **Webmail:** https://m02.internetmailserver.net (login: robert@rcmsoft.com)
- **Incoming:** MX record @ → m02.internetmailserver.net (priority 10) at Namecheap
- **Forwarding:** SmarterMail auto-forwards all incoming mail to rodjmartin@gmail.com
- **Sending:** Gmail configured with "Send mail as: robert@rcmsoft.com" (SMTP via m02.internetmailserver.net:587, TLS)
  - Must manually select robert@rcmsoft.com from the From dropdown when composing
  - Gmail does not default to it automatically

### MX record (Namecheap Advanced DNS → Mail Settings → Custom MX)
- Type: MX, Host: @, Value: m02.internetmailserver.net, Priority: 10
- Note: MX is in the "Mail Settings" section, not "Host Records"

---

## 2026-03-24 — Full site launch

### Site creation
- Built full static HTML/CSS site from scratch, modeled on pointe.com structure
- Pages: index.html (homepage), about.html, contact.html, articles.html
- Single stylesheet style.css — dark navy (#0f2c4a) + gold (#f5a623) color scheme
- 5-item nav: Home | Services | Articles | About | Contact
- Homepage sections: hero, services grid (6 cards), "why RCMSoft" (3 cards), articles preview, CTA strip
- About page: honest solo-developer positioning ("you work directly with me")
- Contact page: Formspree form with service category dropdown
- Directory structure: articles/drafts/, doc/, util/ (mirrors pointe.com)
- Supporting files: CNAME, robots.txt (blocks /articles/drafts/), sitemap.xml, .gitignore, CLAUDE.md

### Draft articles created
- `articles/drafts/getting-started-with-claude-code.html` — full article, ready to publish
- `articles/drafts/mcp-server-python-word-automation.html` — full article, ready to publish
- Article order: Claude Code first, MCP/Word second

### GitHub
- Created repo: https://github.com/rodj/rcmsoft.com (public)
- Initial commit: b644cf1
- GitHub Pages enabled on main branch root
- CNAME recognized by GitHub as rcmsoft.com

### DNS (Namecheap)
- Domain was pointing at cPanel hosting nameserver — had to click "Change DNS Type" in Advanced DNS to switch to Namecheap BasicDNS before host records were editable
- Added 4 A records (@) pointing to GitHub Pages IPs:
  - 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- Added CNAME record: www → rodj.github.io

### Formspree
- Account created, form endpoint: https://formspree.io/f/xeepjorj
- Updated contact.html, committed (409a2f7), pushed

### Google Analytics
- GA4 property created for rcmsoft.com
- Measurement ID: G-C2J13YL8DH
- Snippet added (uncommented) to all 6 HTML files, committed (2d2f6ee), pushed

### Google Search Console
- Property added for rcmsoft.com
- Verified via "URL prefix" method (uses GA tag — no DNS TXT record needed)

### Remaining TODOs
- [ ] DNS propagation complete → enable "Enforce HTTPS" in GitHub repo Settings → Pages
- [ ] Submit sitemap: https://rcmsoft.com/sitemap.xml in Search Console → Sitemaps
- [ ] Publish first article (getting-started-with-claude-code) — see Publishing Checklist below

---

## Publishing Checklist

When moving an article from drafts/ to production:

1. Copy from `articles/drafts/` to `articles/`
2. Update stylesheet path: `../../style.css` → `../style.css`
3. Update nav paths: `../../index.html` → `../index.html`, etc.
4. Update CTA links similarly (same depth change)
5. Add publish date in the article-meta line (replace `[PUBLISH DATE]`)
6. Add `<url>` entry to sitemap.xml with today's date
7. Verify article card on articles.html points to `articles/filename.html` (not drafts)
8. Verify article card on index.html home page points correctly
9. Commit and push

---

## Upcoming Articles

| Target Date | Title | Status |
|-------------|-------|--------|
| TBD         | Getting Started with Claude Code | Draft |
| TBD         | Creating an MCP Server for Python to Automate Microsoft Word | Draft |
