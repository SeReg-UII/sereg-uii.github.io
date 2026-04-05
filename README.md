# Research Working Group — GitHub Pages Site

Built with [Jekyll](https://jekyllrb.com/) and hosted on [GitHub Pages](https://pages.github.com/).
Design inspired by the [al-folio](https://github.com/alshedivat/al-folio) theme.

## Quick Start

### 1. Configure your group info

Edit `_config.yml` and fill in:
- `title` — your working group name
- `description` — short tagline
- `url` — your GitHub Pages URL
- `author` fields (name, institution, department, email)
- `social` links (Google Scholar, GitHub, LinkedIn, etc.)

### 2. Update content

| File | What to edit |
|------|-------------|
| `_pages/about.md` | Group bio / overview |
| `_pages/research.md` | Research themes and projects |
| `_pages/publications.md` | Auto-rendered from data |
| `_pages/team.md` | Auto-rendered from data |
| `_pages/gallery.md` | Auto-rendered from data |
| `_data/publications.yml` | Add your papers |
| `_data/members.yml` | Add team members |
| `_data/gallery.yml` | Add gallery photos |
| `_news/*.md` | Add news announcements |

### 3. Add images

Place images in:
- `assets/img/profile/` — group or PI photo (used on About page)
- `assets/img/team/` — member photos
- `assets/img/gallery/` — gallery photos
- `assets/img/publications/` — paper preview thumbnails

### 4. Enable GitHub Pages

1. Go to **Settings -> Pages** in your repository
2. Under **Source**, select **GitHub Actions**
3. Push to `main` — the site will build and deploy automatically

## Local Development

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```
