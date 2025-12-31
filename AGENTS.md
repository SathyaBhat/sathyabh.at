# AGENTS.md

Commands and workflows for working with this repository in Amp.

## Quick Commands

### Development Server
```bash
hugo server
```
Starts the local development server with live reload. The site will be available at `http://localhost:1313/`.

### Build Static Site
```bash
hugo
```
Builds the static site and outputs to the `public/` directory for deployment.

### Clean Build
```bash
rm -rf public/ && hugo
```
Removes the previous build and creates a fresh build of the site.

## Content Workflows

### Creating a Blog Post
1. Create a new markdown file in `content/` with the format: `YYYY-MM-DD-title.md`
2. Add front matter with title, date, tags, and description
3. Example path: `content/2025-12-28-my-post.md`

### Creating a Weekly Note
1. Create a directory in `content/weekly-notes/` with the pattern: `weekly-notes-XX-YYYY/` (where XX is the week number)
2. Create an `index.md` file inside with front matter and content
3. Example path: `content/weekly-notes/weekly-notes-52-2025/index.md`

### Adding Images to Posts
1. Store images in the post's directory or in `assets/`
2. Reference using Hugo's image syntax: `![alt text](image.jpg)`
3. For Fancybox lightbox: Use `{{< fancybox "path" "image.jpg" "caption" "gallery" >}}`
4. For galleries: Use `{{< fbgallery "path" "gallery" "image1.jpg" "image2.jpg" >}}`

## Custom Shortcodes

### fancybox - Single Image Lightbox
```markdown
{{< fancybox "https://i.sathyabh.at/sb/2023/04" "image.jpg" "Image Caption" "Gallery Name" >}}
```
Or with named parameters:
```markdown
{{< fancybox path="https://i.sathyabh.at/sb/2023/04" file="image.jpg" caption="Image Caption" gallery="Gallery Name" >}}
```
Use `"date"` as the path to auto-resolve to current date's image directory `/img/YYYY/MM`.

### fbgallery - Masonry Gallery with Lightbox
```markdown
{{< fbgallery "https://i.sathyabh.at/sb/weekly-notes" "gallery" "image1.jpg" "image2.jpg" "image3.jpg" >}}
```
With captions (use `|` separator):
```markdown
{{< fbgallery "https://i.sathyabh.at/sb/weekly-notes" "gallery" "image1.jpg|Caption 1" "image2.jpg|Caption 2" >}}
```

## Configuration

### Theme Configuration
- Theme parameters: `config/_default/params.toml`
- Navigation menu: `config/_default/menus.en.toml`
- Custom layouts: `layouts/` directory
- Congo theme supports multiple color schemes

### Hugo Configuration
- Hugo version: `0.91.2` (set in `netlify.toml`)
- Config split across: `config/_default/` directory
- Main configuration typically in `config/_default/config.toml`

## Deployment

### Netlify
- Configured in `netlify.toml` with Hugo v0.91.2
- Automatically builds and deploys on push to main branch
- Runs image compression workflow on PNG/WebP changes

### GitHub Actions
- **Image Compression**: Automatically runs on pull requests when PNG/WebP files are added/changed
- Workflow file: `.github/workflows/optimze-images.yaml`

## File Structure

```
.
├── content/              # Blog posts and pages
├── content/weekly-notes/ # Weekly notes
├── themes/congo/         # Congo theme (git submodule)
├── layouts/              # Custom layouts
├── config/               # Hugo configuration
├── assets/               # Images and static assets
├── public/               # Generated static site (build output)
├── static/               # Static files
└── netlify.toml          # Netlify deployment config
```

## Common Tasks

### Preview a Post Before Publishing
1. Set `draft: true` in the front matter
2. Run `hugo server -D` to include draft posts
3. When ready to publish, set `draft: false` and push

### Update Theme
The Congo theme is a git submodule. To update:
```bash
git submodule update --remote themes/congo
```

### Check Site for Broken Links
```bash
# Build the site first
hugo

# Then check with a tool like linkchecker (if installed)
linkchecker public/
```

## Front Matter Template

```yaml
---
title: "Post Title"
date: 2025-12-28
description: "Brief description of the post"
tags: ["tag1", "tag2"]
categories: ["category"]
draft: false
---
```

## Notes

- All URLs and image paths should use HTTPS
- Images are typically hosted on `i.sathyabh.at` subdomain
- The `"date"` path parameter in shortcodes automatically resolves to `/img/YYYY/MM` format
- Fancybox and fbgallery provide image lightbox functionality
