
# Scribble — Annotate & Snip Anywhere
#Microsoft Edge Add-Ons link=
https://microsoftedge.microsoft.com/addons/detail/fjkejlonkacdbnaiinnondfbhdajckic
A browser extension that lets you draw, highlight, and snip on top of **any** webpage.
Works identically in **Google Chrome** and **Microsoft Edge** (and any other Chromium
browser — Brave, Vivaldi, Opera, Arc) because they all support the same extension
format (Manifest V3). You only need to load this one folder once per browser.

## Features
- **Pen** — smooth freehand strokes
- **Pencil** — thin, slightly translucent freehand strokes
- **Highlighter** — thick, semi-transparent marker (multiply blend, like a real highlighter)
- **Eraser** — erases parts of your annotations
- **Shapes** — line, arrow, rectangle, ellipse
- **Text tool** — click and type anywhere on the page
- **Color palette** + custom color picker
- **Adjustable stroke width**
- **Undo / Redo / Clear all**
- **Snipping tool** — drag to select any region of the page, then Download or Copy it
  to your clipboard as a PNG
- **Full-page export** — save the current view *with* your annotations as one PNG
- **Draggable floating toolbar**, toggled from the toolbar icon or `Alt+Shift+A`

## Install in Google Chrome
1. Open `chrome://extensions`
2. Turn on **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Select this folder (`annotate-extension`)
5. Pin the "Scribble" icon from the puzzle-piece menu for quick access

## Install in Microsoft Edge
1. Open `edge://extensions`
2. Turn on **Developer mode** (left sidebar toggle)
3. Click **Load unpacked**
4. Select this same folder (`annotate-extension`)
5. Pin the icon from the extensions menu

No code changes are needed between the two browsers — it's the same package.

## How to use
1. Click the Scribble icon in your toolbar (or press `Alt+Shift+A`) to show/hide the
   floating toolbar on the current page.
2. Pick a tool, color, and stroke size, then draw directly on the page.
3. Use **Pointer** to temporarily click through to the page underneath your drawings.
4. Click the **snip icon** (dashed corners) to drag-select any region of the page —
   you'll get a preview you can **Download** or **Copy** to the clipboard.
5. Click the **save icon** (floppy disk) to export the whole visible page, including
   your annotations, as one PNG.
6. `Ctrl+Z` / `Ctrl+Shift+Z` to undo/redo. `Esc` cancels an in-progress snip selection.

## Notes & limitations
- Annotations are anchored to the browser **viewport**, not to the page content — if
  you scroll, your drawings stay in place on screen (this is intentional, the same
  behavior used by similar markup tools, and is what makes the snip/export feature
  produce a clean single image).
- Annotations are kept only in memory for that tab and are cleared on page reload.
- Because of how browser extensions load, tabs that were already open **before** you
  installed the extension need a page refresh before the toolbar will respond.
- The toolbar can't be shown on internal browser pages (`chrome://...`, `edge://...`,
  the Web Store) — this is a restriction all browser extensions share, not a bug.
- Clipboard "Copy" requires the page to be served over a normal http(s) origin.

## Folder contents
```
annotate-extension/
├── manifest.json      Extension configuration (Manifest V3)
├── background.js      Service worker: handles the toolbar icon and screen capture
├── content.js          Injected into every page: toolbar, drawing, and snipping logic
├── content.css         Styling for the toolbar, canvas, and snip UI
├── icons/               16 / 48 / 128 px icons
└── README.md           This file
```

## Publishing (optional)
If you'd like to publish this instead of loading it locally:
- **Chrome Web Store**: developer account (one-time fee), zip this folder, submit at
  the Chrome Web Store Developer Dashboard.
- **Microsoft Edge Add-ons**: free developer account, same zip works — submit at the
  Microsoft Edge Add-ons Developer Dashboard. Edge will re-review it independently of
  Chrome's store, but no code changes are required.
