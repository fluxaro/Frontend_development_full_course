# Notes — git remote, add origin, and push

## Core Concept

A **remote** is a version of your repository stored somewhere else — usually on GitHub. Your local repo and the remote repo are separate. You manually sync them using `push` and `pull`.

---

## Key Commands

### View remotes
```bash
git remote -v
```
Shows all remotes and their URLs. The `-v` flag means "verbose" — shows the full URL.

### Add a remote
```bash
git remote add origin https://github.com/username/repo.git
```
Adds a remote named `origin` pointing to the given URL.

### Remove a remote
```bash
git remote remove origin
```

### Change a remote's URL
```bash
git remote set-url origin https://github.com/username/new-repo.git
```

---

## Pushing

### First push (set upstream)
```bash
git push -u origin main
```
The `-u` flag sets the upstream tracking branch. Only needed once.

### All subsequent pushes
```bash
git push
```
Works after you have set the upstream with `-u`.

### Push a specific branch
```bash
git push origin feature/my-feature
```

---

## The Full First-Time Workflow

```bash
# 1. Make sure you have commits
git log --oneline

# 2. Create repo on GitHub (no README)

# 3. Add the remote
git remote add origin git@github.com:username/repo.git

# 4. Rename branch to main if needed
git branch -M main

# 5. Push with upstream flag
git push -u origin main
```

---

## Common Errors and Fixes

| Error | Cause | Fix |
|---|---|---|
| `rejected — non-fast-forward` | Remote has commits you do not have | Run `git pull origin main` then `git push` |
| `Repository not found` | Wrong URL or no access | Check URL with `git remote -v` |
| `Permission denied (publickey)` | SSH key not set up | Set up SSH keys or use HTTPS |
| `src refspec main does not match any` | Local branch is named `master` | Run `git branch -M main` |

---

## SSH vs HTTPS

| Feature | SSH | HTTPS |
|---|---|---|
| URL format | `git@github.com:user/repo.git` | `https://github.com/user/repo.git` |
| Authentication | SSH key (set up once) | Username + Personal Access Token |
| Recommended? | Yes, once set up | Yes, easier to start with |

---

## What "origin" Means

`origin` is just a nickname for the remote URL. You could name it anything, but `origin` is the universal convention. When you see `origin` in Git commands, it means "the main remote repository."

---

## Common Mistakes

- Initializing GitHub repo with a README when you already have local commits (causes conflicts)
- Forgetting `-u` on the first push (future pushes will not know where to go)
- Pushing to the wrong branch
- Using the wrong URL format (SSH vs HTTPS)
- Not running `git branch -M main` when the local branch is named `master`
