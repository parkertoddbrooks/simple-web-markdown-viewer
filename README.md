# Markdown Viewer

A lightweight, single-file markdown viewer for fast and easy document review.

## Features

- **Zero Configuration** - Just open the HTML file in any browser
- **Drag & Drop** - Load markdown files instantly
- **Auto-Refresh** - Automatically reload when files change (Chrome/Edge only)
- **Syntax Highlighting** - 180+ languages supported via highlight.js
- **Dark Mode** - Toggle between light and dark themes
- **Table of Contents** - Auto-generated navigation for long documents
- **GitHub Flavored Markdown** - Tables, task lists, and strikethrough
- **Mermaid Diagrams** - Flowcharts, sequence diagrams, and more
- **Math Equations** - KaTeX rendering for LaTeX expressions
- **Export & Print** - Save as HTML or print with optimized layouts

## Usage

1. Open `markdown-viewer.html` in your browser
2. Load a markdown file using one of two methods:
   - **Drag and drop** - Quick loading, but no auto-refresh
   - **Click "Load File" button** - Enables auto-refresh in Chrome/Edge
3. Use the toolbar buttons to navigate and interact with your document

### Auto-Refresh Feature

When you load a file using the "Load File" button in **Chrome** or **Edge**, the viewer will automatically detect changes to the file and refresh the display every 2 seconds. This is perfect for editing markdown in your favorite editor while previewing changes in real-time.

**Note:** Auto-refresh requires the File System Access API, which is only available in Chrome, Edge, and Opera. Safari and Firefox users can still use the viewer with drag-and-drop or the Load button, but will need to manually click the "Refresh" button to see updates.

## Requirements

Modern web browser with JavaScript enabled. No installation or build process required.

## Demo

Load `demo/demo.md` to see all features in action.

![Landing Page](images/01.png)

![Light Mode View](images/02.png)

![Dark Mode View](images/03.png)

## License

MIT License - see [LICENSE](LICENSE) file for details.