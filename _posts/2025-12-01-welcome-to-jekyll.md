---
layout: post
title:  "The Ultimate Markdown Showcase"
date:   2025-12-01 12:00:00 -0500
categories: demo markdown
image: /assets/moses_snake.webp
---
Welcome to a demonstration of what is possible with **Markdown** in Jekyll. This post serves as a cheat sheet and a showcase of typography, code formatting, and advanced features.

## 1. Typography & Emphasis

Markdown makes it easy to emphasize text. You can make text **bold**, *italic*, or ***bold and italic***. You can also ~~strikethrough~~ text or highlight `inline code`.

> "Typography is the craft of endowing human language with a durable visual form."
>
> — Robert Bringhurst[^1]

## 2. Lists & Organization

### Unordered Lists
*   Item 1
*   Item 2
    *   Sub-item A
    *   Sub-item B

### Ordered Lists
1.  First step
2.  Second step
3.  Third step

### Task Lists
- [x] Install Jekyll
- [x] Choose a theme
- [ ] Write first post

## 3. Code Syntax Highlighting

Jekyll uses Rouge for syntax highlighting. Here is a Python example:

```python
def hello_world():
    # This is a comment
    print("Hello, World!")
    return True
```

And some JavaScript:

```javascript
const container = document.getElementById('app');
container.innerHTML = '<h1>Hello World</h1>';
```

## 4. Tables

Tables are great for structured data.

| Feature | Support | Notes |
| :--- | :---: | ---: |
| **Bold** | Yes | `**text**` |
| *Italics* | Yes | `*text*` |
| Tables | Yes | GFM Syntax |

## 5. Images

You can easily insert images anywhere in your post.

<img src="/assets/icon.png" alt="Description of image" width="250" style="float: right; margin: 0 0 15px 15px; border-radius: 5px;">

This is an example of how text wraps around an image. By using a simple HTML `img` tag with `float: right`, you can have the image sit nicely alongside your text. This is perfect for author bios, side notes, or just breaking up a wall of text without taking up the full vertical space. The text will naturally flow around the image, creating a more magazine-like layout for your blog posts.

<div style="clear: both;"></div>
*You can also add a caption below it using italics.*

## 6. Scripture Tooltips (BLB ScriptTagger)

We have integrated the **Blue Letter Bible ScriptTagger**. This automatically finds Bible references in your text and creates a hover tooltip with the verse.

Try hovering over these examples:
*   **John 3:16**
*   **Rom 8:28**
*   **Psa 23**
*   **Gen 1:1-3**

You don't need to do anything special; just write the reference (e.g., `John 3:16`) and the script does the rest!

## 7. Advanced Features

### Footnotes & Citations
You can easily add footnotes to your text. For example, did you know that Jekyll was created by Tom Preston-Werner? Citations are rendered as superscripts and linked to the bottom of the page.

### Collapsible Details
<details>
<summary>Click to expand extra info</summary>
<br>
Here is some hidden content that is only visible when you click the arrow. Great for spoilers or technical details!
</details>

---

## References

[^1]: Bringhurst, Robert. *The Elements of Typographic Style*. Hartley & Marks, 1992.
[^2]: GitHub co-founder and creator of Jekyll.
