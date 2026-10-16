# Simple MarkItDown Web

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Powered by Pyodide](https://img.shields.io/badge/Pyodide-WebAssembly-orange.svg)](https://pyodide.org/)
[![Powered by MarkItDown](https://img.shields.io/badge/Microsoft-MarkItDown-0078D4.svg)](https://github.com/microsoft/markitdown)
[![Privacy: 100% Client--Side](https://img.shields.io/badge/Privacy-100%25%20Client--Side-brightgreen.svg)](#privacy--security)

A lightweight, private, and fully client-side web application to convert various document formats (PDF, Word, Excel, PowerPoint, HTML, and more) into clean Markdown (`.md`).

Powered by [Microsoft MarkItDown](https://github.com/microsoft/markitdown) running locally inside your browser via [Pyodide](https://pyodide.org/) (Python WebAssembly). **Your files are never uploaded to any external server.**

---

## ✨ Features

- 🔒 **100% Client-Side Privacy:** All conversions happen locally in your browser using WebAssembly. No data leaves your machine.
- ⚡ **Batch Processing:** Drag and drop single or multiple files at once. A background queue converts them sequentially without freezing the UI.
- 👁️ **Live Markdown Preview:** Inspect the generated markdown directly in the browser before saving.
- 📋 **Copy to Clipboard:** Copy converted markdown text with a single click.
- 💾 **Single & Batch Downloads:** Download converted files individually or download all completed files at once.
- 🌓 **Modern & Responsive UI:** Clean interface with automatic Light and Dark theme adaptation based on system preferences.
- 🚀 **Zero Backend / Serverless:** Self-contained static HTML application. No Node.js, Python server, or build step required.

---

## 📄 Supported Formats

| Document Type | Supported File Extensions |
| :--- | :--- |
| **PDF** | `.pdf` |
| **Word Documents** | `.docx` |
| **Excel Spreadsheets** | `.xlsx`, `.xls` |
| **PowerPoint Presentations** | `.pptx` |
| **Web & Structured Data** | `.html`, `.htm`, `.csv`, `.json`, `.xml` |
| **Text & E-Books** | `.txt`, `.epub` |
| **Archives** | `.zip` |

---

## 🛠️ How It Works

1. **Pyodide Initialization:** On page load, a dedicated background Web Worker initializes [Pyodide](https://pyodide.org/), a Python runtime compiled to WebAssembly.
2. **Dependency Loading:** Micropip installs required pure-Python packages (including `markitdown 0.1.4` and document parsers like `beautifulsoup4`, `mammoth`, `openpyxl`, `python-pptx`, etc.).
3. **In-Memory Conversion:** When you upload files, their binary contents are passed to the Web Worker and written to Pyodide's virtual in-memory file system (`py.FS`), parsed by MarkItDown, and the resulting markdown string is returned.
4. **Cleanup:** Temporary virtual files are immediately unlinked from memory after conversion.

---

## 🚀 Getting Started

### Option 1: Open Directly in Browser
Since this is a standalone static file, you can simply:
1. Clone or download this repository.
2. Double-click `index.html` or open it with any modern web browser (Chrome, Firefox, Safari, Edge).

### Option 2: Run via Local HTTP Server
For the best experience (or if your browser restricts Web Workers on `file://` URLs):

```bash
# Using Python
python3 -m http.server 8000

# Using Node.js (npx)
npx serve .
```
Then visit `http://localhost:8000` (or the URL printed in your terminal).

---

## 🌐 Deployment (Hosting)

Because Simple MarkItDown Web is purely static, you can host it for free on any static site platform:

- **[Cloudflare Pages](https://pages.cloudflare.com/):** Connect your GitHub repository and set the build output directory to `/`.
- **[GitHub Pages](https://pages.github.com/):** Go to repository **Settings** > **Pages** > select `main` branch and `/ (root)` folder.
- **[Vercel](https://vercel.com/):** Import the repository as a static project.
- **[Netlify](https://www.netlify.com/):** Drag-and-drop the project folder or connect via Git.

---

## 🔐 Privacy & Security

- **No Remote Processing:** Files are processed entirely in browser memory.
- **No Analytics / Tracking:** There are no trackers, telemetry, or external API calls sending your documents elsewhere.
- **Network Access:** Network requests are only made during initial page load to fetch Pyodide runtime and Python wheel packages from official CDNs (jsdelivr & PyPI).

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- [Microsoft MarkItDown](https://github.com/microsoft/markitdown) for the multi-format conversion engine.
- [Pyodide](https://pyodide.org/) for bringing the Python ecosystem into the browser via WebAssembly.
