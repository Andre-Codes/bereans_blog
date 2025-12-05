# Berean's Blog

This is a Jekyll blog hosted on GitHub Pages.

## How to Run Locally (Recommended)

This project is configured with a **Dev Container**. This is the easiest way to run the site without installing Ruby on your Windows machine.

1.  Open this folder in VS Code.
2.  You should see a notification: "Folder contains a Dev Container configuration file. Reopen to develop in a container." Click **Reopen in Container**.
    *   *If you don't see this, press `F1` and run "Dev Containers: Reopen in Container".*
3.  VS Code will build the environment (this takes a few minutes the first time).
4.  Once the terminal is ready, run:
    ```bash
    bundle exec jekyll serve
    ```
5.  Open your browser to `http://localhost:4000`.

## How to Add Posts

1.  Create a new file in `_posts/` named `YYYY-MM-DD-your-title.md`.
2.  Copy the header from an existing post.
3.  Write your content.

## Custom Domain
https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site