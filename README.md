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
propositions: [1, 2, 3]      # Optional: List of related propositions
image: /assets/post_images/your_image.png
series: "Series Name"        # Optional: Must match exactly across posts
series_order: 1              # Optional: 1, 2, 3...
---
```

*   **Image:** Place images in `assets/post_images/`.
*   **Taxonomy:** See `TAXONOMY_REFERENCE.md` for approved categories and tags.
*   **Propositions:** List the proposition numbers (e.g., `[17, 19]`) discussed in the post. These will appear on the [Propositions Index](/propositions/). These will also be used to make 'badges' at top of the post.

### Proposition badges (top of post)

If you add a `propositions` array in a post's front matter, the layout will automatically render a small proposition badge near the top of the post header. Example front matter:

```yaml
propositions: [1, 19]
```

The badge is generated in the post layout and styled with the `.proposition-badge` class. Use numeric proposition identifiers only; the layout will format and display them for you.

### Feature callout / Feature grid

Use the `feature-callout` wrapper with the `feature-grid` list to present long lists in a compact, two-column layout that collapses to one column on small screens. Example (paste into the post where you want the list):

```html
<div class="feature-callout">
  <ul class="feature-grid">
    <li>First compact item</li>
    <li>Second compact item</li>
    <li>Third compact item</li>
    <!-- more items -->
  </ul>
</div>
```

Notes:
- The grid is responsive (switches to one column below ~700px).
- Items are styled via `.feature-grid li` (smaller font, reduced padding) to keep long lists compact and scannable.
- If you prefer larger spacing, edit `assets/custom.scss` or wrap with your own utility class.

### Image utilities (quick floats)

If you prefer simple inline images instead of the include, you can add one of these CSS utility classes to an `<img>` tag or use kramdown attribute lists.

Examples:

HTML:
```html
<img src="/assets/post_images/mary_and_thrones.png" alt="Mary and the thrones" class="image-left" width="250">
<img src="/assets/post_images/zechariah_and_baby_john.png" alt="Zechariah" class="image-right" width="250">
<img src="/assets/post_images/large.png" alt="Large" class="image-block" width="700">
```

kramdown shorthand:
```markdown
![Mary and the thrones](/assets/post_images/mary_and_thrones.png){:.image-left width=250}
```

Notes:
- `.image-left` and `.image-right` float the image with sensible margins and collapse to block on small screens.
- `.image-block` centers the image.
- These utilities are defined in `assets/custom.scss`.

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
Use this to style Bible verses green. **Do not use the `>` blockquote symbol.**

```html
<span class="scripture">“Repent, for the kingdom of heaven is at hand.”</span>
```

### 4. Peters' Quotes
Use this wrapper for quotes specifically from George N. H. Peters.

```html
<div class="peters-quote">
  “The Kingdom of God is the Kingdom of the Messiah...”
  <br>— <em>Prop. 22, Obs. 1</em>
</div>
```

>**Note:** Markdown is enabled by default inside `.peters-quote` divs (configured in `_config.yml`), so you don't need to add `markdown="1"`. If you want to disable it for a specific div, you can add `markdown="0"`.

```html
<div class="peters-quote" markdown="0">
  “The **Kingdom of God** is the Kingdom of the Messiah...”
  <br>— <em>Prop. 22, Obs. 1</em>
</div>
```

### 5. General Blockquotes
Use standard Markdown blockquotes for other theologians (e.g., Walvoord, Woods). These have a simple gray border.

```markdown
> “This is a quote from a general theologian.”
```

### 6. Post Series
To link posts together in a series (e.g., "The Kingdom Announcement"):
1.  Add `series: "Exact Series Name"` to the front matter of all related posts.
2.  Add `series_order: 1` (or 2, 3, etc.) to define the sequence.
3.  A navigation box will automatically appear at the top of the post.

### 7. Callouts (include)

There is a reusable callout include at `_includes/callout.html` for short sidebars, notes, tips, and warnings. It supports parameters: `type` (note|info|tip|warning|danger), `title`, `id`, `icon`, `classes`, `collapsible` (true|false), and `open`.

Examples:

- Non-collapsible note:

  `{% include callout.html type="note" title="Heads up" content=your_variable_or_string %}`

- Collapsible warning (native `<details>`):

  `{% include callout.html type="warning" title="More on supersessionism" content=supersessionism collapsible=true %}`

- Capture long content then include:

  `{% capture body %}Long markdown content...{% endcapture %}`
  `{% include callout.html type="tip" title="Quick tip" content=body %}`

Notes:

- `type` sets color + default icon; `icon` overrides the icon.  
- `collapsible=true` uses a native `<details>` element (accessible without JS). An optional `assets/callout.js` enhancer can be added for animated open/close.

### 8. Compact Tables

To make wide or dense tables visually smaller, add the `.compact-table` class using a kramdown attribute list. Place the attribute list on the line immediately after the table:

```markdown
| Col A | Col B | Col C |
| ----- | ----- | ----- |
| a     | b     | c     |
{: .compact-table}
```

The `.compact-table` rules are defined in `assets/custom.scss` and reduce padding and font-size for dense tabular data.

---

## Deployment
The site is hosted on GitHub Pages. Pushing to the `main` branch will automatically trigger a build and deployment.
