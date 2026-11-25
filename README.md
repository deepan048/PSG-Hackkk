# Craftify

**Craftify** is a lightweight, browser-based visual multi-page website builder that lets users design, preview, and export responsive websites without writing code or setting up a backend.

---

## Project Overview

Craftify provides an interactive drag-and-drop canvas, a dark-themed workspace, a multi-page manager, reusable built-in and custom templates, global theme controls, and one-click multi-page HTML export — all running directly in the browser from a single `index.html` file.

## Problem Statement

Many beginners, students, and rapid-prototyping teams want to design multi-page websites visually without dealing with complex local build toolchains, heavy dependencies, database setups, or paid SaaS locks. Traditional static-site tools either require coding knowledge or lack integrated visual layout, page linking, and offline-friendly export.

## Proposed Solution

Craftify solves this by bundling a complete React-based visual editor into a zero-backend, single-file web application:
- Drag and drop components onto a zoomable, device-responsive canvas.
- Manage multiple independent pages (`Home`, `About`, `Services`, `Contact`, and custom pages) with a reusable **Nav Bar** component.
- Persist projects, themes, and custom templates locally in the browser using `localStorage` and `IndexedDB`.
- Export clean, linked multi-page HTML files (`index.html`, `<slug>.html`) ready to host anywhere.

---

## Features

- **Visual Drag-and-Drop Canvas**: Add, drag, resize, align, and style 11 component types (`Heading`, `Paragraph`, `Text`, `Button`, `Nav Bar`, `Image`, `Container`, `Section`, `Card`, `Input Field`, `Divider`).
- **Multi-Page Website Builder**:
  - Dedicated **Pages** panel with **+ Add Page** modal (name + URL slug).
  - Create, rename, duplicate, delete, drag-and-drop reorder, and set any page as the homepage.
  - Independent per-page component trees and undo/redo history.
  - Reusable **Nav Bar** component and **Button** page-linking (`targetPageId`).
- **Built-in & Custom Templates**:
  - 4 built-in templates (`Portfolio`, `Business`, `Landing Page`, `College Website`).
  - **Save as Template** modal with thumbnail preview, name/description, duplicate-name protection, and **My Templates** management (use, rename, duplicate, delete).
  - Image deduplication and automatic `IndexedDB` fallback when `localStorage` quota is reached.
- **Global Design Settings**: Configure primary, secondary, background, and text colors plus Google Fonts, and save/reuse custom themes.
- **Advanced Layers & Properties Panels**:
  - Rename layers, toggle visibility, lock/unlock elements, and drag-and-drop reorder layers.
  - Independently scrollable Properties panel for layout, content, colors, typography, borders, shadows, margins, and padding.
- **Image Upload**: Upload local images from your computer or paste external image URLs with `object-fit` and `border-radius` controls.
- **Keyboard Shortcuts**: `Ctrl+C` (Copy), `Ctrl+V` (Paste), `Ctrl+D` (Duplicate), `Ctrl+Z` (Undo), `Ctrl+Y` (Redo), `Delete` (Remove), `Esc` (Deselect), and Arrow keys (Nudge).
- **Workspace & Responsive Preview**:
  - `Fit to Screen`, Zoom In/Out/Reset (`1:1`), and collapsible left/right panels.
  - Desktop (`1280px`), Tablet (`768px`), and Mobile (`375px`) presets.
  - Full-screen interactive multi-page **Preview** mode.
- **Save, Load & Multi-Page Export**: Persist projects to `localStorage` and export separate, linked `.html` files for each page.

---

## Technologies Used

- **HTML5 & CSS3**
- **JavaScript (ES6+ / JSX)**
- **React 18 & ReactDOM 18** (via unpkg CDN)
- **Babel Standalone** (in-browser JSX transpilation via unpkg CDN)
- **Tailwind CSS** (via CDN)
- **Lucide React** (icons via unpkg CDN)
- **Google Fonts** (`Playfair Display` for Craftify branding + selectable site fonts)
- **Web Storage APIs**: `localStorage` and `IndexedDB`

---

## Installation and Setup

No Node.js installation, package manager, or build step is required.

1. **Clone the repository**:
   ```bash
   git clone https://github.com/<your-username>/craftify.git
   cd craftify
   ```
2. **Ensure internet access on first load** so the browser can fetch React, Babel, Tailwind CSS, Lucide Icons, and Google Fonts from their CDNs.

---

## Instructions to Run the Application

### Option 1: Open Directly in Browser
Double-click `index.html` or open it from your browser (`File` → `Open File...` → select `index.html`).

### Option 2: Run with a Local Static Server (Recommended)
Using Python:
```bash
python -m http.server 8000
```
Then open `http://localhost:8000` in your browser.

---

## Screenshots

> Add screenshots of your Craftify workspace, multi-page editor, templates gallery, and preview mode here before submitting.

```markdown
![Craftify Editor Workspace](screenshots/editor.png)
![Craftify Templates Gallery](screenshots/templates.png)
```

---

## Future Scope

- Export as a bundled `.zip` archive containing all pages and assets.
- Component grouping and nested container drop targets.
- Custom CSS/JS code injection per page.
- Responsive breakpoint-specific overrides for Tablet and Mobile layouts.
- Optional cloud sync or GitHub Pages one-click deployment.
