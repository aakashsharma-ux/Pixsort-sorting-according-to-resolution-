# 🖼️ Pixsort — Image Resolution Manager

> Sort images by resolution, auto-rename sequentially, flag low-quality ones, and export as ZIP — **open `index.html` directly in your browser. No server, no install, no build step.**

---

## ⚡ Instant Start

1. Download / clone this repo
2. Double-click `index.html`
3. Done — it works immediately

Or deploy to **GitHub Pages** in 30 seconds (see below).

---

## ✅ All Fixes Implemented

| Fix | What it does |
|-----|-------------|
| **#1 — No drag after upload** | Once images are loaded, the global drag-and-drop is completely disabled. Only internal card-drag (reorder) is active. You can never accidentally re-upload by dragging. |
| **#2 — No duplicates during reorder** | Card drag swaps positions in the in-memory array by ID only — no file re-reading, no re-processing, no duplicates ever created. |
| **#3 — No file extensions in ZIP** | Export filenames are `1`, `2`, `3` — no `.jpg` / `.png`. Google Drive shows clean numeric names. |
| **#4 — Auto-sort on upload** | Images are sorted descending by pixel count (width × height) immediately after upload, before the grid is rendered. No user action required. |

---

## ✨ Features

- **Drag & drop** images or entire folders (upload phase only)
- **File picker** and **folder picker** buttons
- **Resolution detection** — reads actual pixel dimensions from each image
- **Auto-sort** — descending by resolution (highest first) — FIX #4
- **Sequential rename** — `1`, `2`, `3` … assigned after sorting
- **Low-res flagging** — red ⚠ badge on images < 380 × 380 px
- **Filter toggle** — show only low-resolution images
- **Drag-to-reorder** — drag cards to manually rearrange (FIX #2)
- **ZIP export** — clean numeric filenames, no extensions (FIX #3)
- **Deduplication** — skips already-loaded files by name + size
- **Dark / light mode** — persisted in localStorage + respects OS preference
- **50-image pagination** — "Show all" button for large sets
- **100% browser-based** — nothing ever leaves your machine

---

## 🚀 Deploy to GitHub Pages (Free, 30 seconds)

1. **Push to GitHub:**
   ```bash
   git init && git add . && git commit -m "init"
   git remote add origin https://github.com/YOUR_USERNAME/pixsort.git
   git push -u origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repo → **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **root**
   - Click **Save**

3. Your live URL:
   ```
   https://YOUR_USERNAME.github.io/pixsort/
   ```

No build pipeline. No Node.js. No server. Just a static file.

---

## 📁 Repository Structure

```
pixsort/
├── index.html    ← The entire application (HTML + CSS + JS)
└── README.md
```

That's it. One file.

---

## 🔧 Configuration

Open `index.html` in any text editor and change these constants at the top of the `<script>` block:

```js
const LOW_PX    = 380;   // Flag images below this resolution (px)
const PAGE_SIZE = 50;    // Cards shown before "Show all" button
```

---

## 🛡️ Privacy

All processing is done entirely in your browser:
- **FileReader API** — reads file contents locally
- **HTMLImageElement** — detects pixel dimensions locally  
- **JSZip** (loaded from CDN) — creates ZIP archive in memory

**No images, filenames, or metadata are ever sent to any server.**

---

## 📦 Dependencies

| Library | Version | Purpose | Source |
|---------|---------|---------|--------|
| JSZip | 3.10.1 | In-browser ZIP creation | cdnjs CDN |

No npm. No bundler. No framework.

---

## 📄 License

MIT © 2024 — Free to use, modify, and distribute.
