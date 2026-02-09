---
title: "Markdown Features Demo"
date: 2026-01-25
section: tech
slug: markdown-demo
template: page
---

This page demonstrates the full range of Markdown syntax supported by the Luna SSG engine.

---

## Headings

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

---

## Text Formatting

**This is bold text.**

*This is italic text.*

~~This was a mistake.~~

You can combine them **like *this***.

---

## Blockquotes

> This is a blockquote. It's a great way to highlight a section of text. You can quote people, or just make a point.

---

> Nested blockquotes are also possible.
>> Just add another angle bracket.

---

## Lists

### Unordered List

* Item A
* Item B
  * Sub-item 1
  * Sub-item 2
* Item C

### Ordered List

1. First item
2. Second item
3. Third item

---

## Links and Images

This is a [link to Google](https://www.google.com).

Here is a placeholder image:

![A placeholder image of a "landscape"](/media/example.png)
*Image of a "landscape"*

---

## Code Blocks

### Inline Code

You can wrap code `like this` directly in a sentence.

### Standard Code Block (Python)

This renders with a light theme and syntax highlighting.

```python
def hello_world():
    # This is a comment
    message = "Hello from Luna SSG!"
    print(message)
```

### Terminal Style (Dark Mode)

This block is automatically styled like a terminal console.

```bash
$ git clone https://github.com/stornov/luna-ssg.git
Cloning into 'luna-ssg'...
Done.
```

---

## Tables

You can create tables with headers and aligned columns.

| Feature         | Status      | Priority |
| :-------------- | :---------: | -------: |
| Markdown Parser | Implemented |     High |
| Templating      | Implemented |     High |
| Coffee Maker    | Future      |      Low |

---

## Horizontal Rule

A horizontal rule is created with three hyphens and is great for separating sections.

---

That's all for now!
