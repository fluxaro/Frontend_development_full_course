# 06 — git remote, add origin, and push

## Overview

You have a local Git repo with commits. You have a GitHub repo waiting online. Now you need to connect them and send your code up. This lesson covers remotes, `git remote add origin`, and `git push`.

---

## What is a Remote?

A **remote** is a version of your repository stored somewhere else — usually on GitHub. It's the online counterpart to your local repo.

- Your local repo lives on your computer
- The remote repo lives on GitHub's servers
- They are separate — changes in one don't automatically appear in the other
- You **push** to send local changes to the remote
- You **pull** to get remote changes to your local machine

---

## The Name "origin"

When you add a remote, you give it a name. By convention, the main remote is always called **origin**.

- `origin` is just a nickname for the remote URL
- You could name it anything, but `origin` is the universal standard
- When you see `origin` in Git commands, it means "the main remote repository"

---

## git remote — Managing Remotes

### View your remotes

```bash
git remote -v
```

**Output:**
```
origin  git@github.com:username/my-portfolio.git (fetch)
origin  git@github.com:username/my-portfolio.git (push)
```

The `-v` flag shows the full URL. You see two lines per remote — one for fetch (pull) and one for push.

### Add a remote

```bash
git remote add origin git@github.com:username/repo-name.git
```

This tells Git: "The remote named `origin` is at this URL."

### Remove a remote

```bash
git remote remove origin
```

### Rename a remote

```bash
git remote rename origin upstream
```

### Change a remote's URL

```bash
git remote set-url origin git@github.com:username/new-repo-name.git
```

---

## git push — Send Commits to GitHub

### First push (set upstream)

```bash
git push -u origin main
```

The `-u` flag sets the **upstream** — it tells Git that your local `main` branch should track the remote `main` branch. You only need `-u` the first time.

After this, you can just run `git push` without specifying the remote and branch.

### Subsequent pushes

```bash
git push
```

That's it. Git knows where to push because you set the upstream with `-u`.

### Push a specific branch

```bash
git push origin feature/dark-mode
```

### Push all branches

```bash
git push --all origin
```

---

## The Full Workflow: Local Repo → GitHub

Here's the complete process for connecting a local repo to GitHub for the first time:

```bash
# Step 1: Make sure you have commits locally
git log --oneline

# Step 2: Create a repo on GitHub (don't initialize with README)
# (Do this on github.com)

# Step 3: Add the remote
git remote add origin git@github.com:username/repo-name.git

# Step 4: Rename branch to main (if needed)
git branch -M main

# Step 5: Push with upstream flag
git push -u origin main
```

After this, your code is on GitHub. For future changes:

```bash
# Make changes to files
git add .
git commit -m "Describe what you changed"
git push
```

---

## Local vs Remote — Understanding the Difference

```
Your Computer                    GitHub
─────────────────                ─────────────────
Local Repository                 Remote Repository
                                 (origin)
  Commit A                         Commit A
  Commit B        git push →       Commit B
  Commit C        ──────────►      Commit C
  Commit D                         (not here yet)
```

After `git push`:
```
Your Computer                    GitHub
─────────────────                ─────────────────
  Commit A                         Commit A
  Commit B                         Commit B
  Commit C                         Commit C
  Commit D        ──────────►      Commit D ✅
```

---

## Common Push Errors

### "rejected — non-fast-forward"
```
! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'origin'
hint: Updates were rejected because the remote contains work that you do not have locally.
```

**Cause:** Someone else (or you on another machine) pushed commits that you don't have locally.  
**Fix:** Pull first, then push:
```bash
git pull origin main
git push
```

### "remote: Repository not found"
**Cause:** Wrong URL, or you don't have access to the repo.  
**Fix:** Check the URL with `git remote -v` and verify you have access on GitHub.

### "Permission denied (publickey)"
**Cause:** SSH key isn't set up correctly.  
**Fix:** Check your SSH setup (see Lesson 02).

### "src refspec main does not match any"
**Cause:** Your local branch is named `master` but you're trying to push `main`.  
**Fix:**
```bash
git branch -M main
git push -u origin main
```

---

## HTTPS vs SSH Push URLs

When you copy the clone URL from GitHub, you can choose HTTPS or SSH:

**SSH (recommended):**
```
git@github.com:username/repo-name.git
```

**HTTPS:**
```
https://github.com/username/repo-name.git
```

If you set up SSH keys (Lesson 02), use SSH. If not, use HTTPS (you'll need a Personal Access Token as your password).

---

## Learning Objectives

By the end of this lesson you should be able to:

- [ ] Explain what a remote is
- [ ] Add a remote with `git remote add origin <url>`
- [ ] View remotes with `git remote -v`
- [ ] Push to GitHub with `git push -u origin main`
- [ ] Explain what the `-u` flag does
- [ ] Push subsequent commits with just `git push`
- [ ] Troubleshoot common push errors
