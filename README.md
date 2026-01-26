# 🌙 Luna SSG

![Python](https://img.shields.io/badge/python-3.11+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/build-passing-brightgreen.svg)

**Luna SSG** is a lightweight, custom-built static site generator written in Python.

It was designed as a high-performance, developer-friendly alternative to Jekyll. It converts Markdown files into a fully functional HTML website using Liquid templates, with zero Ruby dependencies.

---

## 🚀 Key Features

* **Pure Python Core**: Simple, understandable logic in a single `main.py` engine.
* **Liquid Templating**: Native support for logic-based HTML templates via `python-liquid`.
* **Smart Categorization**: Automatically groups posts into sections (e.g., Blog, Games, Dev) based on `_config.yml`.
* **Intelligent URLs**: Auto-generates clean slugs from titles (or uses custom ones).
* **Template Switching**: Separate layouts for standard posts (with dates) and static pages (like 404 or About).
* **Developer UI**:
  * **Auto-Dark Mode for Code**: Console/Terminal code blocks (`bash`, `sh`) automatically render with a dark theme.
  * **Syntax Highlighting**: Integrated `highlight.js`.
* **GitHub Pages Ready**: Automatically generates `.nojekyll` to bypass Jekyll build limits.

## 🛠️ Tech Stack

* **Engine**: Python 3.x
* **python-liquid**: Templating engine for flexible HTML layouts.
* **python-frontmatter**: For parsing YAML metadata in Markdown files.
* **markdown-it-py**: Fast and CommonMark-compliant Markdown parser (replaces standard `markdown` lib).
* **pyyaml**: For project configuration management.

## ⚙️ Configuration

The site is controlled via `_config.yml`. No code changes required.

```yaml
title: My Awesome Site
theme: mystyle.css

# Navigation Menu
menu:
  - title: Home
    url: /
  - title: GitHub
    url: https://github.com/username

# Content Categories
# 'id' matches the category in your .md files
sections:
  - id: blog
    title: "Latest Thoughts"
  - id: programming
    title: "Dev Logs"
```

## ✍️ Writing Content

Create `.md` files in the `_posts/` directory.

### Frontmatter Options

```yaml
---
title: "My New Post"        # Required
date: 2026-01-26            # Optional (defaults to today)
category: blog              # Matches section ID
slug: my-custom-url         # Optional
published: true             # Set false to hide
template: post              # 'post' (default) or 'page' (no date)
---
```

### Smart Code Styling

The engine detects the language of your code blocks.

* **Python/JS/HTML**: Renders in a light theme with syntax highlighting.
* **Bash/Console**: Renders in a **dark terminal style** automatically.

Just use standard Markdown:

````markdown
```bash
$ git push origin main
# This block will be dark automatically
```
````

## 📦 Quick Start

1. **Use this template** (or clone the repo):

    ```bash
    git clone https://github.com/yourname/luna-ssg.git
    ```

2. **Install dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Build the site**:

    ```bash
    python main.py
    ```

4. **Preview**:

    ```bash
    python -m http.server --directory _site
    ```

    Open `http://localhost:8000`.

## 🤖 CI/CD Deployment

This repo includes a GitHub Actions workflow (`.github/workflows/deploy.yml`).
Simply push to the `main` branch, and the site will be built and deployed to the `gh-pages` branch automatically.

## 📄 License

MIT License. Feel free to use Luna SSG for your personal blog!
