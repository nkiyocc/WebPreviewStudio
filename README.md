
readme_content = '''# Web Preview Studio

A lightweight, browser-based web development playground for testing HTML, CSS, and JavaScript with live device previews — no server, no build step required.

---

## Description

Web Preview Studio is a single-file HTML application that gives you a complete code editor + live preview environment right in your browser. It features a clean dark UI, multi-device preview frames (Desktop, Phone, Tablet), external library support, real-time error checking, and one-click project export.

Perfect for:
- Rapid prototyping and UI experiments
- Testing responsive designs across devices
- Learning HTML/CSS/JS without setting up a dev environment
- Previewing code snippets before deploying
- Sharing live demos via GitHub Pages

---

## Features

| Feature | Description |
|---------|-------------|
| **3-Panel Editor** | Separate tabs for HTML, CSS, and JavaScript with monospace font and tab indentation |
| **Live Preview** | Auto-updates after you stop typing (800ms debounce) or hit **Run** |
| **Multi-Device Preview** | Switch between Desktop, Phone (iPhone/Samsung/Infinix), and Tablet (iPad) |
| **Realistic Device Frames** | Each phone/tablet has accurate notch styles, bezels, and screen ratios |
| **Auto-Fit Scaling** | Device frames automatically scale down to fit the preview panel |
| **External Libraries** | Toggle CDN libraries: Tailwind, Bootstrap, jQuery, Font Awesome, React, Vue, Alpine, GSAP, Three.js |
| **Console Bridge** | `console.log`, `console.error`, and runtime errors from the preview appear in the built-in console |
| **Live Error Highlight** | Real-time syntax checking for unclosed HTML tags, unmatched CSS braces, and JS syntax errors |
| **Resizable Panels** | Drag the vertical divider to adjust editor vs. preview space |
| **Export Project** | Download as a single self-contained HTML file or copy individual files |

---

## How to Use

### Option A: Use Online (GitHub Pages)

If the project is hosted on GitHub Pages, simply visit the URL in your browser:

```
https://yourusername.github.io/web-preview-studio/
```

No download or installation needed. Works on any device with a modern browser.

### Option B: Use Locally

Download `web-preview-studio.html` and double-click it to open in any modern browser (Chrome, Edge, Firefox, Safari). No server or installation needed.

---

### 1. Write Your Code

- Switch between **HTML**, **CSS**, and **JS** tabs in the left panel
- Write or paste your code
- The editor supports `Tab` key for 2-space indentation
- Press **Run** or just stop typing — the preview auto-updates

### 2. Test Across Devices

- Click **Desktop** for a full responsive preview
- Click **Phone** to see a brand selector bar, then choose:
  - **iPhone 14 Pro** — Dynamic Island notch, 390×844
  - **Samsung Galaxy S24** — Punch-hole camera, 360×780
  - **Infinix Note 30** — Teardrop notch, 360×800
- Click **Tablet** for iPad Pro 11" preview (834×1194)

All device frames auto-scale to fit your screen size.

### 3. Add External Libraries

1. Click the **Libraries** button in the top-right header
2. Check the libraries you want (e.g., Tailwind CSS, Bootstrap)
3. Click **Apply & Run** — they are injected into the preview automatically

### 4. Monitor Errors & Console

- **Console** tab — shows `console.log`, `console.error`, `console.warn` from your preview code
- **Errors** tab — live syntax checking:
  - Red dot on a tab = errors in that file
  - Red border on editor = errors present
  - Click the Errors tab to see line-by-line details

### 5. Export Your Project

1. Click **Export** in the header
2. Choose your option:
   - **Download as Single HTML** — one file with everything bundled
   - **Copy HTML / CSS / JS** — copy individual files to clipboard

---

## Deploy to GitHub Pages

Want to host your own copy online? Here's how:

### Step 1: Create a GitHub Repository
1. Go to [github.com](https://github.com) and create a new repository
2. Name it anything (e.g., `web-preview-studio`)
3. Make it **Public**

### Step 2: Upload the File
1. In your repo, click **Add file → Upload files**
2. Drag and drop `web-preview-studio.html`
3. Click **Commit changes**

### Step 3: Enable GitHub Pages
1. Go to **Settings → Pages** (left sidebar)
2. Under **Source**, select **Deploy from a branch**
3. Choose **main** branch and **/(root)** folder
4. Click **Save**
5. Wait 1–2 minutes, then visit the URL shown (e.g., `https://yourusername.github.io/web-preview-studio/`)

> **Tip:** Rename `web-preview-studio.html` to `index.html` before uploading, or set it as the default page in your repo settings, so the URL loads it directly without the filename.

---

## Usage & Tips

### Writing HTML
You can write either a full HTML document or just the body content. The tool will:
- Extract `<body>` content automatically if present
- Preserve `<head>` content (title, meta tags, etc.)
- Wrap everything in a proper HTML5 document for the preview

### CSS Tips
- The preview iframe is sandboxed, so external `@import` or `url()` references work if the resource allows CORS
- CSS is injected into a `<style>` tag in the preview `<head>`

### JavaScript Tips
- Your JS runs inside the preview iframe, isolated from the studio itself
- `console.log()` output is bridged back to the studio's Console panel
- `window.onerror` is captured and displayed in the console
- For DOM queries, use standard `document.getElementById()` — the preview has its own DOM

### Using Libraries
- **Tailwind CSS** — add the CDN, then use Tailwind utility classes directly in your HTML
- **Bootstrap** — both CSS and JS are injected; you can use Bootstrap components and JS plugins
- **React** — select both React and ReactDOM, then write React code in your JS panel
- **Vue** — select Vue, then mount your app in the JS panel

### Responsive Testing
- The **Desktop** preview is a full responsive iframe — resize your browser window to test breakpoints
- Phone and tablet frames have fixed viewport sizes but scale visually to fit the panel
- The preview iframe always uses `width=device-width, initial-scale=1.0` for accurate mobile simulation

### Keyboard Shortcuts
| Key | Action |
|-----|--------|
| `Tab` | Insert 2 spaces in the editor |

### Error Checking Details
| File | What it checks |
|------|----------------|
| **HTML** | Unclosed tags, mismatched closing tags (e.g., `<div>` closed with `</span>`) |
| **CSS** | Unmatched `{` and `}` braces |
| **JS** | Syntax errors via safe `new Function()` parsing |

> Note: The JS error checker uses a safe parse — it won't execute your code, only validate syntax. Runtime errors still appear in the Console panel.

### Saving Your Work
The studio does not auto-save to disk or cloud. To preserve your work:
- Use **Export → Download as Single HTML** to save your project
- Or copy individual files and save them manually
- If using GitHub Pages, your code resets on page refresh — export before leaving

---

## Browser Compatibility

| Browser | Status |
|---------|--------|
| Chrome 90+ | ✅ Full support |
| Edge 90+ | ✅ Full support |
| Firefox 88+ | ✅ Full support |
| Safari 14+ | ✅ Full support |

Requires:
- ES6 support (arrow functions, template literals, `const`/`let`)
- `iframe srcdoc` support
- `Clipboard API` or `document.execCommand` for copy features

---

## File Structure

```
web-preview-studio.html    (single self-contained file)
```

No dependencies. No build step. Just one file.

---

## License

Free to use, modify, and distribute for personal or commercial projects.
'''

with open('/mnt/agents/output/README.md', 'w', encoding='utf-8') as f:
    f.write(readme_content)

print("README updated with GitHub Pages instructions")
