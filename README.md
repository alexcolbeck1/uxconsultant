# UX Consultant Portfolio

A fully accessible Eleventy-based portfolio site for showcasing UX and interaction design work.

## Features

- ✅ Fully accessible (WCAG 2.1 AA compliant)
- ✅ Responsive design
- ✅ 6 case study examples included
- ✅ Skip links for screen readers
- ✅ High contrast mode support
- ✅ Reduced motion support
- ✅ Keyboard navigation
- ✅ Semantic HTML

## Getting Started

### Install Dependencies

```bash
npm install
```

### Run Local Development Server

```bash
npm start
```

This will start the development server at `http://localhost:8080`. The site will automatically rebuild when you make changes.

### Build for Production

```bash
npm run build
```

This creates a `_site` directory with your built site.

## Project Structure

```
uxconsultant/
├── src/
│   ├── _layouts/          # Page templates
│   │   ├── base.njk       # Base layout with navigation
│   │   └── case-study.njk # Case study template
│   ├── case-studies/      # Case study markdown files
│   │   ├── ecommerce-checkout.md
│   │   ├── healthcare-portal.md
│   │   ├── banking-app.md
│   │   ├── education-platform.md
│   │   ├── travel-booking.md
│   │   └── design-system.md
│   ├── css/
│   │   └── style.css      # All styles
│   ├── images/            # Place your images here
│   ├── index.njk          # Homepage
│   ├── about.njk          # About page
│   ├── case-studies.njk   # Case studies listing
│   └── contact.njk        # Contact page
├── .eleventy.js           # Eleventy configuration
├── package.json
└── README.md
```

## Customization

### Update Your Information

1. **Contact Details**: Edit `src/contact.njk` and the footer in `src/_layouts/base.njk`
2. **About Page**: Edit `src/about.njk` with your background and skills
3. **Homepage**: Customize `src/index.njk` with your services and intro

### Add Your Case Studies

Case studies are in `src/case-studies/` as Markdown files. Each file has front matter with:

```yaml
---
layout: case-study.njk
title: Your Project Title
client: Client Name
description: Brief description
date: 2024-01-01
order: 1
tags: 
  - Tag 1
  - Tag 2
---
```

The `order` field controls the display order. Edit the existing files or create new ones following the same structure.

### Styling

All styles are in `src/css/style.css`. The CSS includes:

- CSS custom properties for easy theming
- Responsive design
- Accessibility features (focus states, high contrast support, etc.)
- Print styles

### Add Images

1. Place images in `src/images/`
2. Reference them in your markdown: `![Alt text](/images/your-image.jpg)`
3. Always include descriptive alt text for accessibility

## Accessibility Features

This site is built with accessibility in mind:

- **Skip Links**: Allows keyboard users to jump to main content
- **Semantic HTML**: Proper heading hierarchy and landmarks
- **ARIA Labels**: Where needed for screen readers
- **Keyboard Navigation**: All interactive elements are keyboard accessible
- **Focus Indicators**: Clear focus states for keyboard users
- **Color Contrast**: All text meets WCAG AA standards
- **Responsive**: Works on all screen sizes
- **Reduced Motion**: Respects user's motion preferences

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Deployment

You can deploy the `_site` folder to any static hosting service:

- **Netlify**: Connect your Git repo and it will auto-deploy
- **Vercel**: Similar to Netlify
- **GitHub Pages**: Use GitHub Actions to build and deploy
- **Any static host**: Just upload the `_site` folder

## License

MIT License - feel free to use this as a template for your own portfolio!