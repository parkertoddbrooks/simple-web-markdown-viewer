# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a simple single-file web application that provides a drag-and-drop Markdown viewer. The entire application is contained in `markdown-viewer.html` - a standalone HTML file with embedded CSS and JavaScript.

## Architecture

- **Single-file application**: All code (HTML structure, CSS styling, JavaScript functionality) is contained in `markdown-viewer.html`
- **No build process**: Open the HTML file directly in a browser to run the application
- **External dependency**: Uses marked.js from CDN (https://cdn.jsdelivr.net/npm/marked/marked.min.js) for Markdown parsing

## Key Components

The application has three main states/sections:

1. **Drop Zone (`#drop-zone`)**: Initial landing screen with gradient background that prompts users to drag and drop a .md file
2. **Viewer Container (`#viewer-container`)**: Main viewing interface shown after a file is loaded, containing:
   - Header with file info and controls (Load New File, Refresh Now buttons)
   - Content area with rendered Markdown
3. **Status Messages**: Toast-style notifications at bottom-right for user feedback

## Core Functionality

- **File Loading**: Handles .md and .markdown files via drag-and-drop or file picker
- **Markdown Rendering**: Uses marked.js to convert Markdown to HTML (line 382)
- **File Refresh**: Manual refresh via "Refresh Now" button or re-dropping the same file
- **Auto-refresh Monitoring**: Timer-based check (line 393) exists but is limited by browser security - actual refresh requires user action

## Development

To develop or test:
```bash
open markdown-viewer.html  # macOS
# or just open the file in any web browser
```

No compilation, build, or dependency installation required.

## Key Limitations

Due to browser security restrictions, the application cannot automatically detect file system changes. Users must manually refresh by:
- Clicking the "Refresh Now" button and selecting the file again
- Re-dropping the file onto the viewer