# InkPage - E-Ink Reader Website

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/brennanbrown/inkpage)

A minimalist Jekyll-based website optimized for e-ink devices with limited processing power. Designed for displaying text content (speeches, presentations, notes) with maximum readability and compatibility.

**Original project by** [Brennan Kenneth Brown](https://brennanbrown.ca) · [Berry House 🍓](https://berryhouse.ca)

---

**📖 [Content Management Guide](CONTENT-GUIDE.md)** - Add content without Git or command line!  
**🌐 [Edit on Prose.io](https://prose.io)** - Web-based editor (easiest method)

## Features

- ✅ **Zero JavaScript** - Maximum compatibility with limited browsers
- ✅ **Minimal CSS** - All critical styles inlined, <10KB per page
- ✅ **Fast Loading** - Single HTTP request, instant rendering
- ✅ **E-Ink Optimized** - High contrast, clean typography, simple layout
- ✅ **Easy Content Management** - Write in Markdown, auto-generated navigation
- ✅ **Mobile-Friendly** - Add content from any device via Git

## Quick Start

### Prerequisites

- Ruby (2.5 or higher)
- Jekyll (4.0 or higher)
- Bundler

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
   cd YOUR-REPO
   ```

2. **Install dependencies**
   ```bash
   gem install bundler jekyll
   bundle install
   ```

3. **Build and serve locally**
   ```bash
   jekyll serve
   ```

4. **Open in browser**
   ```
   http://localhost:4000
   ```

### Alternative Setup (Without Bundler)

```bash
jekyll serve --watch
```

## ✨ Easy Content Management (No Technical Skills Required!)

**Don't want to use Git or command line?** We've got you covered!

### 🌐 Option 1: Prose.io (Recommended - Web-Based Editor)

The **easiest way** to add content. Just open your browser:

1. **Go to**: [prose.io](https://prose.io) and authorize with GitHub
2. **Select your repository** from the list
3. **Click** the `_posts` folder
4. **Create** or edit speeches with a simple web interface
5. **Save** - your content goes live automatically!

✅ Works like a blog editor  
✅ No installation needed  
✅ Works on any device with a browser  
✅ Preview your changes before publishing

### 📝 Option 2: GitHub Web Interface

1. Go to your repository on GitHub and navigate to the `_posts` folder
2. Click "Add file" → "Create new file"
3. Write your content
4. Click "Commit new file"

### 📱 Option 3: Mobile Apps

- **iOS**: [Working Copy](https://workingcopyapp.com/) - Full Git client
- **Android**: [MGit](https://play.google.com/store/apps/details?id=com.manichord.mgit) or [Markor](https://play.google.com/store/apps/details?id=net.gsantner.markor)

### 📖 Full Guide for Non-Technical Users

**See**: [`CONTENT-GUIDE.md`](CONTENT-GUIDE.md) for detailed step-by-step instructions on all methods!

---

## Adding Content (Developer Method)

### Create a New Speech/Post

1. Create a new file in `_posts/` directory
2. Name it: `YYYY-MM-DD-title.md`
3. Add front matter and content:

```markdown
---
layout: default
title: "Your Speech Title"
date: 2025-09-30
category: business
---

# {{ page.title }}

**Date:** {{ page.date | date: "%B %d, %Y" }}  
**Category:** {{ page.category }}

Your content here...

---

*End of document*
```

### Categories

Choose from:
- `business` - Business presentations and reviews
- `personal` - Personal speeches and notes
- `technical` - Technical presentations and documentation

### Front Matter Options

```yaml
layout: default        # Required - use default template
title: "Post Title"    # Required - displayed as heading
date: YYYY-MM-DD       # Required - used for sorting
category: business     # Optional - for categorization
```

## Project Structure

```
inkpage/
├── _config.yml           # Jekyll configuration
├── index.html            # Homepage (lists 5 recent speeches)
├── speeches.md           # Archive page (all speeches)
├── _layouts/
│   └── default.html      # Main template (with inline CSS)
├── _posts/               # Your content goes here
│   ├── 2025-09-25-welcome-speech.md
│   ├── 2025-09-20-quarterly-review.md
│   └── 2025-09-15-technical-presentation.md
├── assets/
│   └── css/
│       └── style.css     # Optional additional styles
└── docs/
    └── spec-sheet.md     # Full technical specification
```

## Deployment Options

### Option 1: Netlify (Recommended) ⭐

**One-Click Deploy:**

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/brennanbrown/inkpage)

**Manual Deploy:**

1. **Fork this repository** to your GitHub account
2. **Sign up** for [Netlify](https://netlify.com) (free tier is perfect)
3. **Click** "New site from Git"
4. **Select** your forked repository
5. **Build settings** (auto-detected from `netlify.toml`):
   - Build command: `bundle exec jekyll build`
   - Publish directory: `_site`
6. **Deploy!** Your site will be live in ~2 minutes

**Custom Domain:**
- Add your domain in Netlify dashboard under "Domain settings"
- No CNAME file needed - Netlify handles it automatically!

**Updating Content:**
- Use [Prose.io](https://prose.io) for easy editing
- Or edit files in `_posts/` via GitHub web interface
- Netlify automatically rebuilds and publishes in 1-2 minutes

**Why Netlify?**
- ✅ Automatic HTTPS
- ✅ Instant cache invalidation
- ✅ Free hosting
- ✅ Global CDN
- ✅ Easy custom domains
- ✅ Deploy previews for pull requests

### Option 2: GitHub Pages

1. **Fork this repository**
2. **Enable GitHub Pages** in Settings → Pages
3. **Source**: Deploy from main branch, root directory
4. **Custom domain** (optional): Add CNAME file with your domain
5. **Access at**: `https://yourusername.github.io/inkpage/`

**Note**: GitHub Pages can be slower to rebuild (5-10 minutes vs 1-2 for Netlify)

### Option 3: Local Network

Perfect for offline use or local e-reader access:

```bash
# Build the site
jekyll build

# Serve on local network (find your IP with ifconfig/ipconfig)
jekyll serve --host 0.0.0.0

# Access from e-reader browser
http://YOUR_IP:4000
```

### Option 4: Traditional Web Hosting

```bash
# Build static site
jekyll build

# Upload contents of _site/ directory to web host
# Via FTP, SFTP, or hosting control panel
```

## Mobile Workflow

Add content from your phone or tablet:

### iOS Options
- **Working Copy** - Full Git client, edit and commit
- **iA Writer** - Markdown editor with Git sync
- **Textastic** - Code editor with SSH/SFTP

### Android Options  
- **Termux** - Full terminal with Git
- **MGit** - Mobile Git client
- **Markor** - Markdown editor

### Workflow
1. Clone repository to mobile device
2. Create/edit markdown files in `_posts/`
3. Commit and push changes
4. Site rebuilds automatically (if using GitHub Pages)

## Performance Specifications

### Metrics
- **HTML Size**: 2-5KB per page
- **Total Page Weight**: 3-6KB (with inline CSS)
- **HTTP Requests**: 1 (HTML only)
- **External Dependencies**: 0
- **JavaScript**: None
- **Load Time**: <1 second on e-ink devices

### Optimizations
- All CSS inlined in template
- No external fonts or resources
- No images or media files
- Minimal HTML structure
- Compressed/minified output

## E-Ink Device Compatibility

Tested/designed for:
- Amazon Kindle (Experimental Browser)
- Kobo e-readers
- reMarkable tablets
- Boox devices
- PocketBook readers

### Browser Limitations Addressed
- No JavaScript support
- Limited CSS rendering
- Slow processing speeds
- Black and white displays
- Simple navigation only

## Customization

### Change Site Title
Edit `_config.yml`:
```yaml
title: "Your Site Name"
description: "Your description"
```

### Modify Styling
Edit inline CSS in `_layouts/default.html` (around line 10-70)

Key principles:
- Use only basic CSS 2.1 properties
- Maintain high contrast (black text on white)
- Keep single-column layout
- Avoid complex positioning or flexbox

### Add New Pages
Create new `.md` or `.html` files in root directory with front matter:
```yaml
---
layout: default
title: Page Title
---
```

## Troubleshooting

### Jekyll won't start
```bash
# Update Ruby gems
bundle update

# Reinstall Jekyll
gem uninstall jekyll
gem install jekyll
```

### Changes not showing
```bash
# Clean build and restart
jekyll clean
jekyll serve
```

### Posts not appearing
- Check filename format: `YYYY-MM-DD-title.md`
- Verify front matter is valid YAML
- Ensure date is not in the future
- Check file is in `_posts/` directory

## Development

### Local Testing
```bash
# Serve with live reload
jekyll serve --livereload

# Build for production
JEKYLL_ENV=production jekyll build

# Check build size
du -sh _site
```

### Adding Features

When adding new features, maintain these principles:
1. No JavaScript
2. Minimal CSS (inline preferred)
3. No external dependencies
4. Keep pages under 10KB
5. Test on actual e-ink device

## Contributing

1. Fork the repository
2. Create a feature branch
3. Test on e-ink device (if possible)
4. Submit pull request

## License

- **Code**: MIT License - See [LICENSE](LICENSE) file for details
- **Content**: All text content in `_posts/` is released into the Public Domain

You are free to use, modify, and distribute this project. Attribution is appreciated but not required.

## Support This Project

If you find this project useful, consider supporting its development:

- ☕ **[Ko-fi](https://ko-fi.com/brennan)** - Buy me a coffee
- 💖 **[GitHub Sponsors](https://github.com/sponsors/brennanbrown)** - Sponsor on GitHub
- ⭐ **Star this repo** - Help others discover it
- 🐛 **[Report Issues](https://github.com/brennanbrown/eink.site/issues)** - Help improve the project

### Get Help

- **Documentation**: See `docs/spec-sheet.md`
- **Issues**: Submit via [GitHub Issues](https://github.com/brennanbrown/eink.site/issues)
- **Questions**: Open a [discussion](https://github.com/brennanbrown/eink.site/discussions)

## Credits & Links

**Created by**: [Brennan Brown](https://brennanbrown.ca)  
**Project**: [BerryHouse.ca](https://berryhouse.ca)  
**Repository**: [github.com/brennanbrown/eink.site](https://github.com/brennanbrown/eink.site)

**Built with**:
- Jekyll - Static site generator
- Kramdown - Markdown processor
- Pure HTML/CSS - No frameworks

Optimized for simplicity, performance, and compatibility.

---

💙 Made with love for the e-ink community
