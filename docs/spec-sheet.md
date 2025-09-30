# E-Ink Reader Website Spec Sheet

## Project Overview
A minimalist Jekyll-based website optimized for e-ink devices with limited processing power, designed for displaying text content (speeches, presentations, notes) uploaded from various devices.

## Technical Specifications

### Core Requirements
- **Framework**: Jekyll (static site generator)
- **Markup**: HTML5
- **Styling**: Minimal CSS (inline where possible)
- **No JavaScript** (for maximum compatibility)
- **No external dependencies** (self-contained)
- **File format**: Markdown for content, YAML for configuration

### Device Compatibility Targets
- E-ink readers (Kindle, Kobo, etc.)
- Experimental/limited browsers
- Low-power CPUs (slow rendering engines)
- Limited RAM environments
- Slow refresh rate displays

## Site Structure

### Directory Layout
```
eink-reader/
├── _config.yml
├── index.html
├── speeches.md
├── _layouts/
│   └── default.html
├── _includes/
│   ├── header.html
│   └── footer.html
├── _posts/
│   └── YYYY-MM-DD-speech-title.md
└── assets/
    └── css/
        └── style.css (minimal)
```

### Page Templates

#### 1. Homepage (`index.html`)
```
---
layout: default
title: Speech Reader
---

# Speech Reader

## Recent Speeches
[List of 5 most recent speeches with dates]

## Browse All Speeches
[Link to speeches archive page]

---
Last updated: [date]
```

#### 2. Speeches Archive (`speeches.md`)
```
---
layout: default
title: All Speeches
---

# All Speeches

## By Date
- [2024-03-15] Company Quarterly Review
- [2024-02-28] Conference Keynote
- [2024-01-10] Team Meeting Notes

## By Category
- [Business] [Link]
- [Personal] [Link]
- [Technical] [Link]
```

#### 3. Default Layout (`_layouts/default.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ page.title }}</title>
    <style>
        /* Minimal inline CSS */
        body { 
            font-family: serif; 
            margin: 0; 
            padding: 1em;
            background: white;
            color: black;
            line-height: 1.4;
        }
        h1, h2, h3 { margin: 0.5em 0; }
        a { color: #000; text-decoration: underline; }
        .container { max-width: 600px; margin: 0 auto; }
        .post-date { color: #666; font-size: 0.9em; }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <nav>
                <a href="/">Home</a> | 
                <a href="/speeches.html">All Speeches</a>
            </nav>
        </header>
        
        <main>
            {{ content }}
        </main>
        
        <footer>
            <hr>
            <p>E-Ink Speech Reader | Updated: {{ site.time | date: "%Y-%m-%d" }}</p>
        </footer>
    </div>
</body>
</html>
```

## Content Management

### Speech Post Format (`_posts/YYYY-MM-DD-title.md`)
```
---
layout: default
title: "Speech Title"
date: YYYY-MM-DD
category: [business/personal/technical]
---

# {{ page.title }}

**Date:** {{ page.date | date: "%B %d, %Y" }}
**Category:** {{ page.category }}

[Your speech content here...]

---
*End of document*
```

### Upload Methods
1. **Manual**: Add markdown files to `_posts` directory
2. **Git-based**: Push to repository (if using GitHub Pages)
3. **Mobile**: Use markdown editor apps that sync with repo

## Design & UX Specifications

### Visual Design Principles
- **Maximum contrast**: Black text on white background only
- **No images**: Text-only content
- **System fonts**: Rely on device's built-in serif fonts
- **No animations or transitions**
- **Minimal structural elements**

### Typography
- **Primary font**: `serif` (device default)
- **Fallback**: System serif stack
- **Base size**: 1em (respect user preferences)
- **Line height**: 1.4 for readability
- **No font loading**: Avoid @font-face declarations

### Layout
- **Single column**: No complex grids
- **Fixed width container**: 600px max for line length control
- **No floats or flexbox**: Simple block layout only
- **No positioning**: Static flow only

## Performance Optimizations

### Critical Restrictions
- Zero HTTP requests after page load
- No external resources (CDNs, fonts, analytics)
- No JavaScript execution
- No CSS frameworks or libraries
- Total page weight: <10KB per page

### Build Optimizations
- Minify HTML output
- Inline critical CSS
- Remove unnecessary Jekyll features
- Disable Sass processing (use plain CSS)

## Deployment Options

### 1. Local Network Deployment
- Run Jekyll locally, serve via simple HTTP server
- Access via local IP on e-reader browser

### 2. GitHub Pages
- Free hosting with automatic builds
- Push markdown files via mobile Git client

### 3. Self-hosted
- Build locally, upload static files to any web host

## Content Workflow

### Adding New Speeches
1. Write content in markdown format
2. Name file: `YYYY-MM-DD-descriptive-title.md`
3. Place in `_posts` directory
4. Rebuild site (or push to repo)
5. Refresh on e-reader browser

### Mobile Workflow Options
- **Working Copy** (iOS Git client)
- **Termux** (Android) with Git
- **Markdown editors** with folder sync
- **Simple text editors** + manual transfer

## Browser Compatibility Notes

### Supported Features Only
- Basic HTML5 elements
- CSS 2.1 properties only
- No ES6+ JavaScript features
- No Web APIs beyond core DOM

### Tested E-ink Browser Considerations
- Limited CSS support
- Slow rendering engines
- No JavaScript execution in some cases
- Basic navigation only

## Maintenance & Updates

### Regular Tasks
- Review and prune old content
- Backup `_posts` directory
- Test on actual e-ink device periodically
- Keep Jekyll version updated

### Expansion Possibilities
- Categories/tags for organization
- Search functionality (server-side if needed)
- Print stylesheet for physical copies
- Dark mode toggle (CSS only)

## Example Minimal CSS
```css
/* Absolute minimum styling */
body { 
    font-family: serif; 
    margin: 1em; 
    background: white; 
    color: black; 
    line-height: 1.4;
}
h1 { font-size: 1.4em; margin: 0.5em 0; }
h2 { font-size: 1.2em; margin: 0.5em 0; }
p { margin: 0.5em 0; }
a { color: black; text-decoration: underline; }
.container { max-width: 600px; margin: 0 auto; }
```