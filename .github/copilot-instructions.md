# Copilot Instructions - UX Portfolio (Eleventy)

## Project Overview

This is an Eleventy (11ty) static site generator project for a UX consultant portfolio. The architecture emphasizes accessibility (WCAG 2.1 AA), semantic HTML, and clean separation between content (markdown), templates (Nunjucks), and styling.

## Architecture & File Structure

- **`src/`** - All source files; Eleventy compiles these to `_site/`
- **`src/_includes/`** - Nunjucks layout templates
  - `base.njk` - Main layout with navigation, header, footer (used by all pages)
  - `case-study.njk` - Template for individual case study pages
- **`src/case-studies/*.md`** - Markdown case study content files
- **`src/*.njk`** - Top-level pages (index, about, contact, experience, case-studies)
- **`.eleventy.js`** - Configuration file defining collections, filters, and build settings

## Key Conventions

### Case Study Pattern

Case studies are the core content type. Each markdown file in `src/case-studies/` uses this frontmatter structure:

```yaml
---
layout: case-study.njk
title: Project Title
client: Client Name
description: Brief description (shown in listings)
order: 1                    # Controls display order (lower = earlier)
heroImage: /images/hero.png # Optional
heroImageAlt: Alt text      # Optional
tags:                       # Optional
  - Tag 1
  - Tag 2
---
```

The `order` field is critical - it determines sort order in the `caseStudies` collection (defined in [.eleventy.js](.eleventy.js#L9-L12)).

### Collections

The `caseStudies` collection (`.eleventy.js`) automatically includes all markdown files matching `src/case-studies/*.md` and sorts by the `order` frontmatter field. Access it in templates via `collections.caseStudies`.

### Template Layouts

Files specify their layout via frontmatter `layout: base.njk`. The layout wraps the page content in `{{ content | safe }}`. Nested layouts work (e.g., `case-study.njk` extends `base.njk`).

### Navigation Active States

Navigation in [src/_includes/base.njk](src/_includes/base.njk#L23-L27) uses `page.url` to set `aria-current="page"` on the active link. When creating new pages, follow this pattern for accessibility.

### Accessibility Requirements

**All code must meet WCAG 2.1 AA standard.** This is a non-negotiable requirement:
- Always include skip links (`<a href="#main-content" class="skip-link">`)
- Use semantic HTML (`<article>`, `<section role="...">`, etc.)
- Provide `aria-label` or `aria-labelledby` on all sections
- Add descriptive `aria-label` on links like "Read more" (e.g., `aria-label="Read case study about {{ study.data.title }}"`)
- Images require meaningful alt text (never leave `alt=""`)
- Ensure sufficient color contrast ratios (4.5:1 for normal text, 3:1 for large text)
- Support keyboard navigation for all interactive elements

## Development Workflow

### Running the Development Server

```bash
npm start
```

Starts Eleventy with live reload at `http://localhost:8080`. Changes trigger automatic rebuilds.

### Building for Production

```bash
npm run build
```

Outputs to `_site/` directory. This folder is git-ignored and should not be edited directly.

### Deployment

Site is deployed on **Netlify** with automatic deployments from the `main` branch. The build command is `npm run build` and the publish directory is `_site/`. Netlify automatically rebuilds on every push to main.

### Adding a New Case Study

1. Create a new markdown file in `src/case-studies/` (e.g., `new-project.md`)
2. Add frontmatter with required fields: `layout`, `title`, `client`, `description`, `order`
3. Write content in markdown below the frontmatter
4. The case study will automatically appear in:
   - `/case-studies/` listing page
   - Homepage featured section (first 3 by `order`)

### Adding New Pages

1. Create a `.njk` file in `src/` (e.g., `services.njk`)
2. Add frontmatter: `layout: base.njk`, `title`, `description`
3. Manually add navigation link to [src/_includes/base.njk](src/_includes/base.njk#L23-L27)

## Static Assets

Assets in `src/css/`, `src/images/`, and `src/js/` are copied directly to `_site/` via `addPassthroughCopy` in [.eleventy.js](.eleventy.js#L2-L4). Reference them with root-relative paths: `/css/style.css`, `/images/logo.png`.

## Custom Filters (Eleventy)

Available in templates ([.eleventy.js](.eleventy.js#L16-L32)):
- `readableDate` - Formats dates as "Month Day, Year"
- `excerpt` - Truncates content to 200 characters
- `limit` - Limits array length (e.g., `collections.caseStudies | limit(3)`)

## CSS Architecture

All styles are in [src/css/style.css](src/css/style.css) - a single-file approach using:
- CSS custom properties for theming
- Mobile-first responsive design
- Accessibility features (high contrast mode, reduced motion)

## Reusable Components

### Captioned Image Component

For adding images with captions in case studies, use the `captionedImage` macro from [src/_includes/captioned-image.njk](src/_includes/captioned-image.njk). Based on the NHS Design System image component pattern.

**Usage in case study markdown files:**

```markdown
{% from "captioned-image.njk" import captionedImage %}

{{ captionedImage({
  src: "/images/project-screenshot.png",
  alt: "Detailed description for screen readers",
  caption: "Brief explanation of what to conclude from the image."
}) }}
```

**Guidelines:**
- Alt text must describe the image content for screen readers
- Captions should be full sentences ending with a full stop
- Keep captions short (1-2 sentences max)
- Don't duplicate alt text in the caption
- Use captions to explain what users should conclude from the image

## Common Tasks

**Update contact info**: Edit footer in [src/_includes/base.njk](src/_includes/base.njk) and [src/contact.njk](src/contact.njk)

**Change homepage intro**: Edit [src/index.njk](src/index.njk)

**Modify case study template**: Edit [src/_includes/case-study.njk](src/_includes/case-study.njk)

**Reorder case studies**: Adjust the `order` field in frontmatter (lower numbers appear first)
