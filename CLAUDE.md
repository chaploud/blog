# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo-based technical blog in Japanese (`chaploud dev notes`) that uses the PaperMod theme. The blog is automatically deployed to GitHub Pages via GitHub Actions when changes are pushed to the main branch.

## Key Configuration

- **Site Configuration**: `hugo.toml` - contains base URL, language (Japanese), title, theme, and various PaperMod parameters
- **Content Structure**: Posts are located in `content/posts/` with markdown files
- **Theme**: Uses PaperMod theme located in `themes/PaperMod/`
- **Deployment**: Automatic deployment via `.github/workflows/hugo.yml` using Hugo v0.147.9

## Common Commands

### Content Management
```bash
# Create a new blog post (draft by default)
hugo new posts/post-name.md

# Start development server (include drafts with -D)
hugo server
hugo server -D

# Build the site for production
hugo --gc --minify
```

### Development Workflow
```bash
# 1. Create new post
hugo new posts/name-of-entry.md

# 2. Edit the post (set draft = false when ready)
# 3. Preview locally
hugo server -D

# 4. Build and commit
git add .
git commit -m "commit message"
git push origin main  # Triggers GitHub Actions deployment
```

### Directory Structure
- `content/` - Blog content and pages
- `content/posts/` - Blog posts
- `layouts/` - Custom layout overrides (if any)
- `static/` - Static assets
- `assets/` - Hugo asset pipeline files
- `archetypes/` - Content templates (default.md for new posts)
- `public/` - Generated site (created by Hugo build)

## Content Creation

New posts are created using the archetype in `archetypes/default.md` which sets:
- Date automatically
- `draft = true` by default
- Title based on filename

Remember to set `draft = false` before committing posts that should be published.

## Deployment

The site automatically deploys to GitHub Pages when changes are pushed to main branch. The GitHub Actions workflow:
1. Installs Hugo v0.147.9
2. Builds the site with `--gc --minify` flags
3. Deploys to GitHub Pages

Base URL is configured for: `https://chaploud.github.io/blog/`