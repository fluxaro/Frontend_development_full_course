# 03 — git init, add, commit, status

## Overview

This is where Git actually starts. You'll learn the four commands you'll use every single day as a developer: `git init`, `git add`, `git status`, and `git commit`. Together, they form the core Git workflow.

---

## The Three Areas of Git

Before learning the commands, understand the three places your code can live:

```
┌─────────────────────┐    git add    ┌──────────────────┐    git commit    ┌──────────────────┐
│                     │  ──────────►  │                  │  ──────────────► │                  │
│  Working Directory  │               │  Staging Area    │                  │   Repository     │
│                     │  ◄──────────  │  (Index)         │                  │   (.git folder)  │
│  Your actual files  │  git restore  │                  │                  │   Commit history │
└─────────────────────┘               └──────────────────┘                  └──────────────────┘
```

| Area | What it is | Analogy |
|---|---|---|
| **Working Directory** | Your actual files on disk | Your desk where you're working |
| **Staging Area** | Changes you've selected for the next commit | A box you're packing to ship |
| **Repository** | The permanent history of commits | The shipped packages in a warehouse |

---

## The Commands

### `git init`

Initializes a new Git repository in the current folder. Creates a hidden `.git` folder that stores all the version history.

```bash
git init
```

**Output:**
```
Initialized empty Git repository in /path/to/your/project/.git/
```

**When to use:** Once, at the start of a new project.

**Important:** Only run `git init` once per project. Don't run it inside a folder that's already a Git repo.

---

### `git status`

Shows the current state of your working directory and staging area. This is the most-used Git command — run it constantly.

```bash
git status
```

**What it tells you:**
- Which branch you're on
- Which files have been modified
- Which files are staged (ready to commit)
- Which files are untracked (new files Git doesn't know about yet)

**Run this before and after every other Git command** to understand what's happening.

---

### `git add`

Moves changes from the working directory to the staging area. You're telling Git "include these changes in the next commit."

```bash
# Add a specific file
git add index.html

# Add multiple files
git add index.html about.html

# Add all changes in the current directory
git add .

# Add all changes in the entire repo
git add -A
```

**The staging area lets you be selective.** If you changed 5 files but only want to commit 2 of them, you can `git add` just those 2.

---

### `git commit`

Takes everything in the staging area and saves it as a permanent snapshot in the repository. Every commit needs a message describing what changed.

```bash
# Commit with a message (most common)
git commit -m "Add navigation bar to index.html"

# Open your editor to write a longer message
git commit

# Stage all tracked files and commit in one step
git commit -am "Fix typo in about page"
```

**After committing:** The staging area is cleared. Your working directory is "clean."

---

## Commit Message Best Practices

A good commit message is like a good subject line in an email — short, specific, and informative.

### The Rules

1. **Use the imperative mood** — "Add feature" not "Added feature" or "Adding feature"
2. **Keep the first line under 72 characters**
3. **Be specific** — describe what changed, not just "update" or "fix"
4. **Start with a capital letter**
5. **No period at the end**

### Good vs Bad Examples

| ❌ Bad | ✅ Good |
|---|---|
| `update` | `Update navigation links in header` |
| `fix bug` | `Fix broken contact form submission` |
| `changes` | `Add responsive styles for mobile menu` |
| `wip` | `Add hero section to homepage (in progress)` |
| `asdfgh` | `Remove unused CSS from about page` |

### Commit Message Formats

**Simple (one line):**
```
Add dark mode toggle to settings page
```

**Detailed (with body):**
```
Add dark mode toggle to settings page

Users can now switch between light and dark themes.
The preference is saved to localStorage and persists
across page reloads.
```

---

## The Full Workflow

Here's what a typical session looks like:

```bash
# 1. Check what's going on
git status

# 2. Make changes to your files...

# 3. Check what changed
git status

# 4. Stage the changes you want to commit
git add index.html

# 5. Verify what's staged
git status

# 6. Commit with a message
git commit -m "Add hero section to homepage"

# 7. Verify the commit was made
git status
# Should say "nothing to commit, working tree clean"
```

---

## What's Inside the `.git` Folder?

When you run `git init`, Git creates a `.git` folder. You don't need to touch it, but it's good to know it exists:

```
.git/
├── HEAD          ← Points to the current branch
├── config        ← Local repo configuration
├── objects/      ← All your commits, files, trees stored here
├── refs/         ← Branch and tag references
└── index         ← The staging area
```

**Never manually edit or delete files inside `.git`** — you could corrupt your repo.

---

## Learning Objectives

By the end of this lesson you should be able to:

- [ ] Initialize a new Git repository with `git init`
- [ ] Check the status of your repo with `git status`
- [ ] Stage files with `git add`
- [ ] Create a commit with a meaningful message using `git commit -m`
- [ ] Explain the difference between the working directory, staging area, and repository
- [ ] Write good commit messages following best practices
