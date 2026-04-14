# PROJECT KNOWLEDGE BASE

**Generated:** 2026-04-14
**Commit:** 8e848b9
**Branch:** main

## OVERVIEW
Personal portfolio/landing page for Jens De Clercq (GenAI Developer). Single self-contained `index.html` — all CSS and JS inline, no build system, no framework, deployed via GitHub Pages.

## STRUCTURE
```
./
├── index.html          # Entire site: HTML + inline CSS + inline JS (724 lines)
├── img/
│   └── 1738164396143.jpeg  # Profile photo
├── preview-*.png       # Screenshot previews — gitignored, do not commit
└── .gitignore
```

## WHERE TO LOOK
| Task | Location |
|------|----------|
| Layout / sections | `index.html` — `<main class="container">` |
| All CSS | `index.html` — `<style>` block, lines 12–525 |
| Animations / JS | `index.html` — `<script>` block, lines 651–721 |
| Design tokens | `index.html` `:root` CSS vars (~line 13) |
| Skills list | `index.html` `<ul class="skills-list">` (~line 569) |
| Interests list | `index.html` `<ul class="interests-list">` (~line 589) |
| Contact modal | `index.html` `#contactModal` + `toggleModal()` (~line 624) |
| Profile image | `img/1738164396143.jpeg` |

## DESIGN TOKENS
```css
--bg: #0a0a0f        /* near-black background */
--fg: #f0f0f5        /* off-white text */
--muted: #888899     /* secondary text */
--accent: #00ff88    /* neon green — primary accent */
--border: rgba(255,255,255,0.1)

--font-display: 'Syne'        /* headings */
--font-mono: 'JetBrains Mono' /* code/terminal elements */
```

## CONVENTIONS
- **All uppercase headings** (`text-transform: uppercase` globally on h1–h4)
- **Typewriter effect**: rotating strings in `texts[]` array, `#typewriter` span
- **Scroll reveal**: `.reveal` class + IntersectionObserver; add `reveal` to new sections
- **Section numbering**: `01. CAPABILITIES`, `02. FOCUS AREAS` — increment for new sections
- **Cursor**: global `cursor: crosshair` — intentional design choice, do not remove
- **Profile image**: `grayscale(100%)` default, color on hover — intentional
- **Noise overlay**: `.noise-overlay` SVG at z-index 9999, opacity 0.05 — do not remove
- **Responsive breakpoint**: single breakpoint at `900px`

## ANTI-PATTERNS (THIS PROJECT)
- No external CSS files — keep all styles inline in `<style>` block
- No JS framework — vanilla JS only, no imports
- No build step — file is served as-is by GitHub Pages
- `preview-*.png` files are gitignored — never commit them
- `.playwright-mcp/` and `.idea/` are gitignored — never commit them

## DEPLOYMENT
GitHub Pages — push to `main` branch → auto-deployed at `https://jensdeclercq1.github.io/`

No build command. No test suite.

## NOTES
- `.playwright-mcp/` contains Playwright MCP session logs — ignore when editing
- Contact email: `jens.d.c@outlook.com`, LinkedIn: `/jens-de-clercq-015b37336/`, GitHub: `/JensDeClercq1`
- Typewriter cycling delay: 2500ms pause, 500ms between strings; 70ms type / 30ms delete
