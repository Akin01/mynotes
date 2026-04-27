---
title: 'Building a Blog with Astro and PagesCMS'
description: 'A step-by-step walkthrough of creating a modern, fast blog with Astro and managing content through PagesCMS.'
pubDate: 'Apr 10 2026'
heroImage: '../../assets/blog-placeholder-3.jpg'
---

Astro has quickly become one of the most popular static site generators, and for good reason. Combined with PagesCMS for content management, you get a blog that is fast, easy to maintain, and a joy to write for.

## The Stack

- **Astro v6** — Static site generator with zero-JS-by-default philosophy
- **PagesCMS** — Git-based CMS with a beautiful editing UI
- **Markdown/MDX** — Content format with frontmatter metadata
- **GitHub** — Version control and collaboration
- **Vercel/Netlify** — Automatic deployments from Git

## Project Structure

```
blog/
├── .pages.yml              # PagesCMS configuration
├── src/
│   ├── content/
│   │   └── blog/           # Blog posts (Markdown)
│   ├── pages/              # Route pages
│   ├── components/         # Reusable UI components
│   └── layouts/            # Page layouts
├── public/
│   └── images/             # Static assets & uploaded media
└── astro.config.mjs        # Astro configuration
```

## Setting Up Content Collections

Astro uses content collections to organize and validate your content. Each collection has a schema defined with Zod:

```typescript
const blog = defineCollection({
  loader: glob({ base: './src/content/blog', pattern: '**/*.{md,mdx}' }),
  schema: ({ image }) =>
    z.object({
      title: z.string(),
      description: z.string(),
      pubDate: z.coerce.date(),
      updatedDate: z.coerce.date().optional(),
      heroImage: z.optional(image()),
    }),
});
```

## Configuring PagesCMS

The `.pages.yml` file maps PagesCMS fields to your content schema. Each field type (string, date, image, rich-text) corresponds to what PagesCMS renders in its editing interface:

```yaml
content:
  - name: posts
    label: Blog Posts
    type: collection
    path: src/content/blog
    fields:
      - name: title
        type: string
      - name: description
        type: text
      - name: pubDate
        type: date
      - name: heroImage
        type: image
      - name: body
        type: rich-text
```

## The Editing Workflow

1. Open your repo in PagesCMS
2. Click "New Post" in the blog collection
3. Fill in title, description, date, and upload a hero image
4. Write your content in the rich-text editor
5. Click Save — PagesCMS commits the new Markdown file to your repo
6. Your deployment platform detects the commit and rebuilds the site
7. The new post is live within minutes

## Why This Combination Works

Astro handles the heavy lifting of building a fast, optimized static site. PagesCMS handles the content editing experience. Neither gets in the way of the other.

The result: developers can focus on the site design and functionality, while content creators get a friendly editing interface. Everyone wins.
