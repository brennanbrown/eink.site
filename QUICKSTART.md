# Quick Start Guide

## ⚡ Easiest Method: Netlify + Prose.io (No Installation!)

**Don't want to install anything?** Deploy and edit entirely in your browser:

### 1. Deploy to Netlify (One Click)

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/brennanbrown/inkpage)

- Fork the repo and connect to Netlify
- Your site goes live in ~2 minutes
- Get a free `*.netlify.app` URL (or add your own domain)

### 2. Edit Content with Prose.io

1. **Visit**: [prose.io](https://prose.io)
2. **Authorize** with GitHub (one-time)
3. **Select your repository** from the list
4. **Navigate** to `_posts` folder
5. **Click** "New File" and start writing!

✅ No command line  
✅ No installation  
✅ Works on any device  
✅ Free hosting

**[→ See full guide for non-technical users](CONTENT-GUIDE.md)**

---

## 🚀 Developer Method: Local Setup in 3 Steps

### 1. Install & Serve

```bash
bundle install
bundle exec jekyll serve
```

Visit: **http://localhost:4000**

### 2. Add Your First Speech

Create a new file: `_posts/2025-09-30-my-first-speech.md`

```markdown
---
layout: default
title: "My First Speech"
date: 2025-09-30
category: personal
---

# {{ page.title }}

**Date:** {{ page.date | date: "%B %d, %Y" }}  
**Category:** {{ page.category }}

Your content goes here...

---

*End of document*
```

### 3. Rebuild & View

The site automatically rebuilds when you save. Just refresh your browser!

---

## 📱 Adding Content from Mobile

### Using Git on Mobile

**iOS - Working Copy:**
1. Clone your repository
2. Create new file in `_posts/`
3. Commit and push
4. Netlify rebuilds automatically (or GitHub Pages if you're using that)

**Android - Termux:**
```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
cd YOUR-REPO/_posts
nano 2025-09-30-my-speech.md
git add .
git commit -m "Add new speech"
git push
```

---

## 🎯 File Naming Convention

Always use this format: `YYYY-MM-DD-title-with-dashes.md`

**Examples:**
- ✅ `2025-09-30-quarterly-review.md`
- ✅ `2025-12-25-holiday-message.md`
- ❌ `my-speech.md` (missing date)
- ❌ `2025-9-5-speech.md` (use 09 and 05)

---

## 📂 Categories

Choose one for each post:

- **business** - Work presentations, quarterly reviews, team meetings
- **personal** - Personal thoughts, messages, journal entries  
- **technical** - Technical docs, how-to guides, presentations

---

## 🔧 Common Commands

```bash
# Serve locally
bundle exec jekyll serve

# Serve on local network (access from e-reader)
bundle exec jekyll serve --host 0.0.0.0

# Build for production
JEKYLL_ENV=production bundle exec jekyll build

# Clean build files
bundle exec jekyll clean

# Check site size
du -sh _site
```

---

## 📊 Performance Targets

Your pages should stay under these limits:

- **HTML Size**: < 10KB
- **HTTP Requests**: 1 (HTML only)
- **Load Time**: < 1 second on e-ink
- **External Dependencies**: 0

Check your page sizes:
```bash
find _site -name "*.html" -exec wc -c {} \;
```

---

## 🎨 Styling Tips

Keep it minimal for e-ink compatibility:

- **Use**: Black text on white background
- **Use**: System serif fonts
- **Use**: Simple margins and padding
- **Avoid**: Colors (except black/white/grey)
- **Avoid**: Images and media
- **Avoid**: JavaScript
- **Avoid**: Complex layouts (flexbox, grid)

---

## 🚨 Troubleshooting

### Posts not showing up?
- Check filename format: `YYYY-MM-DD-title.md`
- Verify date isn't in the future
- Ensure front matter is valid YAML

### Site won't build?
```bash
bundle exec jekyll clean
bundle exec jekyll build --trace
```

### Changes not appearing?
- Hard refresh browser (Cmd+Shift+R / Ctrl+Shift+R)
- Check Jekyll console for errors
- Restart Jekyll server

---

## 📚 Learn More

- **Full Documentation**: See `README.md`
- **Technical Specs**: See `docs/spec-sheet.md`
- **Jekyll Docs**: https://jekyllrb.com/docs/

---

## ✅ Checklist for New Posts

- [ ] File named correctly: `YYYY-MM-DD-title.md`
- [ ] Front matter includes: layout, title, date, category
- [ ] Content is plain text/markdown only
- [ ] No images or external links
- [ ] Tested on actual e-ink device (if available)

Happy writing! 📝
