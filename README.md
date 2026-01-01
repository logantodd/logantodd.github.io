# abby's website

This is my personal website hosted on GitHub Pages. The site includes a blog for musings, a projects section highlighting my rocketry work, and a live Last.fm widget showing what I'm currently listening to.

## Features

- **Blog**: Jekyll-powered blog with markdown support and clean URLs
- **Projects Portfolio**: Dedicated collection for showcasing projects with customizable buttons and descriptions
- **Last.fm Integration**: Live music widget displaying currently playing tracks with auto-refresh and caching
- **Theme Switching**: Multiple Catppuccin themes (Mocha, Latte) plus Monochrome mode
- **Font Options**: Toggle between classic Mac fonts and Atkinson Hyperlegible for accessibility
- **Responsive Design**: Mobile-optimized layout with touch-friendly navigation
- **Resume Page**: Professional experience and qualifications
- **Custom 404 Page**: Themed error page with sad Mac icon
- **Staging Banner**: Visual indicator for development environments
- **88x31 Buttons**: Classic web button collection in footer

## Usage

### Local Development

#### Initial Setup

1. Install Ruby and Bundler:
```bash
gem install bundler
```

2. Clone the repository:
```bash
git clone https://github.com/abbyfluoroethane/abbyfluoroethane.github.io.git
cd abbyfluoroethane.github.io
```

3. Configure Bundler to install gems locally:
```bash
bundle config set --local path 'vendor/bundle'
bundle install
```

**Note**: Installing gems locally to `vendor/bundle` ensures Jekyll is available via `bundle exec` and prevents conflicts with system-wide gems.

#### Running the Development Server

Start Jekyll with:
```bash
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`. Jekyll will automatically rebuild when you make changes to files.

**Useful options:**
- `bundle exec jekyll serve --drafts` - Include draft posts
- `bundle exec jekyll serve --livereload` - Auto-refresh browser on changes
- `bundle exec jekyll serve --incremental` - Faster rebuilds (only changed files)

#### Development Environment Indicator

When running locally (localhost or 127.0.0.1), a red "STAGING" banner appears at the top of the page to indicate you're in development mode.

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

The widget features:
- Auto-refresh every 2 minutes
- Manual refresh button
- LocalStorage caching for faster loads
- "Now Playing" vs "Last Played" status indicator
- Animated pulse for currently playing tracks
- Direct link to track on Last.fm
- Fallback to cached data if API fails

### Theme Customization

The site supports multiple color themes via the menubar:

**Available Themes:**
- **Mocha** (dark) - Default dark theme
- **Latte** (light) - Light mode with high contrast
- **Monochrome** - Classic black and white

Theme preference is saved to localStorage and persists across sessions. The theme is applied before page render to prevent FOUC (Flash of Unstyled Content).

### Font Options

Toggle between font sets via the menubar:

- **Default**: Classic Mac fonts (Chicago headers, Geneva body)
- **Atkinson Hyperlegible**: Accessible font optimized for readability

Font preference is saved to localStorage.

### Site Structure

```
├── _posts/          # Blog posts (YYYY-MM-DD-title.md)
├── _projects/       # Project pages
├── _layouts/        # Page templates
│   ├── default.html # Main layout with menubar and window chrome
│   └── post.html    # Blog post layout
├── _includes/       # Reusable components
│   ├── head.html           # HTML head with fonts and theme
│   ├── menubar.html        # Top navigation bar
│   ├── project-preview.html # Project card component
│   └── lastfm-widget.html  # Last.fm now playing widget
├── assets/
│   ├── css/
│   │   ├── catppuccin.css  # Theme color definitions
│   │   └── custom.css      # Site-specific styles
│   ├── fonts/              # Chicago and Geneva fonts
│   └── images/             # Icons, buttons, artwork
├── _config.yml      # Jekyll configuration
└── index.md         # Homepage
```

### Images in Content

Images in markdown files are automatically constrained to content width:

```markdown
![Alt text](/assets/images/example.png)
```

Images will:
- Never exceed content width (max-width: 100%)
- Maintain aspect ratio
- Display as block elements with margin spacing

### Deployment

The site automatically deploys via GitHub Pages when changes are pushed to the `main` branch. GitHub Actions builds the site using the `github-pages` gem.

**Build process:**
1. Push changes to `main` branch
2. GitHub Actions triggers Jekyll build
3. Built site is deployed to `abbyfluoroethane.github.io`

**Branches:**
- `main` - Production branch (auto-deploys)
- `devel` - Development branch for testing changes

### Troubleshooting

**Site not updating:**
- Check for syntax errors in markdown/YAML front matter
- Verify file naming (posts must be `YYYY-MM-DD-title.md`)
- Restart Jekyll server: `Ctrl+C` then `bundle exec jekyll serve`

**Last.fm widget not working:**
- Verify API key is correct in `_config.yml`
- Check browser console for errors
- Ensure username is correct and profile is public

## Acknowledgements

- [**Jekyll**](https://github.com/jekyll/jekyll): Static site generator
- [**Catppuccin**](https://github.com/catppuccin/catppuccin): Soothing pastel theme for the site
- [**system7.css**](https://github.com/opencoca/system7.css): Classic Mac OS inspired CSS framework
- [**Atkinson Hyperlegible**](https://fonts.google.com/specimen/Atkinson+Hyperlegible): Font designed for greater legibility and readability
- [**Last.fm API**](https://www.last.fm/api): Music tracking and scrobbling data

---

made on earth by humans | 2025 abby bigaouette
