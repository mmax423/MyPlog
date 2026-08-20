# 铸言 · MyPlog

> A literary blog that rains with the weather — essays, fiction, poetry, and campus wanderings, chronicling the writing life of a Chinese literature student.

[🌐 Live Preview](https://mmax423.github.io/MyPlog/) · [RSS Feed](https://mmax423.github.io/MyPlog/rss.xml)

---

## About

**铸言 (Zhùyán / "Casting Words")** is a single-file, fully static personal literary site. Everything — HTML, CSS, JavaScript, and all article data — is inlined into one `index.html`. No backend, no build step, no database: drop it on any static host and it goes live. It uses `localStorage` as local storage, so each visitor's reading progress, drafts, and comments stay in their own browser; the author writes and publishes through a hidden admin entry.

---

## ✨ Features

- **Single file, zero dependencies**: one `index.html` holds it all. marked.js / DOMPurify are inlined, so it renders even offline.
- **70+ original pieces**: essays, fiction, poetry, campus travelogues, book/film reviews, plans, study notes, lecture reports, research reports, and drama.
- **Categories & tags**: organized by genre, freely taggable, with tag filtering and curated series.
- **Weather effects**: real-time weather via [open-meteo](https://open-meteo.com), with programmatic Canvas rendering of clear / cloudy / rain / snow / fog / starry skies, following the visitor's location.
- **Immersive writing (Zen mode)**: one-key fullscreen writing; top/bottom bars auto-hide, Esc to exit, Ctrl/⌘+S to save, auto-saves drafts.
- **Resume reading**: remembers scroll position per article and picks up where you left off.
- **Dark mode**: one-click toggle, preference saved locally.
- **Daily quote bar**: a new line each day in the nav bar; click to shuffle, or jump to the source article.
- **"笔触校园" Campus Route Map**: a featured series ("笔触校园、文彰华农") with a map preview, gradient cover card, and article grid.
- **Social share cards**: full OG / Twitter Card support with cover image and summary on share.
- **RSS & static article pages**: `rss.xml` feed plus SSG-generated standalone article pages (each with its own URL and OG card) for better distribution and SEO.
- **Smooth scrolling**: Lenis silky scroll with restrained page transitions.
- **Optional comment backends**: Twikoo (guest comments by nickname) or giscus (GitHub Discussions storage), enable as needed.
- **Optional cross-device sync**: the author can supply a GitHub PAT to publish posts to repo Issues, visible on any device after refresh.

---

## 🛠 Tech Stack

| Layer | Choice |
|-------|--------|
| Structure | Plain HTML5 |
| Styling | Plain CSS3 (CSS variables / responsive / dark mode) |
| Logic | Vanilla JavaScript (no framework, no build step) |
| Rendering | marked.js (Markdown) + DOMPurify (XSS guard, both inlined) |
| Storage | localStorage (local) / optional GitHub Issues (cross-device) |
| Weather | open-meteo real-time API + Canvas rendering |
| Comments | Optional Twikoo / giscus |

---

## 📁 Project Structure

```
.
├── index.html          # The single source of truth (edit everything here)
├── rss.xml             # RSS feed
├── og-cover.jpg        # Social share cover
├── images/             # Article images
├── posts/              # SSG-generated standalone article pages
└── MyPlog/             # Deploy copy (includes GitHub Pages workflow)
```

---

## ✍️ Writing & Administration

The author entry is **hidden from visitors** by default to avoid exposing editing features.

- **Open admin**: press `Ctrl + Shift + A` anywhere on the page to summon the admin login modal; press again while logged in to log out.
- **After login**: a "设置 (Settings)" button appears top-right and a "写新文章 (+)" floating button bottom-right.
- **Settings panel**: edit bio, manage tags, backup/restore data, GitHub sync token, comment backend URL, weather effect testing.
- **Writing**: click the bottom-right `+` to enter the editor — Markdown, image upload, auto-save drafts, featured marking.

> ⚠️ The admin password is hardcoded in the public HTML; it is only an editing switch and **provides no real security**. A production setup should move auth to a backend.

---

## 🚀 Deployment

This is a pure static site — any of the following works:

### GitHub Pages (current live address)
1. Push `index.html`, `rss.xml`, `og-cover.jpg`, `images/`, `posts/` to your repo (e.g. `mmax423/MyPlog`).
2. Repo Settings → Pages → Source: **GitHub Actions**.
3. After push, Actions deploys automatically at `https://<user>.github.io/<repo>/`.

### CloudStudio / any static host
Upload `index.html` and friends to the static host's root directory.

---

## 🗺 Roadmap

- [x] Distributable: OG share cards + RSS + standalone article pages
- [x] "笔触校园" campus route map series
- [ ] Official comment backend (giscus / Twikoo)
- [ ] Discoverable: SEO structured data (JSON-LD), upgrade to history routing
- [ ] Content assets: featured exhibition hall, author's notes series
- [ ] Automated sync between working copy and deploy copy

---

## ⚠️ Known Limitations

- Comments / likes / view counts default to localStorage, so they are per-visitor unless Twikoo / giscus is enabled for cross-visitor sharing.
- Admin password is plaintext in the frontend.
- Storing images as base64 in localStorage can hit the quota; use an image host URL or the GitHub repo image host.

---

## 📄 License

© 2026 铸言 (Zhùyán). Article copyright belongs to the author; please credit the source when reposting. Code is for personal learning and use.
