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
## 💡 Pro tips

*  Keep **Lock Layout = On** during daily use to avoid accidental edits.
*  Use **Export JSON** before major changes.
*  Seed categories (e.g., Docs, Learning, Tools) to stay organized from day one.

----

# Update 

--------

# Bookmark Board v1.1 - The Cross-Tab Update!

We're excited to release a major update focused on improving flexibility and workflow! This version introduces the much-requested ability to move bookmarks between tabs, along with several other quality-of-life enhancements.

## ✨ What's New

* **Move Bookmarks Between Tabs**: You can now easily organize your bookmarks across different boards!
    * **How it works**: Drag a bookmark and hover it over any tab button. The board will automatically switch, allowing you to drop the bookmark into a new category. If you drop it directly on the tab, it will be added to the first category.

* **Inline Category Renaming**: Quickly rename your categories without opening any menus.
    * **How it works**: Simply **double-click** any category title to edit it directly on the board. Press `Enter` or click away to save.

* **Tab Renaming**: Your tabs can now be renamed to better suit your projects.
    * **How it works**: Open the **Settings** (⚙️) modal and use the new "Rename Current Tab" option.

## 🔧 Other Improvements

* **Visual Drag-and-Drop Feedback**: Categories now highlight with a blue border when you drag a bookmark over them, making it clear where you're about to drop it.
* **Code Refinements**: The underlying code for handling drag-and-drop has been refactored and generalized for better maintainability.

---

Happy bookmarking!
