# 07 — git clone and git pull

## What Is This Lesson About?

You already know how to create a local repo and push it to GitHub. Now you will learn how to go the other direction — how to download a repository from GitHub to your computer, and how to keep your local copy up to date when changes happen on GitHub.

---

## git clone — Download a Repository

`git clone` downloads a complete copy of a remote repository to your computer. It copies every file, every commit, and the full history.

```bash
git clone https://github.com/username/repo-name.git
```

This creates a new folder called `repo-name` in your current directory, containing everything from the repository.

### What clone does automatically

When you clone a repository, Git automatically:
- Downloads all files and the full commit history
- Sets up the remote named `origin` pointing to the URL you cloned from
- Checks out the default branch (usually `main`)

So after cloning, you can immediately run `git push` and `git pull` without any extra setup.

### Clone into a specific folder name

```bash
git clone https://github.com/username/repo-name.git my-project
```

This clones into a folder called `my-project` instead of `repo-name`.

---

## git pull — Get the Latest Changes

`git pull` downloads new commits from the remote repository and merges them into your current branch.

```bash
git pull
```

Or more explicitly:

```bash
git pull origin main
```

### When to use git pull

- Before starting work each day — get the latest changes from your team
- Before pushing — make sure you have the latest version to avoid conflicts
- After someone else pushes changes to the shared repository

### What git pull actually does

`git pull` is a combination of two commands:

```bash
git fetch    # Download new commits from remote (does not change your files)
git merge    # Merge the downloaded commits into your current branch
```

---

## Clone vs Fork vs Pull

These three things sound similar but are different:

| Action | What It Does | When to Use |
|---|---|---|
| `git clone` | Downloads a repo to your computer | Starting work on any project |
| Fork (GitHub) | Creates your own copy of someone else's repo on GitHub | Contributing to open source |
| `git pull` | Downloads new commits into an existing local repo | Keeping your local copy up to date |

---

## Real-World Example

Here is a typical workflow when joining a team project:

```bash
# Day 1: Clone the project
git clone https://github.com/team/project.git
cd project

# Day 2: Before starting work, get the latest changes
git pull

# Make your changes
# ... edit files ...

# Commit and push
git add .
git commit -m "Add new feature"
git push
```

---

## Why This Matters

Every professional developer uses `git clone` and `git pull` every single day. When you start a new job, the first thing you do is clone the company's repository. Every morning, you pull the latest changes before starting work.
