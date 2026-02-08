# 🌙 Luna SSG (v1.5)

![Python](https://img.shields.io/badge/python-3.11+-blue.svg)
![Version](https://img.shields.io/badge/version-1.5.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

**Luna SSG** is a lightweight, custom-built static site generator written in **Python**.

It was designed as a high-performance, developer-friendly alternative to Jekyll. It converts Markdown files into a fully functional HTML website using Liquid templates, with zero Ruby dependencies.

---

## 🚀 Key Features

* **Pure Python Core**: Simple, understandable logic in a single `main.py` engine.
* **Liquid Templating**: Native support for logic-based HTML templates with **inheritance** (`base.html`, `{% extends %}`).
* **Dynamic Layouts**: Create unlimited custom lists (Projects, Books, Portfolio) in the footer directly from the config.
* **Smart Sections**: Automatically groups posts into structural sections (e.g., Blog, Games) based on the `section` field.
* **Auto-Generated Archive**: Creates a categorized `/archive.html` page for all your blog posts.
* **Linklog Support**: Create "Daring Fireball" style external link posts.
* **Intelligent URLs**: Auto-generates clean slugs from titles (or uses custom ones).
* **Template Switching**: Separate layouts for standard posts (with dates) and static pages (like 404 or About).
* **Developer UI**:
  * **Auto-Dark Mode for Code**: Console/Terminal code blocks (`bash`, `sh`) automatically render with a dark theme.
  * **Syntax Highlighting**: Integrated `highlight.js` for all languages.
* **Local Media Support**: Store images and files locally in `_media` folder.
* **GitHub Pages Ready**: Automatically generates `.nojekyll` to bypass Jekyll build limits.

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
│   ├── index.html        # Homepage with section logic
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

# 1. Top Navigation Menu
menu:
  - title: Home
    url: /
  - title: Archive
    url: /luna-ssg/archive.html
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

3. **Build the site**:

    ```bash
    python main.py
    ```

4. **Preview locally**:
    Start a simple Python server to view the generated site:

    ```bash
    python -m http.server --directory _site
    ```

    Then open [http://localhost:8000](http://localhost:8000) in your browser.

## 📜 Version History

* **v1.5**: Introduced template inheritance (`base.html`), added `archive.html` generator, and split logic into `section` (structure) vs `category` (semantic).
* **v1.4**: Added `_media` folder support for hosting local images and assets.
* **v1.3**: Added `bottom_sections` — create unlimited custom lists in the footer via config.
* **v1.2**: Added Linklog functionality and Projects section.
* **v1.1**: Migrated to `markdown-it-py` for better rendering (tables, nested lists).
* **v1.0**: Initial release.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
