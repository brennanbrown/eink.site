---
layout: default
title: "Welcome to the E-Ink Reader"
date: 2025-09-25
category: personal
---

# {{ page.title }}

**Date:** {{ page.date | date: "%B %d, %Y" }}  
**Category:** {{ page.category }}

---

## Introduction

Welcome to the E-Ink Speech Reader, a minimalist platform designed specifically for reading speeches and presentations on e-ink devices. This first post demonstrates the format and capabilities of the system.

## Purpose

This reader was built with several key principles:

- **Simplicity**: No JavaScript, minimal CSS, pure content focus
- **Compatibility**: Works on limited e-ink browsers with slow processors
- **Readability**: Maximum contrast, optimal line length, clean typography
- **Portability**: Easy to add content from any device

## How to Use

1. Navigate using the links at the top of each page
2. Browse speeches by date or category
3. All content is static and loads instantly
4. No external dependencies or tracking

## Adding Content

To add your own speeches:

1. Create a new markdown file in the `_posts` directory
2. Name it in the format: `YYYY-MM-DD-title.md`
3. Include front matter with title, date, and category
4. Write your content in standard markdown format
5. Rebuild the site or push to your repository

---

*End of document*
