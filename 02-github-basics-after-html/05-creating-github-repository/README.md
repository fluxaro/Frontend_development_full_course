# 05 — Creating a GitHub Repository

## Overview

Now that you know how to use Git locally, it's time to put your code on GitHub. This lesson walks through creating a repository on GitHub, understanding all the options, and exploring the GitHub interface.

---

## Creating a Repository on GitHub

### Step-by-Step

1. **Log in** to https://github.com
2. Click the **+** icon in the top-right corner → **New repository**
   (or go directly to https://github.com/new)
3. Fill in the details:
   - **Repository name** — use lowercase, hyphens instead of spaces (e.g., `my-portfolio`)
   - **Description** — optional but recommended (1–2 sentences about the project)
   - **Public or Private** — see below
   - **Initialize with README** — check this if starting fresh
   - **.gitignore template** — choose a template if applicable
   - **License** — choose if you want to open source it
4. Click **Create repository**

---

## Public vs Private Repositories

| | Public | Private |
|---|---|---|
| **Who can see it** | Anyone on the internet | Only you and collaborators you invite |
| **Who can clone it** | Anyone | Only invited collaborators |
| **GitHub Pages** | Free | Free (with limitations) |
| **Best for** | Portfolio projects, open source | Work projects, personal experiments |
| **Cost** | Free | Free (unlimited on free plan) |

**For bootcamp projects:** Use **public** repos. Employers and instructors need to see your work.

---

## README Initialization

When you check "Initialize this repository with a README", GitHub creates a `README.md` file automatically. This is useful when:
- You're starting a new project directly on GitHub
- You want to clone the repo and start working immediately

**If you already have a local project with commits:** Don't initialize with a README — it will create a conflict when you try to push.

---

## .gitignore Templates

GitHub offers pre-built `.gitignore` templates for different project types. When you select one, GitHub creates a `.gitignore` file that ignores common files for that technology.

Common templates:
- **Node** — for JavaScript/Node.js projects
- **Python** — for Python projects
- **macOS** — ignores `.DS_Store` and other Mac system files
- **VisualStudioCode** — ignores VS Code settings folders

For a basic HTML project, you can skip this or choose "Node" if you plan to add npm packages later.

---

## License Options

A license tells others what they can and can't do with your code.

| License | What it means |
|---|---|
| **MIT** | Anyone can use, modify, and distribute your code (most permissive) |
| **Apache 2.0** | Like MIT but with patent protection |
| **GPL v3** | Anyone can use it, but derivatives must also be open source |
| **No license** | All rights reserved — others technically can't use your code |

**For bootcamp projects:** MIT is the most common choice for open source projects. It's simple and permissive.

---

## Exploring the GitHub Repository Interface

After creating a repo, you'll see the main repository page. Here's what everything means:

### The Code Tab
- Shows all your files and folders
- Click any file to view its contents
- The README.md is rendered below the file list

### The Commits Link
- Shows the number of commits
- Click to see the full commit history (like `git log`)

### The Branches Dropdown
- Shows which branch you're on (usually `main`)
- Click to switch branches or see all branches

### The Issues Tab
- Where bugs and feature requests are tracked
- Anyone can open an issue on a public repo

### The Pull Requests Tab
- Where code review happens
- Used when collaborating with others

### The Actions Tab
- Automated workflows (CI/CD)
- Can run tests automatically when you push

### The Settings Tab
- Repo settings: rename, delete, add collaborators
- GitHub Pages settings

### The Green "Code" Button
- Shows the URL to clone the repo
- Switch between HTTPS and SSH URLs

---

## Repository Settings Worth Knowing

### Renaming a Repository
Settings → General → Repository name → Rename

**Note:** Renaming changes the URL. Update your local remote with:
```bash
git remote set-url origin <new-url>
```

### Adding Collaborators
Settings → Collaborators → Add people

### Enabling GitHub Pages
Settings → Pages → Source → Deploy from branch → main → / (root) → Save

### Deleting a Repository
Settings → Danger Zone → Delete this repository (requires typing the repo name to confirm)

---

## Learning Objectives

By the end of this lesson you should be able to:

- [ ] Create a new repository on GitHub
- [ ] Choose between public and private appropriately
- [ ] Explain what a README, .gitignore, and license are
- [ ] Navigate the GitHub repository interface
- [ ] Find commits, branches, issues, and pull requests on a repo
- [ ] Explain what GitHub Pages is
