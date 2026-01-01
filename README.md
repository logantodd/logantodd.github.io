# abby's website

This is my personal website hosted on GitHub Pages. The site includes a blog for musings, a projects section highlighting my rocketry work, and a live Last.fm widget showing what I'm currently listening to.

## Features

- **Blog**: Jekyll-powered blog with markdown support
- **Projects Portfolio**: Dedicated collection for showcasing  projects
- **Last.fm Integration**: Live music widget displaying currently playing tracks using the Last.fm API
- **Responsive Design**: Custom CSS with mobile-friendly navigation and layout
- **Resume Page**: Professional experience and qualifications
- **Custom Permalink Structure**: Clean URLs for blog posts and project pages

## Usage

### Local Development

1. Install Ruby and Bundler:
```bash
gem install bundler
```

2. Install dependencies:
```bash
bundle install
```

3. Run the local development server:
```bash
bundle exec jekyll serve
```

4. Visit `http://localhost:4000` in your browser

### Adding Blog Posts

Create a new markdown file in `_posts/` following the naming convention `YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: "Your Post Title"
date: 2025-01-01
---

Your content here...
```

#### Blog Post Front Matter

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| `layout` | Yes | Page layout template | `post` |
| `title` | Yes | Post title | `"My Blog Post"` |
| `date` | Yes | Publication date | `2025-01-01` |
| `app_name` | No | Override menu bar title | `"Blog"` |

### Adding Projects

Create markdown files in `_projects/` directory with project details.

#### Project Front Matter

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| `title` | Yes | Project name | `"My Project"` |
| `status` | Yes | Project status (`active` or `archive`) | `active` |
| `description` | Yes | Short description shown in project listing | `"A cool project I built"` |
| `date` | Yes | Project start/creation date (for sorting) | `2019-01-01` |
| `article` | No | Show "Read More" button (default: `false`) | `true` or `false` |
| `featured` | No | Feature this project (currently unused) | `true` or `false` |
| `external_url` | No | External link URL (GitHub, live demo, etc.) | `"https://github.com/user/repo"` |
| `url_text` | No | Custom text for external link button (default: "External Link") | `"View on GitHub"` |

Example project front matter:

```markdown
---
title: High-Power Rocketry
status: active
featured: true
article: true
description: building high power rockets on a budget
external_url: "https://github.com/user/rocketry"
url_text: "View Code"
date: 2019-01-01
---

Your project details here...
```

### Configuration

Edit [`_config.yml`](_config.yml) to customize:
- Site title and description
- Last.fm username and API key
- Permalink structure
- Collection settings

### Last.fm Widget

To add the Last.fm widget to a page, include it in your markdown:

```markdown
{% include lastfm-widget.html %}
```

Configure your Last.fm credentials in `_config.yml`:
```yaml
lastfm:
  username: "your_username"
  api_key: "your_api_key"
```

Get a free API key from [Last.fm API](https://www.last.fm/api/account/create).

## Acknowledgements

- [**Jekyll**](https://github.com/jekyll/jekyll): Static site generator
- [**Catppuccin**](https://github.com/catppuccin/catppuccin): Soothing pastel theme for the site
- [**system7.css**](https://github.com/opencoca/system7.css): Classic Mac OS inspired CSS framework
- [**Atkinson Hyperlegible**](https://fonts.google.com/specimen/Atkinson+Hyperlegible): Font designed for greater legibility and readability
- [**Last.fm API**](https://www.last.fm/api): Music tracking and scrobbling data

---

made on earth by humans | 2025 abby bigaouette
