# responsive-site

Responsive navigation bar templates — pure HTML/CSS/JS, no build step.

## Overview

`nav/` contains two independent responsive navigation bar implementations:

| # | Directory | Source | Approach |
|---|-----------|--------|----------|
| 1 | `nav/How to Create Responsive Navigation Bar using HTML and CSS/` | Tutorial (ArtClub branding) | Checkbox-toggle hamburger (`input#check`), CSS-only slide-down menu |
| 2 | `nav/Responsive Navigation Bar using HTML, CSS & Javascript by evlearn/` | Tutorial (ArtClub branding) | JavaScript-controlled hamburger (`.hamburger` click → `classList.toggle('active')`) |

Both implementations share the same visual target (an "ArtClub" brand site with Home, About, Services, Contact, Feedback navigation links) and the same responsive breakpoint pattern (desktop menu collapses to a hamburger icon on smaller viewports).

## Structure

```
responsive-site/
├── README.md                  ← this file
├── nav/
│   ├── How to Create Responsive Navigation Bar using HTML and CSS/
│   │   ├── index.html         # checkbox-toggle nav (no JS)
│   │   ├── style.css          # includes hd.jpg background section
│   │   └── hd.jpg             # hero image (360 KB)
│   └── Responsive Navigation Bar using HTML, CSS & Javascript by evlearn/
│       ├── index.html         # JS-controlled hamburger nav
│       └── style.css          # dark header (#11101b) theme
```

## Key Differences

| Feature | Checkbox-toggle (nav #1) | JS-controlled (nav #2) |
|---------|------------------------|----------------------|
| Menu toggle mechanism | CSS `:checked` pseudo-class | JavaScript `classList.toggle()` |
| JavaScript dependency | None (Font Awesome CDN only) | Required for hamburger toggle |
| Menu reveal animation | `left: -100%` → `left: 0` | `height: 0` → `height: 450px` + `opacity: 0` → `opacity: 1` |
| Hamburger icon | Font Awesome `fas fa-bars` | CSS pseudo-elements (`.line` divs) |
| Breakpoint | `max-width: 858px` | `max-width: 900px` |
| Background | Blue (`#0082e6`) | Dark (`#11101b`) |

## Running

Open either directory's `index.html` directly in a browser:

```bash
# From nav #1
python3 -m http.server 8000  # then open http://localhost:8000

# Or simply open the file directly
# file:///path/to/nav/How to Create.../index.html
```

## Dependencies

- [Font Awesome 6.4.2](https://cdnjs.com/libraries/font-awesome) (CDN) — icon only, loaded via `<link>` + `<script>` in `index.html`

## Notes

- `hd.jpg` (360 KB) in nav #2 is a large hero image referenced by CSS `background: url('hd.jpg')`. Not gitignored — tracked in the repository.
- No `package.json`, no build tooling, no testing framework.
- Repo root `README.md` was a 31-byte stub ("Responsive site template list") before this rewrite.
