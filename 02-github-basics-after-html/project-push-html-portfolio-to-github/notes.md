# Notes — GitHub Pages Deployment

## GitHub Pages Quick Setup

1. Push your HTML files to a public GitHub repository
2. Go to Settings → Pages
3. Source: Deploy from a branch → main → / (root)
4. Save
5. Wait 1–2 minutes
6. Visit: `https://yourusername.github.io/repository-name`

## GitHub Pages URL Format

```
https://USERNAME.github.io/REPOSITORY-NAME/
```

For a user/organization site (special repo named `username.github.io`):
```
https://USERNAME.github.io/
```

## Deployment Checklist

- [ ] Repository is public
- [ ] `index.html` is in the root folder
- [ ] GitHub Pages is enabled in Settings
- [ ] All file paths are relative (not absolute)
- [ ] All links work (no broken links)
- [ ] Images load correctly

## Common Issues

| Problem | Fix |
|---|---|
| Page shows 404 | Make sure `index.html` is in the root, not a subfolder |
| CSS not loading | Check the path in `<link href>` — must be relative |
| Images not showing | Check image paths — must be relative |
| Changes not appearing | Wait 1–2 minutes and hard refresh (Ctrl+Shift+R) |
| Site not found | Make sure GitHub Pages is enabled in Settings |

## Relative vs Absolute Paths

```html
<!-- Absolute path (breaks on GitHub Pages) -->
<link href="/Users/alex/Desktop/portfolio/style.css" rel="stylesheet">

<!-- Relative path (works everywhere) -->
<link href="style.css" rel="stylesheet">
<link href="./style.css" rel="stylesheet">
```

Always use relative paths in your HTML files.

## Updating Your Site

```bash
# Make changes to your files
git add .
git commit -m "Update portfolio with new project"
git push
# Wait 1-2 minutes, then refresh your GitHub Pages URL
```
