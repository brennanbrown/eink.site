# Setup Guide

This guide will help you configure your InkPage site after forking or deploying.

## 🚀 Quick Setup (5 Minutes)

### Step 1: Fork or Deploy

**Option A: One-Click Netlify Deploy (Easiest)**
1. Click: [![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/brennanbrown/inkpage)
2. Connect your GitHub account
3. Choose a repository name
4. Deploy!

**Option B: Fork on GitHub**
1. Go to: https://github.com/brennanbrown/inkpage
2. Click "Fork" button (top right)
3. Choose your account
4. Done!

### Step 2: Configure Your Site

Edit `_config.yml` in your repository:

```yaml
# Site settings
title: "Your Site Title"              # Change this!
description: "Your description here"   # Change this!
author: "Your Name"                    # Change this!
baseurl: ""                            # Leave empty for Netlify/custom domain
url: ""                                # Netlify auto-detects, or add your domain
github_username: "your-username"       # Optional: your GitHub username
repository: "your-username/your-repo"  # Optional: enables GitHub link in footer
```

### Step 3: Configure Prose.io (Optional but Recommended)

Edit `_prose.yml`:

```yaml
prose:
  rooturl: '_posts'
  siteurl: 'https://your-site-url.com'  # Your site URL
  media: 'assets/images'
```

### Step 4: Add Your First Post

1. Go to [prose.io](https://prose.io)
2. Select your repository
3. Navigate to `_posts`
4. Create a new file: `2025-09-30-my-first-post.md`
5. Add content and save!

---

## 🌐 Custom Domain Setup

### For Netlify (Recommended)

1. **Log into Netlify Dashboard**
2. **Go to**: Domain settings
3. **Click**: "Add custom domain"
4. **Enter your domain**: `yourdomain.com`
5. **Add DNS records** at your domain provider:
   ```
   Type: A
   Name: @
   Value: 75.2.60.5
   
   Type: CNAME
   Name: www
   Value: your-site.netlify.app
   ```
6. **Wait** for DNS propagation (5-30 minutes)
7. **Enable HTTPS** in Netlify (automatic)

### For GitHub Pages

1. **Create** a file named `CNAME` in your repository root
2. **Add your domain**: `yourdomain.com`
3. **Commit** the file
4. **Add DNS records** at your domain provider:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153
   
   Type: CNAME
   Name: www
   Value: your-username.github.io
   ```
5. **Enable** custom domain in GitHub Pages settings
6. **Wait** for DNS propagation

---

## 🎨 Customization Options

### Change Site Title and Description

Edit `_config.yml`:
```yaml
title: "My Personal Speeches"
description: "A collection of my thoughts and presentations"
```

### Modify Footer

Edit `_layouts/default.html` around line 77-84:

```html
<footer>
    <p>
        <strong>{{ site.title }}</strong> | Updated: {{ site.time | date: "%Y-%m-%d" }}<br>
        Add your custom footer text here<br>
        <small>Your copyright notice</small>
    </p>
</footer>
```

### Change Styling

All CSS is inlined in `_layouts/default.html` (lines 7-62).

**Key styles to customize:**
```css
body { 
    font-family: serif;  /* Change font */
    color: black;        /* Change text color */
    background: white;   /* Change background */
}

.container { 
    max-width: 600px;    /* Change content width */
}
```

**Keep it minimal!** This site is optimized for e-ink devices. Avoid:
- Complex colors (stick to black/white/grey)
- Heavy fonts (use system defaults)
- Large images
- JavaScript

### Add Categories

Edit posts to use these categories:
- `business` - Work-related content
- `personal` - Personal thoughts
- `technical` - Technical documentation

Add new categories by editing `speeches.md`:

```markdown
### Your New Category
<ul class="post-list">
{% for post in site.posts %}
  {% if post.category == "your-category" %}
  <li>
    <span class="post-date">[{{ post.date | date: "%Y-%m-%d" }}]</span>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>
```

---

## 📝 Content Management

### Delete Example Posts

Remove these files from `_posts/`:
- `2025-09-25-welcome-speech.md`
- `2025-09-20-quarterly-review.md`
- `2025-09-15-technical-presentation.md`

### Add Your Own Posts

**Via Prose.io** (easiest):
1. Go to [prose.io](https://prose.io)
2. Select your repo
3. Create new file in `_posts/`

**Via GitHub**:
1. Navigate to `_posts/` in your repo
2. Click "Add file" → "Create new file"
3. Name: `YYYY-MM-DD-title.md`

**Template**:
```markdown
---
layout: default
title: "Your Post Title"
date: 2025-09-30
category: personal
---

# {{ page.title }}

**Date:** {{ page.date | date: "%B %d, %Y" }}  
**Category:** {{ page.category }}

Your content here...

---

*End of document*
```

---

## 🔧 Advanced Configuration

### Enable Comments (Optional)

If you want comments, add a service like:
- [Utterances](https://utteranc.es/) (GitHub issues)
- [Giscus](https://giscus.app/) (GitHub discussions)

**Warning**: Adds JavaScript (not ideal for e-ink)

### Analytics (Optional)

Add lightweight analytics like:
- [GoatCounter](https://www.goatcounter.com/) (privacy-friendly)
- [Plausible](https://plausible.io/) (lightweight)

**Warning**: Adds external requests

### Search Functionality

For a static site, consider:
- [Lunr.js](https://lunrjs.com/) - Client-side search
- [Algolia](https://www.algolia.com/) - External service

**Warning**: Adds JavaScript and complexity

---

## 🆘 Troubleshooting

### Site Not Building

**Check**:
1. `_config.yml` is valid YAML (no syntax errors)
2. All posts have correct front matter
3. No future dates in posts
4. Posts are in `_posts/` folder

**Test locally**:
```bash
bundle install
bundle exec jekyll build
```

### Custom Domain Not Working

**Check**:
1. DNS records are correct
2. Wait 24 hours for propagation
3. HTTPS is enabled
4. Clear browser cache

### Posts Not Showing

**Check**:
1. Filename format: `YYYY-MM-DD-title.md`
2. Date is not in the future
3. Front matter is correct
4. File is in `_posts/` directory

### Prose.io Not Working

**Check**:
1. Repository is public (or Prose has access to private repos)
2. `_prose.yml` is in repository root
3. You've authorized Prose.io with GitHub

---

## 📚 Next Steps

1. ✅ Configure `_config.yml`
2. ✅ Add custom domain (optional)
3. ✅ Delete example posts
4. ✅ Add your first post
5. ✅ Customize footer
6. ✅ Share your site!

---

## 🆘 Need Help?

- **Documentation**: See [README.md](README.md)
- **Content Guide**: See [CONTENT-GUIDE.md](CONTENT-GUIDE.md)
- **Issues**: [Report an issue](https://github.com/brennanbrown/inkpage/issues)
- **Original Project**: [InkPage on GitHub](https://github.com/brennanbrown/inkpage)

---

**Made your site awesome?** Consider giving the [original project](https://github.com/brennanbrown/inkpage) a ⭐ star on GitHub!
