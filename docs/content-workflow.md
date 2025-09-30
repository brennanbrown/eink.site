# Content Workflow Options

This document shows all the different ways you can add content to your e-ink reader website.

## 🎯 Choose Your Method

```
┌─────────────────────────────────────────────────────────────┐
│                  CONTENT CREATION OPTIONS                    │
└─────────────────────────────────────────────────────────────┘

┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│   🌐 Prose.io    │  │  💻 GitHub Web   │  │  📱 Mobile Apps  │
│                  │  │                  │  │                  │
│  ✅ Easiest      │  │  ✅ Simple       │  │  ✅ On-the-go    │
│  ✅ Web-based    │  │  ✅ Built-in     │  │  ✅ Offline      │
│  ✅ Preview      │  │  ⚠️  Basic UI    │  │  ⚠️  App needed  │
│  ✅ Metadata UI  │  │  ⚠️  No preview  │  │  ⚠️  Git knowledge│
└──────────────────┘  └──────────────────┘  └──────────────────┘
        ↓                     ↓                      ↓
        └─────────────────────┴──────────────────────┘
                              ↓
                    ┌─────────────────────┐
                    │   GitHub Repository │
                    │  brennanbrown/      │
                    │    eink.site        │
                    └─────────────────────┘
                              ↓
                    ┌─────────────────────┐
                    │   GitHub Pages      │
                    │   Auto-builds in    │
                    │   1-2 minutes       │
                    └─────────────────────┘
                              ↓
                    ┌─────────────────────┐
                    │   🌍 Live Website   │
                    │   https://eink.site │
                    └─────────────────────┘
```

---

## Method Comparison

| Method | Difficulty | Setup Time | Best For |
|--------|-----------|-----------|----------|
| **Prose.io** | ⭐ Easy | 2 minutes | Most users |
| **GitHub Web** | ⭐⭐ Simple | 0 minutes | Quick edits |
| **Mobile Apps** | ⭐⭐⭐ Medium | 10 minutes | On-the-go |
| **Local Dev** | ⭐⭐⭐⭐ Advanced | 30 minutes | Developers |

---

## Detailed Workflows

### 1. Prose.io Workflow (Recommended)

```
User writes content
        ↓
Opens prose.io
        ↓
Clicks _posts folder
        ↓
Creates new file
        ↓
Fills metadata form
        ↓
Writes in editor
        ↓
Previews (optional)
        ↓
Clicks Save
        ↓
Enters commit message
        ↓
Content saved to GitHub
        ↓
GitHub Pages builds
        ↓
Live in 1-2 minutes! ✅
```

**Time**: ~5 minutes  
**Difficulty**: Very Easy  
**Requirements**: GitHub account only

---

### 2. GitHub Web Interface Workflow

```
User writes content (locally)
        ↓
Goes to GitHub repo
        ↓
Navigates to _posts
        ↓
Clicks "Add file"
        ↓
Creates new file
        ↓
Pastes content
        ↓
Commits directly
        ↓
GitHub Pages builds
        ↓
Live in 1-2 minutes! ✅
```

**Time**: ~3 minutes  
**Difficulty**: Easy  
**Requirements**: GitHub account only

---

### 3. Mobile App Workflow (iOS - Working Copy)

```
User opens Working Copy
        ↓
Clones repository (once)
        ↓
Navigates to _posts
        ↓
Creates new file
        ↓
Writes content
        ↓
Saves file
        ↓
Commits changes
        ↓
Pushes to GitHub
        ↓
GitHub Pages builds
        ↓
Live in 1-2 minutes! ✅
```

**Time**: ~10 minutes (first time), ~3 minutes (after)  
**Difficulty**: Medium  
**Requirements**: Working Copy app, basic Git knowledge

---

### 4. Local Development Workflow

```
User opens text editor
        ↓
Creates file in _posts/
        ↓
Names: YYYY-MM-DD-title.md
        ↓
Adds front matter
        ↓
Writes content
        ↓
Saves file
        ↓
Jekyll auto-rebuilds (if serving)
        ↓
Preview at localhost:4000
        ↓
Git add, commit, push
        ↓
GitHub Pages builds
        ↓
Live in 1-2 minutes! ✅
```

**Time**: ~2 minutes (after setup)  
**Difficulty**: Advanced  
**Requirements**: Ruby, Jekyll, Git, text editor

---

## Quick Decision Tree

```
START: I want to add a speech
        ↓
        ├─→ Never used Git? 
        │   └─→ USE PROSE.IO ⭐
        │
        ├─→ Just need quick edit?
        │   └─→ USE GITHUB WEB
        │
        ├─→ Writing on phone?
        │   └─→ USE MOBILE APP
        │
        └─→ Developer with setup?
            └─→ USE LOCAL DEV
```

---

## Common Use Cases

### Use Case 1: Business User Adding Quarterly Report
**Recommended**: Prose.io  
**Why**: Simple interface, no technical knowledge needed, can do from work computer

### Use Case 2: Executive Making Quick Edit from Phone
**Recommended**: GitHub Web Interface  
**Why**: No app installation, works in mobile browser, fast

### Use Case 3: Frequent Contributor (Multiple Speeches per Week)
**Recommended**: Mobile App or Local Dev  
**Why**: Faster workflow after initial setup, can work offline

### Use Case 4: Developer Maintaining Site
**Recommended**: Local Development  
**Why**: Full control, can test locally, familiar workflow

---

## Support Matrix

| Feature | Prose.io | GitHub Web | Mobile Apps | Local Dev |
|---------|----------|------------|-------------|-----------|
| Offline editing | ❌ | ❌ | ✅ | ✅ |
| Preview | ✅ | ❌ | Varies | ✅ |
| Metadata UI | ✅ | ❌ | ❌ | ❌ |
| Image upload | ✅ | ✅ | ✅ | ✅ |
| Batch edits | ❌ | ❌ | ✅ | ✅ |
| Auto-save | ⚠️ | ❌ | ✅ | ✅ |
| Mobile-friendly | ✅ | ✅ | ✅ | ❌ |

---

## Getting Help

- **Prose.io Issues**: See [CONTENT-GUIDE.md](../CONTENT-GUIDE.md)
- **GitHub Help**: [docs.github.com](https://docs.github.com)
- **General Questions**: [Open an issue](https://github.com/brennanbrown/eink.site/issues)

---

## Tips for Success

1. **Start with Prose.io** - Easiest to learn
2. **Use consistent filenames** - Always `YYYY-MM-DD-title.md`
3. **Write offline first** - Draft in your favorite app, then paste
4. **Preview before committing** - Catch errors early
5. **Use descriptive commit messages** - Help track changes

---

**Ready to start?** → [Open Prose.io](https://prose.io/#brennanbrown/eink.site)
