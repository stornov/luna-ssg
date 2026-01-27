# 🌙 Luna SSG (v1.2)

![Python](https://img.shields.io/badge/python-3.11+-blue.svg)
![Version](https://img.shields.io/badge/version-1.2.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

**Luna SSG** is a lightweight, custom-built static site generator written in Python. Designed as a high-performance, developer-friendly alternative to Jekyll with native "Linklog" support.

---

## 🚀 Key Features

*   **Pure Python Core**: Simple logic in a single `main.py` engine.
*   **Smart Categorization**: Groups posts into sections (Blog, Games, Dev) via `_config.yml`.
*   **Linklog Support (v1.2)**: Ability to create "link posts" that redirect directly to external URLs (Daring Fireball style).
*   **Projects Portfolio (v1.2)**: Dedicated section for showcasing projects in the footer.
*   **Auto-Dark Mode**: Terminal code blocks (`bash`, `sh`) render with a dark theme automatically.
*   **GitHub Pages Ready**: Auto-generates `.nojekyll` to bypass Jekyll limits.

## ⚙️ Configuration

Control your site structure via `_config.yml`.

```yaml
title: My Awesome Site
theme: mystyle.css

# 1. Navigation Menu
menu:
  - title: Home
    url: /

# 2. Content Categories
sections:
  - id: blog
    title: "Latest Thoughts"

# 3. Projects / Portfolio (New in v1.2)
# Displayed at the bottom of the home page
projects:
  - title: Luna SSG
    url: https://github.com/yourname/luna-ssg
    description: "My custom python engine."
  - title: Another App
    url: https://google.com
    description: "Something cool I made."
```

## ✍️ Writing Content

Create `.md` files in the `_posts/` directory.

### Metadata Options
```yaml
---
title: "My New Post"
date: 2026-01-27
category: blog
link: https://external-site.com/cool-article  # <--- NEW: External Link
slug: my-custom-url
published: true
template: post
---
```

### 🔗 Linklog Posts
If you add a `link: URL` field to your Frontmatter:
1.  The post title on the homepage will point **directly** to that URL.
2.  An arrow (`→`) will be appended to the title.
3.  This is perfect for sharing interesting articles from other sites.

## 📦 Quick Start

1.  **Clone the repo**:
    ```bash
    git clone https://github.com/yourname/luna-ssg.git
    ```
2.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```
3.  **Build**:
    ```bash
    python main.py
    ```

## 📜 Version History
*   **v1.2**: Added Linklog functionality (external posts) and Projects section.
*   **v1.1**: Migrated to `markdown-it-py` for better rendering (tables, nested lists).
*   **v1.0**: Initial release.

## 📄 License
MIT License.