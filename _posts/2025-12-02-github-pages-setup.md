---
layout: post
title:  "GitHub Pages Setup Instructions"
date:   2025-12-01 14:00:00 -0500
categories: jekyll update
---

Here are the manual steps required to finish setting up this blog with the custom domain.

### 1. Rename Repository on GitHub
1. Go to the repository on GitHub.
2. Click **Settings**.
3. Change the repository name from `andre-codes.github.io` to `bereans_blog`.

### 2. Configure DNS
Log in to the domain registrar for `bereansblog.com` and update the DNS records:

**A Records** (Point `@` to GitHub's IPs):
* `185.199.108.153`
* `185.199.109.153`
* `185.199.110.153`
* `185.199.111.153`

**CNAME Record**:
* Point `www` to `andre-codes.github.io`.

### 3. Verify CNAME File
Ensure the `CNAME` file in the root of the repository contains exactly:
```
bereansblog.com
```

### 4. Dev Container
Since we are using a Dev Container, we don't need to worry about local Ruby versions or the `vendor/` folder. The container handles the environment for us.
