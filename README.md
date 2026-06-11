# Tab Manager Pro — Chrome Extension

A powerful tab management extension with a clean glassmorphism UI. List, search, group, and save all your open tabs — right from the toolbar.

---

## Features

| Feature | Description |
|---|---|
| **All Tabs list** | See every open tab with favicon, title, and URL |
| **Real-time search** | Filter tabs instantly as you type — matches title and URL |
| **By Domain view** | Tabs automatically grouped by hostname, collapse/expand groups |
| **Close all in domain** | One click closes every tab from the same site |
| **Pin / Unpin tabs** | Toggle pin directly from the popup |
| **Group by domain** | Auto-creates Chrome tab groups for all domains (2+ tabs) |
| **Close duplicates** | Detects and removes duplicate URLs in one click |
| **Save sessions** | Save your current open tabs as a named session |
| **Restore sessions** | Re-open all tabs from any saved session |
| **Delete sessions** | Remove sessions you no longer need |
| **Tab badge** | Extension icon shows the total number of open tabs |

---

## Installation (2 minutes)

1. Open Chrome and go to `chrome://extensions/`
2. Enable **Developer mode** (toggle in the top-right corner)
3. Click **Load unpacked**
4. Select the `tab-manager` folder
5. The extension icon appears in your toolbar — click it to open

---

## How to Use

### Search
Type anything in the search bar to instantly filter tabs by title or URL. Matching text is highlighted. Press the **×** button or clear the field to reset.

### All Tabs
- **Click a tab row** → switches to that tab and focuses its window
- **Pin button** → pin or unpin the tab
- **× button** → close the tab immediately

### By Domain
- Tabs are grouped by their hostname
- Click a group header to **collapse or expand** it
- Click the **× on a group header** to close all tabs from that domain

### Sessions
1. Click the **save icon** in the header to open the save dialog
2. Give your session a name (e.g., "Work", "Research")
3. Click **Save Session** — all currently open tabs are saved
4. In the Sessions view, click **Restore** to re-open all tabs, or **Delete** to remove the session

### Header Buttons
| Icon | Action |
|---|---|
| Grid / radial | Group all tabs by domain using Chrome tab groups |
| Floppy disk | Save current tabs as a named session |
| Trash | Close all duplicate tabs (keeps the first occurrence) |

---

## File Structure

```
tab-manager/
├── manifest.json       # Extension config (Manifest V3)
├── popup.html          # Main popup UI
├── popup.css           # Glassmorphism styles
├── popup.js            # All tab management logic
├── background.js       # Service worker (tab count badge)
└── icons/
    ├── icon16.png
    ├── icon48.png
    └── icon128.png
```

---

## Permissions Used

| Permission | Why |
|---|---|
| `tabs` | Read tab list, titles, URLs, favicons |
| `storage` | Save and load sessions |
| `tabGroups` | Create Chrome tab groups by domain |

---

## Tech Stack

- **Manifest V3** — current Chrome extension standard
- **chrome.tabs API** — query, update, remove, and group tabs
- **chrome.storage.local** — persist sessions across browser restarts
- **chrome.tabGroups API** — create native tab groups
- Pure HTML / CSS / JS — zero dependencies, no build step needed
