# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## About

This is a Hugo static site blog (sathyabh.at) using the Congo theme. The site is deployed on Netlify and Fly.io.

## Architecture

- **Hugo Static Site Generator**: Uses Hugo v0.91.2+ to generate static HTML from markdown content
- **Congo Theme**: Located in `themes/congo/` directory with extensive customization options
- **Content Structure**: 
  - Blog posts in `content/` directory with date-based filename format
  - Weekly notes in `content/weekly-notes/` subdirectory
  - Special pages like About, Subscribe in their own subdirectories
- **Configuration**: Hugo config split across `config/_default/` directory
- **Generated Content**: `public/` directory contains the built static site

## Common Commands

Since this is a Hugo site, typical commands would be:

```bash
# Development server (if Hugo is installed)
hugo server

# Build static site
hugo

# Get weekly notes (custom script)
./get_weekly_notes.sh
```

## Deployment

- **Netlify**: Configured in `netlify.toml` with Hugo v0.91.2

## Content Management

- Blog posts use date-based naming: `YYYY-MM-DD-title.md`
- Weekly notes follow pattern: `weekly-notes-XX-YYYY/index.md`
- Uses Hugo's front matter for metadata (title, date, tags, etc.)
- Images and assets stored in post directories or `assets/` directory

## Theme Configuration

The Congo theme provides extensive customization through:
- `config/_default/params.toml` for theme parameters
- `config/_default/menus.en.toml` for navigation
- Custom layouts in `layouts/` directory
- Theme supports multiple color schemes and layouts

## Custom Shortcodes

### fancybox

Creates a single image with Fancybox lightbox functionality.

**Basic Usage:**
```markdown
{{< fancybox "https://i.sathyabh.at/sb/2023/04" "image.jpg" "Image Caption" "Gallery Name" >}}
```

**Named Parameters:**
```markdown
{{< fancybox path="https://i.sathyabh.at/sb/2023/04" file="image.jpg" caption="Image Caption" gallery="Gallery Name" >}}
```

**Using Date Path (resolves to `/img/YYYY/MM`):**
```markdown
{{< fancybox "date" "image.jpg" "Image Caption" "Gallery Name" >}}
```

**Parameters:**
- First parameter (path): Image path (can be URL or "date" for auto-resolution)
- Second parameter (file): Image filename
- Third parameter (caption): Image caption (optional)
- Fourth parameter (gallery): Gallery name for grouping (default: "gallery" if omitted)

### fbgallery

Creates a Fancybox gallery with masonry layout from multiple images.

**Basic Usage:**
```markdown
{{< fbgallery "https://i.sathyabh.at/sb/weekly-notes" "gallery" "image1.jpg" "image2.jpg" "image3.jpg" >}}
```

**With Captions:**
```markdown
{{< fbgallery "https://i.sathyabh.at/sb/weekly-notes" "gallery" "image1.jpg|Caption 1" "image2.jpg|Caption 2" "image3.jpg|Caption 3" >}}
```

**Using Date Path (resolves to `/img/YYYY/MM`):**
```markdown
{{< fbgallery "date" "gallery" "image1.jpg" "image2.jpg" "image3.jpg" >}}
```

**With Custom Gallery Name:**
```markdown
{{< fbgallery "https://i.sathyabh.at/sb/weekly-notes" "My Custom Gallery" "image1.jpg" "image2.jpg" "image3.jpg" >}}
```

**Parameters:**
- First parameter: Image path (can be URL or "date" for auto-resolution)
- Second parameter: Gallery name for Fancybox grouping (default: "gallery" if omitted)
- Remaining parameters: Image filenames, optionally with captions using `|` separator