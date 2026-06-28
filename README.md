# ⬡ Territory Hierarchy Viewer

A standalone, single-file web app to visualize **Sokrio DMS territory bulk export** files as an interactive hierarchy — no backend, no installation, works directly in any browser.

---

## 🚀 Quick Start

1. Download `territory-hierarchy-viewer.html`
2. Open it in any browser (Chrome / Edge / Firefox)
3. Enter your **Company Name**
4. Upload your **Sokrio territory bulk export** (`.xlsx`)
5. Click **Generate Hierarchy**

> ✅ No internet required after loading. All processing happens locally in your browser.

---

## 📁 Input File Format

Export from **Sokrio DMS Web → Territory → Bulk Download**.

The app auto-detects the hierarchy levels from the column structure — no manual configuration needed. Works with any company's territory setup regardless of how many levels they have (Country → National → Zone → Division → Region → Territory → Distributor → Route, etc.)

---

## 🗂️ Features

### 🌳 Hierarchy Tree
- Full collapsible tree from root to leaf
- Every node shows **level badge**, **code**, **name**, and **assigned managers**
- **Search** by name, code, or manager name — matches highlight and auto-expand their parent chain
- Expand All / Collapse All controls

### 🔀 Flow View
- Sankey-style **drill-down view** — left to right, level by level
- Click any node to drill into it — its children and grandchildren appear to the right
- **Bar indicator** shows relative depth (sub-node count) per node
- **Curved lines** connect parent to children visually
- **Breadcrumb** navigation — click any ancestor to go back up
- **Search** by name or code — dropdown results with level badges, click to jump directly to that node with full context visible

### ⚠️ Duplicates
- Detects nodes with the **same name but different codes** within the same level
- For each duplicate group shows:
  - All code variants
  - **Parent (upper level)** — who it belongs to
  - **Children (lower level)** — what is under each variant

### 📊 Level Summary
- Node count per level
- Total managers per level
- Average managers per node

---

## 🏢 Multi-Company Support

Load one company at a time. Click **↩ Load New File** in the top bar to reset and load a different company's file.

---

## 🛠️ Tech Stack

| | |
|---|---|
| **Runtime** | Pure HTML + CSS + JavaScript |
| **Excel parsing** | [SheetJS (xlsx)](https://sheetjs.com/) via CDN |
| **Dependencies** | None (except SheetJS loaded from cdnjs) |
| **Backend** | ❌ None |
| **Data storage** | ❌ None — all in-memory, nothing sent anywhere |

---

## 🌐 Deploy via GitHub Pages

To share with your team without sending the file:

1. Push `territory-hierarchy-viewer.html` to a GitHub repository
2. Go to **Settings → Pages**
3. Set source to **main branch → / (root)**
4. Save — your app will be live at:
   ```
   https://<your-username>.github.io/<repo-name>/territory-hierarchy-viewer.html
   ```

---

## 📸 Screenshots

| Tree View | Flow View |
|---|---|
| Collapsible hierarchy with managers | Drill-down with curves and search |

---

## 📝 Notes

- Manager column supports **comma-separated multiple managers** — each shown as a separate chip
- Hierarchy depth is **auto-detected** — works for 3-level or 14-level companies equally
- Duplicate detection works **per level** — same name across different levels is not flagged
- All data stays in your browser — nothing is uploaded to any server

---

## 👤 Author

Built for internal use at **Sokrio** by the Client Onboarding & Business Development team.
