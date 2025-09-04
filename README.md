# 📑 Bookmark Board — README

A zero-backend, single-file **bookmark manager** that organizes links into **columns (categories)** across **multiple tabs (boards)** with **search, drag-and-drop, dark/light themes, JSON import/export, and a layout lock**. All data is stored locally via `localStorage`—**no servers, no tracking**.

---

## TL;DR

* **Open `index.html`** in any modern browser → start using.
* Data auto-saves to `localStorage` (`bookmarkBoard.v1`).
* Use **⚙️ Settings** to add tabs/categories, import/export JSON, toggle theme, and **lock** layout.

---

## Table of Contents

* [Features](#features)
* [Demo / Local Run](#demo--local-run)
* [Deploy to GitHub Pages](#deploy-to-github-pages)
* [How It Works](#how-it-works)
* [Data Model](#data-model)
* [Keyboard & UI UX](#keyboard--ui-ux)
* [Configuration & Customization](#configuration--customization)
* [Troubleshooting](#troubleshooting)
* [Roadmap](#roadmap)
* [Skills & Tech Stack](#skills--tech-stack)
* [Contributing](#contributing)
* [License](#license)

---

## Features

* **Multi-tab boards**: switch and reorder tabs; segregate contexts (Work, Study, Personal).
* **Category columns**: collapsible sections with per-category link counts.
* **Link ops**: add/edit links, favicon auto-fetch, open in new tab.
* **Drag-and-drop**: move links across categories (when unlocked).
* **Dual search**: filter by **Category** name and **Bookmark** text/URL.
* **Theme switch**: dark ↔ light (persisted).
* **Layout lock**: freeze editing & DnD to avoid accidental changes.
* **JSON import/export**: full data portability.
* **Zero dependencies**: pure HTML/CSS/JS; works fully offline.

---

## Demo / Local Run

1. Save your file as `index.html` (use the provided code).
2. Double-click `index.html` to open in Chrome/Edge/Firefox/Safari.
3. Click **⚙️ Settings** to add a **Category** and start dropping links.

> Pro tip: keep the file under version control (`git init`) so you can track changes to your local HTML.

---

## Deploy to GitHub Pages

1. New repo → add `index.html` (this app) at the repo root.
2. Commit & push:

   ```bash
   git add index.html
   git commit -m "feat: initial Bookmark Board"
   git push origin main
   ```
3. In GitHub: **Settings → Pages → Branch: `main` / root → Save**
4. Your app is live at `https://<your-user>.github.io/<repo>/`

---

## How It Works

* **Persistence**: Uses `localStorage` with key `bookmarkBoard.v1`.
* **State shape**: `{ tabs: [...], current: <index> }`
* **Lock**: `localStorage['bookmarkBoardLockLayout'] = 'true'|'false'`
* **Theme**: `localStorage['bookmarkBoardTheme'] = 'dark'|'light'`
* **Favicons**: `https://www.google.com/s2/favicons?domain=<host>&sz=32`
* **DnD**: HTML5 Drag & Drop API with JSON payload `{ linkId, fromCatId }`

---

## Data Model

```json
{
  "tabs": [
    {
      "id": "auto",
      "title": "Main",
      "categories": [
        {
          "id": "auto",
          "title": "Search Engines",
          "collapsed": false,
          "links": [
            { "id": "auto", "title": "Google", "url": "https://google.com" }
          ]
        }
      ]
    }
  ],
  "current": 0
}
```

* **IDs** are generated (`uid()`).
* `collapsed` is ensured on load for backward compatibility.

### Import / Export

* **Export**: **⚙️ → Export JSON** downloads `bookmark-board-<timestamp>.json`.
* **Import**: **⚙️ → Import JSON** chooses a JSON file matching the structure above.

---

## Keyboard & UI UX

* **Tabs**: click tab name to switch; drag tab items to reorder (when unlocked).
* **Categories**:

  * **▼ / ▶** toggles collapse
  * **+** adds link
  * **⚙️** rename/delete
* **Links**: drag to move (unlocked). Edit via ✏️ button (visible when unlocked).
* **Search**:

  * **Find Category** filters category titles
  * **Search Bookmarks** matches link title+URL

---

## Configuration & Customization

* **Make layout toggle look like ON/OFF**: already implemented via `updateLockToggleButton()`.
* **Change theme defaults**: update CSS variables in `:root` and `.light-mode`.
* **Branding**: change `<title>`, add a logo in the nav, tweak the palette.
* **Validation**: URL prompts enforce `http(s)://`—extend as needed.
* **Storage key**: change `STORAGE_KEY` if you want parallel boards on the same browser.

---

## Troubleshooting

* **“Nothing saves”**: Check browser storage settings; `localStorage` must be enabled.
* **Favicons not showing**: Some internal/unsupported domains won’t return icons; link still works.
* **Drag & drop not working**: Ensure **Layout** is **Unlocked** in **⚙️ Settings**.
* **Import says “Invalid JSON structure”**: Ensure your JSON has `tabs` as an array and matches the model.
* **Accidental edits**: Lock the layout (⚙️ → **Toggle** to **Locked**).

---

## Roadmap

* [ ] Inline, modal-based editors (no `prompt()`).
* [ ] Per-tab search and tag metadata for links.
* [ ] Optional cloud sync (OneDrive/GitHub Gist) with explicit user consent.
* [ ] Keyboard shortcuts (add link, jump to search fields).
* [ ] Accessibility polish (ARIA landmarks, focus states).
* [ ] Optional export of **tab/category** as Markdown.

---

## Skills & Tech Stack

**Tech:**

* HTML5, CSS3 (custom properties, responsive grid)
* Vanilla JavaScript (ES6+): DOM, Events, `localStorage`, Drag & Drop API, FileReader API

**Skills demonstrated:**

* Front-end architecture without frameworks
* State management using browser storage
* UX for information architecture (tabs, categories, search)
* Defensive coding (back-compat, validation, lock mode)
* Data portability (JSON import/export)

---

## Contributing

PRs welcome. Keep it **simple, dependency-free, and privacy-first**.

1. Fork → Feature branch → PR with a crisp changelog.
2. Add before/after screenshots or a short Loom/GIF if UI changes.
3. No libraries unless they are absolutely necessary.

---

## License

**MIT** — do what you want, just don’t blame the messenger.

---
