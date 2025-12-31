# abbyfluoroethane.github.io

A personal portfolio and blog site built with Jekyll, featuring a minimalist design and Last.fm integration.

## Description

This is my personal website hosted on GitHub Pages, showcasing my work in aerospace, rocketry, and engineering. The site includes a blog for technical posts and musings, a projects section highlighting my rocket propulsion and high-power rocketry work, and a live Last.fm widget showing what I'm currently listening to.

Built with Jekyll for static site generation, the site features a clean, responsive design with a custom navigation system and integrated music tracking.

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
title: Your Post Title
app_name: Blog
---

Your content here...
```

### Adding Projects

Create markdown files in `_projects/` directory with project details.

### Configuration

Edit [`_config.yml`](_config.yml) to customize:
- Site title and description
- Last.fm username and API key
- Permalink structure
- Collection settings

## Acknowledgements

- [**Jekyll**](https://github.com/jekyll/jekyll): Static site generator
- [**Catppuccin**](https://github.com/catppuccin/catppuccin): Soothing pastel theme for the site
- [**system7.css**](https://github.com/opencoca/system7.css): Classic Mac OS inspired CSS framework
- [**Atkinson Hyperlegible**](https://fonts.google.com/specimen/Atkinson+Hyperlegible): Font designed for greater legibility and readability
- [**Last.fm API**](https://www.last.fm/api): Music tracking and scrobbling data

---

made on earth by humans | 2025 abby bigaouette
