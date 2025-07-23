# Design Document

## Overview

The sathyabh.at blog is a Hugo-based static site that serves as Sathyajith Bhat's personal publishing platform. The architecture follows Hugo's standard conventions with custom configurations optimized for a personal blog with regular weekly content, travelogues, and technical posts. The site leverages the Congo theme with extensive customizations for appearance, navigation, and content organization.

## Architecture

### Site Structure
```
sathyabh.at/
├── config/
│   └── _default/
│       ├── config.toml      # Core Hugo configuration
│       ├── params.toml      # Theme and display parameters
│       └── menus.en.toml    # Navigation structure
├── content/
│   ├── weekly-notes/        # Organized by year/week
│   ├── about/               # Static pages
│   ├── subscribe/
│   └── [legacy-posts].md    # Historical WordPress content
├── layouts/                 # Custom theme overrides
├── static/                  # Static assets
├── assets/                  # Processed assets
└── public/                  # Generated site output
```

### Content Organization Strategy
- **Weekly Notes**: Hierarchical structure (`/weekly-notes/YYYY/WW/`)
- **Travelogues**: Individual directories with associated media
- **Legacy Content**: Preserved original WordPress URL structure
- **Static Pages**: Direct content directory placement

### Theme Integration
- **Base Theme**: Congo Hugo theme
- **Customizations**: Avocado color scheme, dark mode default
- **Layout**: Hybrid header, custom homepage, enhanced article display

## Components and Interfaces

### Content Management Components

#### Weekly Notes Template System
```markdown
# Template Structure
- Frontmatter with standardized fields
- Predefined content sections
- Consistent URL pattern
- Series association
- Image and summary requirements
```

#### Taxonomy System
- **Categories**: High-level content classification (Life, Travel, Tech)
- **Tags**: Granular content labeling
- **Places**: Geographic content organization
- **Series**: Sequential content grouping (Weekly notes, etc.)

#### Media Integration
- **Custom Shortcodes**: fbgallery, fancybox for image galleries
- **External Embeds**: YouTube, Strava activity integration
- **Image Management**: Responsive images with captions

### Navigation Components

#### Primary Navigation
- Home, About, Setup pages
- External tech blog link
- Subscription management
- Content discovery (Wot I Read)

#### Footer Navigation
- Content type browsing (Weekly Notes, Travelogues)
- Taxonomy access (Categories, Tags, Places)
- Archive functionality

### Build and Deployment Components

#### Hugo Build Process
- Static site generation from Markdown
- Asset processing and optimization
- RSS feed generation (site-wide and series-specific)
- Sitemap creation with exclusions

#### Netlify Integration
- Automated deployment on Git push
- Hugo version pinning (0.91.2)
- Build environment configuration
- CDN distribution

## Data Models

### Content Frontmatter Schema
```yaml
# Standard Post Schema
author: string
categories: array[string]
tags: array[string]
places: string|array[string]
type: string
series: array[string]
url: string
title: string
date: datetime
summary: string
images: array[string]
draft: boolean
```

### Weekly Notes Specific Schema
```yaml
# Weekly Notes Extension
url: "/weekly-notes-{week}-{year}/"
title: "Weekly notes {week}/{year}"
series: ["Weekly notes"]
categories: ["Life"]
tags: ["weekly-notes", ...]
places: string (current location)
```

### Site Configuration Model
```toml
# Core Configuration
baseurl: string
title: string
theme: string
languageCode: string
paginate: integer
enableRobotsTXT: boolean
enableEmoji: boolean
enableGitInfo: boolean
googleAnalytics: string
```

## Error Handling

### Build-Time Error Management
- **Invalid Frontmatter**: Hugo build fails with descriptive errors
- **Missing Templates**: Fallback to theme defaults
- **Asset Processing**: Graceful degradation for missing images
- **URL Conflicts**: Hugo's built-in duplicate detection

### Runtime Error Handling
- **404 Pages**: Theme-provided error pages
- **Missing Images**: Alt text fallbacks
- **External Embed Failures**: Graceful degradation
- **RSS Feed Issues**: Hugo's built-in error handling

### Deployment Error Recovery
- **Build Failures**: Netlify maintains previous successful deployment
- **Configuration Errors**: Build logs provide debugging information
- **Asset Pipeline Issues**: Incremental build recovery

## Testing Strategy

### Content Validation
- **Frontmatter Validation**: Hugo's built-in schema checking
- **Link Validation**: Manual review process for external links
- **Image Validation**: Build-time asset verification
- **URL Structure**: Consistent pattern enforcement

### Build Testing
- **Local Development**: Hugo server with live reload
- **Staging Builds**: Netlify deploy previews for pull requests
- **Production Validation**: Post-deployment smoke testing
- **Performance Testing**: Lighthouse audits for static site performance

### Content Quality Assurance
- **Template Consistency**: Weekly notes template adherence
- **SEO Validation**: Meta tag and structured data verification
- **Accessibility**: Basic WCAG compliance through theme
- **Mobile Responsiveness**: Theme-provided responsive design

### Integration Testing
- **RSS Feed Validation**: Feed reader compatibility testing
- **Social Sharing**: Meta tag validation for social platforms
- **Analytics Integration**: Google Analytics event tracking
- **Search Functionality**: Built-in search feature validation

### Backup and Recovery
- **Git Repository**: Complete site source control
- **Netlify Deployment History**: Rollback capability
- **Asset Backup**: External image hosting on i.sathyabh.at
- **Configuration Backup**: Version-controlled configuration files