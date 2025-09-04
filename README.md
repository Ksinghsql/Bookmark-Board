# 📑 Bookmark Board — README

A single-file, local-first bookmark dashboard. Multiple tabs (boards), categories as cards, fast search, drag-and-drop, light/dark theme, JSON import/export, and a **Lock Layout** control — all persisted in `localStorage`.

---

## ✅ What’s in this code

*  **Pure front-end**: 1 HTML file (HTML + CSS + vanilla JS). No frameworks, no build.
*  **Tabs (boards)**: create/delete, click to switch, drag to reorder (when unlocked).
*  **Categories**: cards with title, collapse/expand, add/delete, reorder via Settings.
*  **Bookmarks**: add, open in new tab, favicon auto-fetch, quick **✏️ Edit** (when unlocked).
*  **Search**: “Find Category” and “Search Bookmarks” inputs filter live.
*  **Drag-and-drop**: move links between categories (unlocked only).
*  **Theme**: toggle Light/Dark (persists).
*  **Lock Layout**: freezes editing & drag to prevent accidental changes.
*  **Import/Export JSON**: backup/restore your boards.
*  **Local persistence**: everything saved to `localStorage` under key `bookmarkBoard.v1`.

---

## 🚀 Quick start

1. **Save the file**

   * Name it e.g. `bookmark-board.html`.

2. **Open it**

   * Double-click to open in any modern browser (Chrome/Edge/Firefox/Safari).
   * No server required.

3. **Start using**

   * Click **⚙️ Settings** (top-right) to manage layout and data.
   * Data auto-saves to your browser’s `localStorage`.

---

## 🧭 Core workflow (how to use)

*  **Add a Tab** → **⚙️ Settings** → **+ Tab**.
*  **Delete current Tab** → **⚙️ Settings** → **Delete Tab**.
*  **Reorder Tabs** → drag tab headers (only when **Unlocked**).
*  **Add a Category** → **⚙️ Settings** → **+ Category**.
*  **Rename/Delete Category** → Card **⚙️** → choose **Rename** or **Delete**.
*  **Reorder Categories** → **⚙️ Settings** → **Reorder Categories** (↑ / ↓).
*  **Collapse/Expand Category** → Card **▼ / ▶**.
*  **Add Bookmark** → Card **+** → enter **URL** and **Title**.
*  **Edit Bookmark** → Click **✏️** next to a link (only when **Unlocked**).
*  **Move Bookmark** → Drag a link to another category (only when **Unlocked**).
*  **Search** → Top bar: **Find Category** or **Search Bookmarks**.
*  **Theme** → **⚙️ Settings** → **Toggle** (Light/Dark).
*  **Lock Layout** → **⚙️ Settings** → **Layout: On/Off** (prevents edits/drag).
*  **Export** → **⚙️ Settings** → **Export JSON** (downloads a backup).
*  **Import** → **⚙️ Settings** → **Import JSON** (choose a previous backup).

---

## 🛠 Tech stack

*  **HTML5** for structure
*  **CSS** (no frameworks) for theming & layout
*  **JavaScript (ES6)** for state & interactions
*  **localStorage** for persistence

---

## 📂 Data model (stored in `localStorage`)

```json
{
  "tabs": [
    {
      "id": "string",
      "title": "Main",
      "categories": [
        {
          "id": "string",
          "title": "Category Name",
          "collapsed": false,
          "links": [
            { "id": "string", "title": "Example", "url": "https://example.com" }
          ]
        }
      ]
    }
  ],
  "current": 0
}
```

---

## 🔐 Privacy & limitations

*  **Local-first**: data never leaves your browser (no calls to any backend).
*  **Favicon fetch**: uses Google’s favicon service by domain (for icons only).
*  **Per-browser**: your boards live in the browser where you use the file.
*  **Clearing site data** will remove your boards — use **Export JSON** regularly.

---

## 🧪 Compatibility

*  Works on modern desktop browsers (Chromium/Firefox/Safari).
*  Mobile browsers work but drag-and-drop UX varies by device.

---

## 📦 How to add this to GitHub

1. Create a new repo (e.g., `bookmark-board`).
2. Add two files:

   * `bookmark-board.html` (your code above)
   * `README.md` (this file)
3. Commit & push.
4. (Optional) Enable **GitHub Pages** → *Deploy from branch* → open the published URL.

---

## 📝 License

MIT (recommended). Add a `LICENSE` file if you want to open-source it.

---

## 💡 Pro tips

*  Keep **Lock Layout = On** during daily use to avoid accidental edits.
*  Use **Export JSON** before major changes.
*  Seed categories (e.g., Docs, Learning, Tools) to stay organized from day one.
