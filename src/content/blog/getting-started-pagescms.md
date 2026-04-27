---
title: 'Getting Started with PagesCMS'
description: 'Learn how PagesCMS makes content management simple by editing files directly in your GitHub repository.'
pubDate: 'Apr 20 2026'
heroImage: '../../assets/blog-placeholder-1.jpg'
---

PagesCMS is an open-source content management system that works differently from traditional CMS platforms. Instead of storing your content in a database, it edits files directly in your GitHub repository.

## Why PagesCMS?

Most static sites already have everything they need:

- Content lives in files (Markdown, MDX, YAML)
- Media is stored in the repository
- Git provides version history
- CI/CD handles deployments

The missing piece has always been the editing experience. PagesCMS fills that gap by providing a clean, intuitive UI for editing content without requiring every team member to learn Git.

## How It Works

1. **Add a `.pages.yml` config** to your repository
2. **Define your content structure** — collections, fields, media paths
3. **Sign in** at app.pagescms.org with GitHub
4. **Start editing** — changes are committed directly to your repo

## Key Features

### Visual Rich-Text Editor
Write and format content with a full-featured rich-text editor. No need to write Markdown manually unless you want to.

### Media Management
Upload images through a drag-and-drop interface. PagesCMS organizes them in your configured media folder.

### Customizable Content Types
Define collections with any combination of fields — strings, dates, images, rich text, code blocks, and more.

### Git-Native Workflow
Every save is a Git commit. Your existing deployment pipeline picks up changes automatically.

## Configuration Example

Here's a minimal `.pages.yml` configuration:

```yaml
media: media
content:
  - name: posts
    label: Blog Posts
    type: collection
    path: src/content/blog
    fields:
      - name: title
        type: string
      - name: body
        type: rich-text
```

This creates one collection for blog posts with a title and rich-text body.

## Getting Your Team Onboard

PagesCMS supports GitHub-based authentication, so anyone with access to your repository can edit content. You can also configure granular permissions through the collaborators settings.

The best part? No training required. If someone can use a word processor, they can use PagesCMS.
