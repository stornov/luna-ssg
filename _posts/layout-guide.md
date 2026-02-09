---
title: "Mastering Layout: Sections, Categories, and Templates"
date: 2026-02-10
section: blog
category: Documentation
location: "Luna Core"
---

Luna SSG is driven by metadata (Frontmatter). By changing a few lines at the top of your Markdown file, you can completely change how and where your content appears.

This guide covers the core logic of the engine as of **v1.6**.

---

## 1. Sections vs. Categories

In Luna SSG, these two fields serve different purposes:

### `section` (Structural)
The `section` field determines which block on the **Homepage** your post will appear in.
*   **How to use:** The value must match an `id` in the `sections` list within your `_config.yml`.
*   **Example:** `section: blog` or `section: tech`.
*   **Behavior:** To keep the homepage clean, the **blog** section is limited to the latest 10 posts. Other sections (like "Projects" or "Events") display all entries.

### `category` (Semantic)
The `category` field is used for grouping posts on the **Archive** page.
*   **Availability:** Currently, categories are only processed for posts where `section: blog`.
*   **Default:** If not specified, it defaults to **"Random"**.
*   **Behavior:** Clicking a category in the post metadata will take you to the specific section in `/archive.html`.

---

## 2. Templates

You can choose between two built-in layouts:

1.  **`template: post`** (Default):
    *   Displays the date and location.
    *   Shows the "Posted in..." metadata.
    *   Appears in the chronological blog list.
2.  **`template: page`**:
    *   Hides the date and metadata.
    *   Used for static content like "About Me", "Contact", or "404".

---

## 3. Linklog (External Links)

Luna SSG supports "Daring Fireball" style link posts. If you add a `link` field, the post title on the homepage and archive will point directly to that URL.

```yaml
title: "Check this cool site"
link: "https://example.com"
```

A small arrow (`→`) is automatically added to the title to indicate an external destination.

---

## 4. Intelligent URLs

By default, the engine creates a URL based on your title (e.g., `Hello World` -> `hello-world.html`). However, you can override this:

*   **Custom Slug:** Use `slug: my-custom-url` to set a specific filename.
*   **Unpublished:** Set `published: false` to hide the post from all lists (useful for drafts), though the HTML file will still be generated if you want to preview it via a direct link.

---

## Example Frontmatter

Here is a complete example of a well-configured post:

```yaml
---
title: "My New Project"
date: 2026-02-10
section: blog
category: Projects
location: "Ozersk, Russia"
slug: cool-project-2026
published: true
template: post
---
```

Happy blogging with **Luna SSG**!
