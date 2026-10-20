# Static site — The As-Received Web (Edition 01)

No build step. No dependencies. Upload this folder as-is to any static host
(Netlify drop, Cloudflare Pages, GitHub Pages, S3, a VPS).

## Files
- `index.html` — landing page
- `edition-01.html` — the report (print-ready: Print → Save as PDF)
- `data.html` — tables + downloads
- `corrections.html` — correction window
- `assets/site.css` — the only stylesheet
- `data/` — frozen CSV/JSON, MANIFEST, sha256 seals

## Contact path (no accounts, no forms)
- Set `AS_RECEIVED_CONTACT` in the environment (an email address) to turn the CTAs
  and the correction link into `mailto:` links with a prefilled subject and body.
- Leave it unset and every CTA still works: it points at the public channel
  (`https://x.com/afterhuman_ai`) — reply to the launch post or DM.
- There is no form, no backend, no email service, and no payment rail on this site.

```bash
AS_RECEIVED_CONTACT="you@example.com" python3 output/audit/build_site.py
```

## Rule
Do not hand-edit the generated HTML. Change copy in `build_site.py`, then:
```
python3 output/audit/build_site.py
```
Numbers are read from `output/as-received-web-2026-10-18/` (frozen, hashed).
Re-freezing the dataset means a new edition, not an edited page.

## Copy status
Landing copy mirrors EDITOR_SALES_PAGE_AND_TOC.md §2 (v13): free Edition 01,
founding annual $99, no seats, no countdown, no preorder, no early-bird price.
Banned: agent behaviour, task completion, scores, rankings, loss estimates.

---

## Published copy

Base URL: https://zencrypto101.github.io/as-received-web

This repository is a static copy of `output/site/` from the ai-attention-economy
project, with the domain placeholder replaced at publish time. The site folder
in the project stays pristine so the build is reproducible.
