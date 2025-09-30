# Content Management Guide for Non-Technical Users

This guide shows you how to add and edit speeches on your e-ink reader website **without using Git or the command line**. Perfect for anyone who just wants to write and publish!

---

## 🌐 Method 1: Prose.io (Recommended - Easiest!)

**Prose.io** is a simple web editor that connects to your GitHub repository. It's like using a blog editor, but your content goes directly to your website.

### Setup (One-Time Only)

1. **Visit**: https://prose.io
2. **Click**: "Authorize on GitHub"
3. **Allow**: Prose.io to access your repositories
4. **Done!** You're ready to write

### Adding a New Speech

1. **Go to**: https://prose.io
2. **Authorize** with GitHub (first time only)
3. **Select your repository** from the list
4. **Navigate to**: `_posts` folder
5. **Click**: The green "New File" button (+ icon)
6. **Name your file**: `YYYY-MM-DD-your-title.md`
   - Example: `2025-09-30-my-amazing-speech.md`
7. **Click the metadata button** (document icon in the right sidebar)
8. **Fill in**:
   - **Title**: "My Amazing Speech"
   - **Date**: 2025-09-30
   - **Category**: business, personal, or technical
   - **Layout**: default (this should be pre-filled)
9. **Write your speech** in the main editor (use the toolbar for formatting)
10. **Click**: "Save" (the disk icon) or press Ctrl/Cmd + S
11. **Enter a commit message**: "Add new speech about X"
12. **Click**: "Commit" button

**That's it!** Your speech will appear on your website in about 1-2 minutes.

### Editing an Existing Speech

1. **Go to**: https://prose.io
2. **Select your repository**
3. **Navigate to**: `_posts` folder
4. **Click on**: The file you want to edit
5. **Make your changes** in the editor
6. **Save and commit** with a message like "Updated speech title"

### Prose.io Tips

- ✅ Use the **formatting toolbar** for headers, lists, and links
- ✅ **Preview** your changes with the eye icon
- ✅ **Auto-save** works if you enable it in settings
- ✅ Works on **mobile browsers** too!

---

## 📝 Method 2: GitHub Web Interface (No Extra Tools)

GitHub has a built-in editor that works great for simple edits.

### Adding a New Speech

1. **Go to**: Your repository on GitHub
2. **Click**: `_posts` folder
3. **Click**: "Add file" → "Create new file"
4. **Name your file**: `YYYY-MM-DD-your-title.md`
5. **Add the front matter** at the top:

```markdown
---
layout: default
title: "Your Speech Title"
date: 2025-09-30
category: personal
---

# Your Speech Title

**Date:** September 30, 2025  
**Category:** Personal

Your speech content goes here...

---

*End of document*
```

6. **Scroll down** to "Commit new file"
7. **Enter a description**: "Add new speech"
8. **Click**: "Commit new file"

### Editing an Existing Speech

1. **Go to**: Your repository's `_posts` folder on GitHub
2. **Click on**: The file you want to edit
3. **Click**: The pencil icon (Edit this file)
4. **Make your changes**
5. **Scroll down** and click "Commit changes"

---

## 📱 Method 3: Mobile Apps

### iOS - Working Copy (Best for iPhone/iPad)

**Download**: [Working Copy](https://workingcopyapp.com/) from App Store

**Setup**:
1. Open Working Copy
2. Clone your repository from GitHub
3. Authenticate with GitHub

**Add/Edit Speeches**:
1. Navigate to `_posts` folder
2. Tap "+" to create new file or tap existing file to edit
3. Write your content
4. Commit → Push to publish

### Android - Markor (Simple Markdown Editor)

**Download**: Markor from Google Play Store

**Setup**:
1. Install a Git client (MGit or Termux)
2. Clone your repository
3. Open Markor and navigate to your repo folder

**Add/Edit Speeches**:
1. Create/edit files in `_posts/` directory
2. Use Git client to commit and push changes

---

## ✍️ Method 4: Any Text Editor + Git Desktop

If you prefer writing on your computer without using the command line:

### Setup

1. **Install**: [GitHub Desktop](https://desktop.github.com/)
2. **Clone**: Your repository from GitHub
3. **Find your local folder**: Usually in `Documents/GitHub/YOUR-REPO`

### Writing Workflow

1. **Open** your favorite text editor (Notepad, TextEdit, VS Code, etc.)
2. **Create a new file** in the `_posts/` folder
3. **Name it**: `YYYY-MM-DD-your-title.md`
4. **Write your speech** (see template below)
5. **Save the file**
6. **Open GitHub Desktop**
7. **Review your changes** in the left sidebar
8. **Enter a commit message** at the bottom
9. **Click**: "Commit to main"
10. **Click**: "Push origin" to publish

---

## 📋 Speech Template

Copy this template whenever you create a new speech:

```markdown
---
layout: default
title: "Your Speech Title Here"
date: YYYY-MM-DD
category: personal
---

# {{ page.title }}

**Date:** {{ page.date | date: "%B %d, %Y" }}  
**Category:** {{ page.category }}

---

## Introduction

Your opening paragraph...

## Main Points

### Point One

Details about your first point...

### Point Two

Details about your second point...

## Conclusion

Your closing thoughts...

---

*End of document*
```

---

## 📅 File Naming Rules

**ALWAYS** use this format: `YYYY-MM-DD-title-with-dashes.md`

✅ **Good Examples**:
- `2025-09-30-quarterly-business-review.md`
- `2025-12-25-holiday-message-to-team.md`
- `2025-01-01-new-years-resolutions.md`

❌ **Bad Examples**:
- `my-speech.md` ← Missing date
- `2025-9-5-speech.md` ← Use 09 and 05 (two digits)
- `2025-09-30 my speech.md` ← No spaces allowed
- `2025/09/30-speech.md` ← No slashes in name

---

## 🎨 Formatting Tips

### Headers
```markdown
# Main Title (H1)
## Section (H2)
### Subsection (H3)
```

### Text Formatting
```markdown
**Bold text**
*Italic text*
```

### Lists
```markdown
- Item one
- Item two
- Item three

1. First point
2. Second point
3. Third point
```

### Links
```markdown
[Link text](https://example.com)
```

### Quotes
```markdown
> This is a blockquote
> - Author Name
```

---

## ⚡ Quick Reference

| Task | Easiest Method |
|------|----------------|
| **First-time user** | Prose.io |
| **Quick edit from phone** | GitHub web interface |
| **Offline writing** | Text editor + GitHub Desktop |
| **Bulk editing** | Clone repo + local editor |

---

## 🆘 Troubleshooting

### My speech isn't showing up

**Check**:
- ✅ File is in `_posts/` folder
- ✅ Filename starts with date: `YYYY-MM-DD-`
- ✅ Front matter is correctly formatted (no typos)
- ✅ Date is not in the future
- ✅ Changes were committed AND pushed

**Wait**: GitHub Pages can take 1-2 minutes to rebuild

### I see an error after committing

**Common causes**:
- ❌ Missing dashes `---` around front matter
- ❌ Quotes not closed properly
- ❌ Invalid date format
- ❌ Missing required fields (title, date, layout)

**Fix**: Edit the file and correct the errors

### I want to delete a speech

1. Navigate to the file on GitHub
2. Click the trash can icon
3. Commit the deletion

Or use Prose.io to delete files directly.

---

## 🎯 Best Practices

1. **Write offline first** - Draft in any editor, then copy to website
2. **Use descriptive filenames** - `2025-09-30-q3-financial-review.md` not `speech.md`
3. **Add good commit messages** - "Add Q3 financial review" not "Update"
4. **Preview before committing** - Use Prose.io's preview feature
5. **Keep categories consistent** - Stick to: business, personal, technical
6. **Date posts accurately** - Use the date you want displayed

---

## 🚀 Ready to Start?

**Option A - Easiest**:  
👉 **[Open Prose.io now](https://prose.io)**

**Option B - Simple**:  
👉 **Go to your GitHub repository and navigate to `_posts` folder**

**Option C - Mobile**:  
👉 **Download Working Copy (iOS) or MGit (Android)**

---

**Questions?** Open an issue on your GitHub repository or check the [original project](https://github.com/brennanbrown/inkpage)

Happy writing! ✨
