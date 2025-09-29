# BBEdit Preview Template Installation Guide

This guide explains how to use the enhanced markdown viewer as a BBEdit preview template.

## What You Get

When installed, you'll have a beautiful, feature-rich markdown preview in BBEdit with:

- ✅ **Syntax highlighting** for 180+ languages (highlight.js)
- ✅ **Mermaid diagrams** (flowcharts, sequence diagrams, etc.)
- ✅ **Math equations** (KaTeX for LaTeX rendering)
- ✅ **Table of Contents** with smooth scrolling
- ✅ **Dark mode toggle** (persists across sessions)
- ✅ **Print support** via `⌘P` (print-optimized layouts)
- ✅ **Auto-refresh** when you save/edit in BBEdit
- ✅ **Image support** with relative paths

## Installation

### Step 1: Locate BBEdit's Preview Templates Folder

Open BBEdit and navigate to the Preview Templates folder:

**Via BBEdit Menu:**
- `BBEdit` → `Folders` → `Preview Templates`

**Via Finder (Go to Folder):**
1. In Finder, press `⇧⌘G` (Shift-Command-G) or use menu `Go` → `Go to Folder...`
2. Paste this path: `~/Library/Application Support/BBEdit/Preview Templates/`
3. Click "Go"

**Via Terminal:**
```bash
# Create folder if it doesn't exist
mkdir -p ~/Library/Application\ Support/BBEdit/Preview\ Templates/

# Open in Finder
open ~/Library/Application\ Support/BBEdit/Preview\ Templates/
```

### Step 2: Copy the Template

Copy `bbedit-preview-template.html` to the Preview Templates folder:

```bash
cp bbedit-preview-template.html ~/Library/Application\ Support/BBEdit/Preview\ Templates/
```

Or drag and drop the file into the folder in Finder.

### Step 3: Use the Template

1. Open any `.md` or `.markdown` file in BBEdit
2. Press `⌃⌘P` (Control-Command-P) to open Preview
3. In the Preview window, click the "Templates" dropdown in the toolbar
4. Select `bbedit-preview-template.html`

**Tip:** BBEdit remembers your template choice for each file type!

## Usage - Web

The web version (`markdown-viewer.html`) can be used standalone in any browser:

1. Open `markdown-viewer.html` in your browser
2. Load a markdown file using one of two methods:
   - **Drag and drop** - Quick loading, but no auto-refresh
   - **Click "Load File" button** - Enables auto-refresh in Chrome/Edge
3. Use the toolbar buttons to navigate and interact with your document

### Auto-Refresh (Chrome/Edge Only)
When you load a file using the "Load File" button in Chrome or Edge, the viewer will automatically detect changes to the file and refresh the display every 2 seconds. This is perfect for editing markdown in your favorite editor while previewing changes in real-time.

**Note:** Auto-refresh requires the File System Access API, which is only available in Chrome, Edge, and Opera. Safari and Firefox users can still use the viewer with drag-and-drop or the Load button, but will need to manually click the "Refresh" button to see updates.

## Usage - BBEdit

The BBEdit template provides a seamless markdown preview experience directly within BBEdit:

### Table of Contents
- Click the **📑 TOC** button to show/hide the sidebar
- Click any heading to jump to that section
- Smooth scrolling for better navigation

### Dark Mode
- Click the **🌓 Theme** button to toggle dark/light mode
- Your preference is saved in localStorage
- Syncs highlight.js and Mermaid themes automatically

### Print
- Use `⌘P` to print
- Print-optimized CSS removes buttons and sidebar
- Clean, professional output

### Auto-Refresh
The preview automatically updates when you:
- Save the file (`⌘S`)
- Make edits (if auto-save is enabled)
- BBEdit detects file changes

No need to click refresh - it just works!

### Images
Images in your markdown work with relative paths:

```markdown
![My Image](images/photo.jpg)
![Demo](demo/demo-image.png)
```

BBEdit resolves image paths relative to your markdown file location, so if your markdown is in the project root, images in subdirectories will load correctly.

## Supported Markdown Features

### Code Blocks with Syntax Highlighting

\`\`\`javascript
function hello() {
    console.log("Hello, BBEdit!");
}
\`\`\`

### Mermaid Diagrams

\`\`\`mermaid
graph TD
    A[Start] --> B[BBEdit]
    B --> C[Beautiful Preview]
\`\`\`

### Math Equations

Inline: `$E = mc^2$`

Display block:
```
$$
\\int_{-\\infty}^{\\infty} e^{-x^2} dx = \\sqrt{\\pi}
$$
```

### GitHub Flavored Markdown
- [x] Task lists
- [x] Tables
- [x] Strikethrough with ~~text~~

## How It Works

BBEdit's preview system:
1. You edit markdown in BBEdit
2. BBEdit converts markdown → HTML (using cmark, MultiMarkdown, or Pandoc)
3. BBEdit injects the HTML into the template at `#DOCUMENT_CONTENT#`
4. The template applies:
   - Syntax highlighting via highlight.js
   - Diagram rendering via Mermaid
   - Math rendering via KaTeX
   - Table of Contents generation
   - Your chosen theme (light/dark)

## Customization

### Change Markdown Renderer
`BBEdit` → `Preferences` → `Languages` → `Markdown` → Choose renderer:
- cmark (default, fast)
- cmark-gfm (GitHub Flavored Markdown)
- MultiMarkdown (extended syntax)
- Pandoc (most features)

### Modify the Template
Edit `bbedit-preview-template.html` to customize:
- CSS colors and styling
- Button labels and icons
- JavaScript behavior
- CDN library versions

After editing, BBEdit automatically uses the updated template.

## Troubleshooting

### Preview doesn't update
- Make sure you saved the file (`⌘S`)
- Close and reopen the preview window (`⌃⌘P`)

### Mermaid diagrams don't render
- Check diagram syntax at [mermaid.js.org](https://mermaid.js.org)
- View browser console for errors (if preview is detached)

### Math equations don't render
- Ensure you're using proper LaTeX syntax
- Single `$` for inline, double `$$` for display blocks

### Dark mode doesn't persist
- Check browser localStorage isn't disabled
- BBEdit preview uses WebKit which has localStorage support

### Missing syntax highlighting
- Make sure language identifier is correct in code fence
- Example: \`\`\`python (not \`\`\`Python or \`\`\`py)

## Comparison: Web Version vs BBEdit Template

| Feature | Web Version | BBEdit Template |
|---------|-------------|-----------------|
| Syntax Highlighting | ✅ | ✅ |
| Mermaid Diagrams | ✅ | ✅ |
| Math Equations | ✅ | ✅ |
| Dark Mode | ✅ | ✅ |
| Table of Contents | ✅ | ✅ |
| Export HTML | ✅ | ❌ (Use BBEdit's export) |
| Print | ✅ Button | ✅ Via `⌘P` |
| Drag & Drop Files | ✅ | ❌ (Not needed) |
| Auto-refresh | Only Chrome/Edge | ✅ All browsers |
| File System Access API | Required for auto-refresh | ❌ (BBEdit handles it) |
| Standalone | ✅ | ❌ (Requires BBEdit) |
| Integration | Web browser | Native to BBEdit |
| Image Support | ✅ | ✅ Relative paths |

## Benefits of BBEdit Template

1. **Seamless workflow** - Edit and preview in one app
2. **True auto-refresh** - No polling, instant updates
3. **No browser required** - All within BBEdit
4. **Better performance** - Native WebKit rendering
5. **Persistent settings** - Theme and TOC preferences saved

## Support

For issues or questions:
- BBEdit documentation: [barebones.com/support/bbedit](https://www.barebones.com/support/bbedit/)
- Template issues: See main project README

## License

MIT License - Same as the main markdown-viewer project