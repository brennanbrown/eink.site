---
layout: default
title: "Static Site Architecture for E-Ink Devices"
date: 2025-09-15
category: technical
---

# {{ page.title }}

**Date:** {{ page.date | date: "%B %d, %Y" }}  
**Category:** {{ page.category }}

---

## Overview

This presentation explores the technical architecture behind building static websites optimized for e-ink displays and limited computing environments.

## Core Principles

### 1. Zero Client-Side Computation
E-ink devices often have severely limited processing power. By eliminating JavaScript entirely, we ensure instant page loads and maximum compatibility.

### 2. Minimal Bandwidth Usage
Every HTTP request matters on slow connections. Our approach:
- Inline all critical CSS
- No external dependencies
- No fonts, images, or media files
- Target page weight under 10KB

### 3. Progressive Enhancement Philosophy
Start with the most basic HTML that works everywhere, then carefully add only essential styling that degrades gracefully.

## Technical Stack

### Jekyll Static Site Generator
Jekyll provides:
- Simple markdown-to-HTML conversion
- Templating with Liquid
- Zero runtime dependencies
- Easy hosting options

### Build Process
1. Write content in markdown
2. Jekyll processes templates
3. Generate static HTML files
4. Deploy to any web host
5. No server-side processing required

## CSS Strategy

### What We Include
- Basic typography (font-family, line-height)
- Layout constraints (max-width for readability)
- Minimal spacing (margins, padding)
- Simple borders for visual hierarchy

### What We Exclude
- Animations and transitions
- Complex positioning (flexbox, grid)
- Web fonts
- Media queries (keep it simple)
- Colors beyond black/white/grey

## Performance Results

### Typical Page Metrics
- HTML size: 2-5KB
- Total page weight: 3-6KB
- HTTP requests: 1 (HTML only)
- Load time on e-ink: <1 second
- Rendering: Nearly instant

## Deployment Options

### Option 1: GitHub Pages
- Free hosting
- Automatic builds on push
- Easy content updates via Git

### Option 2: Local Network
- Run Jekyll locally
- Serve via simple HTTP server
- Access from e-reader on same network

### Option 3: Traditional Hosting
- Build site locally
- Upload static files via FTP/SFTP
- Works with any web host

## Content Management

### Adding New Posts
```
1. Create: _posts/YYYY-MM-DD-title.md
2. Add front matter (title, date, category)
3. Write content in markdown
4. Commit and push (or rebuild locally)
```

### File Structure
```
_posts/           # All content here
_layouts/         # HTML templates
_config.yml       # Site configuration
index.html        # Homepage
speeches.md       # Archive page
```

## Future Enhancements

### Potential Additions
- Search functionality (static index)
- Print stylesheet
- Dark mode (CSS only)
- Table of contents generation
- Export to plain text

### Constraints to Maintain
- No JavaScript requirement
- Single HTTP request per page
- Total compatibility with old browsers
- Sub-10KB page weight

## Conclusion

By embracing constraints and focusing on core functionality, we've created a reading platform that works reliably on the most limited devices while remaining easy to maintain and extend.

The key insight: Less is often more, especially when dealing with constrained environments.

---

*End of document*
