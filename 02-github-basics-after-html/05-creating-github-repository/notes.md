# Notes — Creating GitHub Repositories

## Repository Creation Checklist

When creating a new GitHub repo:

- [ ] Choose a clear, descriptive name (lowercase, hyphens)
- [ ] Add a short description
- [ ] Choose Public or Private appropriately
- [ ] Decide whether to initialize with README
- [ ] Choose .gitignore template if needed
- [ ] Choose a license if open sourcing

---

## Naming Conventions

```
✅ Good names:
my-portfolio
frontend-bootcamp-projects
alex-rivera-portfolio
todo-app-vanilla-js
weather-dashboard

❌ Bad names:
test
untitled
asdfgh
MyPortfolio (use hyphens, not camelCase)
my portfolio (no spaces)
```

---

## Public vs Private

| Situation | Use |
|---|---|
| Portfolio project | Public |
| Open source project | Public |
| Work/client project | Private |
| Personal experiments | Either |
| Projects with secrets/API keys | Private |
| Bootcamp assignments | Public (so instructors can see) |

---

## README Best Practices

### Must-Have Sections
1. **Title** — Clear project name
2. **Description** — What the project does (2–3 sentences)
3. **Technologies** — What it's built with
4. **How to run** — Installation/setup instructions
5. **Author** — Who built it

### Nice-to-Have Sections
- Live demo link
- Screenshots
- Features list
- Contributing guidelines
- License

### Markdown Quick Reference
```markdown
# H1 Heading
## H2 Heading
### H3 Heading

**bold text**
*italic text*
`inline code`

```code block```

- Bullet item
- Another item

1. Numbered item
2. Another item

[Link text](https://url.com)
![Alt text](image.jpg)
```

---

## License Types (Simple Explanation)

| License | Use when... |
|---|---|
| **MIT** | You want anyone to use your code freely |
| **Apache 2.0** | Like MIT but with patent protection |
| **GPL v3** | You want derivatives to also be open source |
| **No license** | You want to keep all rights (others can't use it) |

For most bootcamp/portfolio projects: **MIT** is the right choice.

---

## GitHub Interface Quick Reference

| Element | What it does |
|---|---|
| ⭐ Stars | Bookmark a repo (like a favorite) |
| 🍴 Fork | Make your own copy of the repo |
| 👁️ Watch | Get notifications for activity |
| Code tab | Browse files |
| Issues tab | Bug reports and feature requests |
| Pull Requests | Code review and merging |
| Actions | Automated CI/CD workflows |
| Settings | Repo configuration |
| Green "Code" button | Get clone URL |

---

## GitHub Pages

GitHub Pages lets you host static websites (HTML/CSS/JS) for free directly from a GitHub repo.

### How to Enable
1. Go to repo → Settings → Pages
2. Source: Deploy from a branch
3. Branch: main
4. Folder: / (root)
5. Click Save

### Your URL will be:
```
https://yourusername.github.io/repo-name
```

### What works on GitHub Pages
- ✅ HTML files
- ✅ CSS files
- ✅ JavaScript files
- ✅ Images and other static assets
- ❌ Server-side code (PHP, Python, Node.js)
- ❌ Databases

---

## Common Issues

### "Repository already exists"
You tried to create a repo with a name you already used. Choose a different name or delete the old one.

### README not rendering correctly
Check your markdown syntax. Common issues:
- Missing blank line between heading and paragraph
- Code blocks not closed properly
- Incorrect link syntax

### Files not showing after push
Make sure you ran `git push` and it succeeded. Check for error messages.

### Wrong branch name
If your local branch is `master` but GitHub expects `main`:
```bash
git branch -M main
git push -u origin main
```

---

## Repo Settings Worth Knowing

```
Settings → General
  - Rename repository
  - Change visibility (public ↔ private)
  - Delete repository

Settings → Collaborators
  - Add team members
  - Set permissions

Settings → Pages
  - Enable GitHub Pages
  - Set custom domain

Settings → Branches
  - Set default branch
  - Add branch protection rules
```
