# PagesCMS Blog

A modern, fast blog built with [Astro](https://astro.build) and managed with [PagesCMS](https://pagescms.org).

## Quick Start

```bash
npm install
npm run dev        # Development server at http://localhost:4321
npm run build      # Production build to dist/
npm run preview    # Preview production build
```

## Project Structure

```
blog/
├── .pages.yml                  # PagesCMS configuration
├── src/
│   ├── content/
│   │   └── blog/               # Blog posts (Markdown with frontmatter)
│   ├── pages/                  # Route pages (index, about, blog listing)
│   ├── components/             # Reusable UI components (Header, Footer)
│   ├── layouts/                # Page layouts (BlogPost)
│   ├── assets/                 # Fonts and images
│   └── styles/                 # Global CSS
├── public/
│   └── images/                 # PagesCMS media uploads
├── astro.config.mjs            # Astro configuration
└── package.json
```

## PagesCMS Integration

This blog is configured for PagesCMS editing. The `.pages.yml` configuration maps to the Astro content schema:

- **Blog Posts** — Editable collection at `src/content/blog/`
  - Title, description, publish date, hero image, rich-text body
- **Pages** — Static pages at `src/content/pages/`
  - Title, description, rich-text body
- **Media** — Uploads go to `public/images/`

### To Start Editing with PagesCMS

1. Push this repository to GitHub
2. Go to [app.pagescms.org](https://app.pagescms.org)
3. Sign in with GitHub
4. Install the PagesCMS GitHub App on your repo
5. Open your repository — PagesCMS will detect `.pages.yml`
6. Start creating and editing content!

### Content Schema

Each blog post uses this frontmatter:

```yaml
title: 'Post Title'
description: 'SEO description'
pubDate: 'Apr 20 2026'
updatedDate: 'Apr 25 2026'  # optional
heroImage: '../../assets/hero.jpg'  # optional
---

Post content in Markdown...
```

## Deployment

Build output is static HTML in `dist/`. Deploy anywhere:

- **Vercel:** Connect GitHub repo, auto-deploys on push
- **Netlify:** Same — Git-based CI/CD
- **Cloudflare Pages:** `npm run build`, output directory `dist`
- **GitHub Pages:** Use the deploy action

## Tech Stack

- **Astro v6** — Static site generator
- **PagesCMS** — Git-based headless CMS
- **Atkinson Hyperlegible** — Accessible typeface
- **Custom CSS** — No framework, minimal footprint
