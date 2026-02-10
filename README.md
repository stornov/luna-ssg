# 🌙 Luna SSG (v1.6.6)

![Python](https://img.shields.io/badge/python-3.11+-blue.svg)
![Version](https://img.shields.io/badge/version-1.6.6-blue)
![License](https://img.shields.io/badge/license-MIT-green)

**Luna SSG** is a lightweight, custom-built static site generator written in **Python**.

It was designed as a high-performance, developer-friendly alternative to Jekyll. It converts Markdown files into a fully functional HTML website using Liquid templates, with zero Ruby dependencies.

---

## 🚀 Key Features

### 🛠️ Core Engine
* **Pure Python Core**: Simple, understandable logic in a single `main.py` engine.
* **Liquid Templating**: Native support for logic-based HTML templates with inheritance (`base.html`, `{% extends %}`).
* **Subfolder Portability**: Support for root domains or project subfolders (e.g., `username.github.io/repo/`) via the `baseurl` setting.
* **GitHub Pages Ready**: Automatically generates `.nojekyll` and includes deployment workflows.

### 📝 Content Management
* **Smart Sections & Archive**: Automatically groups posts into structural sections for the homepage and creates a categorized `/archive.html` with post counts.
* **Chronological Blog**: Generates a `/blog.html` page grouped by Year and Month.
* **Smart Homepage**: To keep the landing page clean, the **blog** section is limited to the latest 10 posts.
* **Linklog Support**: Create "Daring Fireball" style external link posts.

### 🎨 Design & DX (Developer Experience)
* **Mobile Responsive**: Fully optimized for smartphones and tablets with a 2-column grid footer and scrollable tables.
* **Smart Code Styling**: Console blocks (`bash`, `sh`) automatically render with a dark terminal theme.
* **Refined Typography**: Unified heading sizes and metadata styles for a professional look.
* **Local Media Support**: Automatic processing of images from the `_media` folder (WebP conversion).

## 🛠️ Tech Stack

* **python-liquid**: Templating engine for flexible HTML layouts.
* **python-frontmatter**: For parsing YAML metadata in Markdown files.
* **markdown-it-py**: Fast and CommonMark-compliant Markdown parser (replaces standard `markdown` lib).
* **pyyaml**: For project configuration management.

## 📂 Project Structure

```text
.
├── main.py               # The core build script (The Engine)
├── _config.yml           # Global site & navigation settings
├── requirements.txt      # Python dependencies
├── _posts/               # Markdown content files
├── _templates/           # Liquid HTML templates
│   ├── base.html         # Base site skeleton (<html>, <head>, <body>)
│   ├── footer.html       # Shared site footer content
│   ├── index.html        # Homepage (latest 10 posts)
│   ├── blog.html         # Chronological list (Year > Month)
│   ├── archive.html      # Categorized archive page
│   ├── post.html         # Template for blog articles (with date)
│   └── page.html         # Template for static pages (no date)
├── _themes/              # CSS Stylesheets
├── _media/               # Local images and static assets
└── .github/workflows/    # GitHub Actions automation script
```

## ⚙️ Configuration

Manage your site structure via `_config.yml` without touching any Python code:

```yaml
title: My Awesome Site
theme: mystyle.css
baseurl: "/luna-ssg"  # NEW: Use "/repo-name" for project pages, or "" for root domains

# 1. Top Navigation Menu
menu:
  - title: Home
    url: /
  - title: Archive
    url: /archive.html
  - title: GitHub
    url: https://github.com/

# 2. Homepage Content Sections
# 'id' must match the 'section' in your .md files
sections:
  - id: blog
    title: "Latest Blog Posts"
  - id: tech
    title: "Technology"

# 3. Dynamic Bottom Sections (New in v1.3)
# You can add as many lists as you want (Projects, Books, Friends, etc.)
bottom_sections:
  - title: "My Projects"
    items:
      - title: Luna SSG
        url: https://github.com/stornov/luna-ssg
        description: "My custom site engine."
      - title: Another App
        url: https://google.com
        description: "A cool demo app."

  - title: "Reading List"
    items:
      - title: "Clean Code"
        url: https://amazon.com
        description: "Essential reading."
```

## ✍️ Writing Content

To create a new post or page, add a `.md` file to the `_posts/` directory.

### Metadata (Frontmatter)

Each file starts with a YAML block. Here is the configuration:

```markdown
---
title: "How to use Pathlib"
date: 2026-01-27
section: tech           # Structural: Places post in the "Technology" section on Home
category: Python        # Semantic: Groups post under "Python" in the Archive
link: https://python.org # Optional: Makes this a "Linklog" post (redirects externally)
slug: pathlib-guide     # Custom URL (optional)
published: true         # Set to false to hide from lists
template: post          # Use 'page' to hide date/location
location: "Somewhere"
---
```

### 📝 Supported Markdown Features

The generator uses `markdown-it-py`, ensuring strict adherence to CommonMark standards with extra features enabled:

* **Standard Markdown**: Headings, lists, links, images, blockquotes.
* **Tables**: Fully supported with header alignment.
* **Strikethrough**: Use `~~text~~` to cross out words.
* **Code Blocks**: Fenced blocks with automatic syntax highlighting.
* **Nested Lists**: Proper indentation for multi-level lists.

### 🖥️ Smart Code Styling

No extra configuration needed! The engine automatically detects the language and applies the correct theme:

1. **Light Theme**: For `python`, `javascript`, `html`, etc.
2. **Dark Terminal Theme**: For `bash`, `sh`, `console`, `shell`.

**Example (Dark Mode):**

````markdown
```bash
$ git push origin main
# This block renders in dark mode automatically
```
````

## 🖼️ Images & Media

You can store images locally instead of uploading them to external sites.

1. Place your files in the `_media/` directory.
2. Reference them in Markdown using the absolute path `/media/filename.ext`.

**Example:**
If you have a file `_media/example.png`:

```markdown
![My Image](/media/example.png)
```

## 📦 Quick Start

1. **Use this template** (or clone the repo):
    ```bash
    git clone https://github.com/stornov/luna-ssg.git
    cd luna-ssg
    ```

2. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Configure (Crucial for GitHub Pages)**:
    Open `_config.yml` and set your `baseurl`:
    * If your site is `username.github.io/my-site/`, set `baseurl: "/my-site"`.
    * If you use a custom domain or it's a root user site, set `baseurl: ""`.

4. **Build the site**:
    ```bash
    python main.py
    ```

5. **Preview locally**:
    Start a simple Python server to view the generated site:
    ```bash
    python -m http.server --directory _site
    ```

    Then open [http://localhost:8000](http://localhost:8000) in your browser.

## 📜 Version History

Current version: **v1.6.6**

The full list of changes and roadmap is available in [CHANGELOG.md](./CHANGELOG.md).

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
