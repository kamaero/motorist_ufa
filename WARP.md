# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview
This is a static website for МОТОРИСТ УФА (Motorist Ufa), a motor repair service business in Bashkortostan, Russia. The site is a single-page landing page built with vanilla HTML, CSS, and JavaScript.

## Repository Structure
- `index.html` - Primary landing page (root level)
- `motorist-ufa.ru/html/` - Production version of the site with enhanced SEO
  - `index.html` - Production landing page with structured data and comprehensive meta tags
  - `robots.txt` - Search engine crawler directives
  - `sitemap.xml` - XML sitemap for search engines
- `motorist-ufa.ru/images/` - Service photos and assets (.webp, .jpg, .jpeg formats)
- `html/` - Simple placeholder HTML file
- `.gigaide/` - AI assistant artifacts (not for deployment)

## Key Architectural Details

### HTML Structure
Both HTML files are self-contained single-page applications with:
- **Inline CSS**: All styles embedded in `<style>` tags (no external stylesheets)
- **Inline JavaScript**: Interactive features (mobile menu, smooth scrolling, scroll animations) in `<script>` tags
- **External dependency**: Font Awesome CDN for icons

### Two versions of the site
1. **Root `index.html`**: Simpler version with basic meta tags, uses Unsplash images
2. **`motorist-ufa.ru/html/index.html`**: Production version with:
   - Comprehensive SEO meta tags (Open Graph, Twitter Card, geo-location)
   - JSON-LD structured data for search engines
   - Local images from `/images` directory
   - Canonical URL and alternate language tags

### Page Sections
- Header with sticky navigation
- Hero section with background image
- About section with statistics grid
- Services section with card layout
- Contacts section with Yandex Maps iframe and Telegram bot integration
- Footer with company info and links

### Responsive Design
- CSS Grid and Flexbox layout
- Mobile-first responsive breakpoints: 992px, 768px, 480px
- Mobile hamburger menu toggle

### Contact Information
- **Phones**: +7 (917) 737-40-40, +7 (917) 388-89-11
- **Email**: motorist.ufa@mail.ru
- **Telegram Bot**: @motorist_ufa_bot
- **Website**: www.motorist-ufa.ru
- **Location**: Республика Башкортостан, Уфимский район, село Зубово

## Common Tasks

### Testing the site locally
```bash
# Open in browser directly
open index.html

# Or serve with Python HTTP server
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### Validating HTML
```bash
# If you have html5validator installed
html5validator index.html motorist-ufa.ru/html/index.html
```

### Optimizing images
Images should be in modern formats (WebP preferred) and optimized for web:
- Service images in `motorist-ufa.ru/images/` are already in .webp and .jpg formats
- Keep file sizes reasonable for web loading

### SEO Updates
When updating SEO metadata, ensure changes are made to:
- `<title>` tag
- `<meta name="description">` 
- Open Graph tags (`og:*`)
- Twitter Card tags
- JSON-LD structured data
- `sitemap.xml` lastmod dates
- Canonical URL if domain changes

### Deployment
This is a static site. Deployment typically involves:
1. Copy files to web server (likely Nginx based on `index.nginx-debian.html`)
2. Ensure proper file permissions
3. Point web server to `motorist-ufa.ru/html/` directory
4. Verify robots.txt and sitemap.xml are accessible

## Version Control
- **Main branch**: `main`
- Recent commits focus on SEO improvements and content updates
- The site is maintained by Булат (Bulat) based on commit messages
