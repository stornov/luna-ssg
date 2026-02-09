# Changelog

All notable changes to the **Luna SSG** project will be documented in this file.

## [1.6.4] - 2026-02-10
### Added
- CSS styles for image captions (text becomes centered, italic, and gray when placed immediately under an image).
- Proper centering logic for images within post content.

## [1.6.3] - 2026-02-10
### Changed
- Refined homepage logic: the 10-post limit now applies exclusively to the `blog` section.
- Updated documentation and added `CHANGELOG.md`.

## [1.6.2] - 2026-02-09
### Added
- `baseurl` support for improved portability between root domains and subfolders (GitHub Pages demo support).

## [1.6.1] - 2026-02-08
### Fixed
- Heading hierarchy: distinguished H1 (2.0em) and H2 (1.5em) sizes for better visual structure.

## [1.6.0] - 2026-02-07
### Added
- Chronological Blog page (`/blog.html`) grouped by Year and Month.
- Automatic post counts in subtitles for Archive and Blog pages.
- Homepage optimization: limit `blog` section to the latest 10 posts.
- Unified typography and metadata styles.

## [1.5.0] - 2026-02-05
### Added
- Template inheritance using `base.html` and `{% extends %}` tags.
- Automatic Archive page (`/archive.html`) with category grouping.
### Changed
- Renamed `category` field to `section` for structural organization.
- Introduced semantic `category` field for Archive grouping.

## [1.4.0] - 2026-01-30
### Added
- `_media` folder support for hosting local assets.
- Automatic image conversion to WebP format.

## [1.3.0] - 2026-01-20
### Added
- `bottom_sections` feature for creating unlimited custom lists in the footer via config.

## [1.2.0] - 2026-01-15
### Added
- Linklog functionality (external links in titles).
- Support for custom "Projects" sections.

## [1.1.0] - 2026-01-10
### Changed
- Migrated to `markdown-it-py` for better rendering (tables, nested lists, strikethrough).

## [1.0.0] - 2026-01-01
### Added
- Initial release of Luna SSG.