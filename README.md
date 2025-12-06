# Berean's Blog

This is a Jekyll blog hosted on GitHub Pages, dedicated to the study of *The Theocratic Kingdom* by George N. H. Peters.

## How to Run Locally

This project is configured with a **Dev Container**.

1.  Open this folder in VS Code.
2.  Press `F1` and run **"Dev Containers: Reopen in Container"**.
3.  Once the terminal is ready, run:
    ```bash
    bundle exec jekyll serve
    ```
4.  Open your browser to `http://localhost:4000`.

---

## Creating Content

### 1. Create a Post File
Create a new file in `_posts/` using the format: `YYYY-MM-DD-your-title.md`.

### 2. Front Matter Template
Copy and paste this into the top of your new file:

```yaml
---
layout: post
title:  "Your Post Title"
date:   2025-12-08 12:00:00 -0500
categories: [Category1, Category2]
tags: [Tag1, Tag2]
image: /assets/post_images/your_image.png
series: "Series Name"        # Optional: Must match exactly across posts
series_order: 1              # Optional: 1, 2, 3...
---
```

*   **Image:** Place images in `assets/post_images/`.
*   **Taxonomy:** See `TAXONOMY_REFERENCE.md` for approved categories and tags.

---

## Styling & Features Guide

### 1. Emphasis (Gold Text)
Use this for the **strongest points** of your argument. Do not overuse.

```html
<span class="kingdom-gold">The Kingdom is the central theme of Scripture.</span>
```

### 2. Propositions
Use this wrapper for Peters' propositions.

```html
<div class="proposition">
  <span class="prop-title">Prop. 19</span>
  “The New Testament begins the announcement of the kingdom...”
</div>
```

### 3. Scripture References
Use this to style Bible verses green.

```html
<span class="scripture">“Repent, for the kingdom of heaven is at hand.”</span>
```

### 4. Post Series
To link posts together in a series (e.g., "The Kingdom Announcement"):
1.  Add `series: "Exact Series Name"` to the front matter of all related posts.
2.  Add `series_order: 1` (or 2, 3, etc.) to define the sequence.
3.  A navigation box will automatically appear at the top of the post.

### 5. Blockquotes
Standard Markdown blockquotes are styled with a gold border.

```markdown
> “This is a quote from Peters or a theologian.”
```

---

## Deployment
The site is hosted on GitHub Pages. Pushing to the `main` branch will automatically trigger a build and deployment.
