# Notes — Git vs GitHub Cheat Sheet

## The One-Line Difference

> **Git** = the tool on your computer that tracks changes  
> **GitHub** = the website that stores your Git repos online

---

## Key Terms Quick Reference

| Term | Simple Definition | Example |
|---|---|---|
| **Repository (repo)** | A project folder tracked by Git | Your `my-portfolio` folder |
| **Commit** | A saved snapshot of your changes | "Added navigation bar" |
| **Branch** | A parallel version of your project | `feature/dark-mode` |
| **Merge** | Combining one branch into another | Merging `feature/dark-mode` into `main` |
| **Push** | Sending local commits → GitHub | `git push origin main` |
| **Pull** | Getting GitHub changes → local machine | `git pull origin main` |
| **Clone** | Downloading a GitHub repo to your computer | `git clone <url>` |
| **Fork** | Making your own copy of someone else's repo | Forking `facebook/react` |
| **Remote** | A version of your repo stored online | GitHub is a remote |
| **Origin** | The default name for your remote | Usually points to your GitHub repo |
| **HEAD** | A pointer to your current position in history | Usually points to latest commit |
| **Staging area** | Where you prepare changes before committing | After `git add`, before `git commit` |

---

## Git vs GitHub Side-by-Side

```
GIT                          GITHUB
────────────────────         ────────────────────
Software you install         Website you visit
Runs on your computer        Runs in the cloud
Works offline                Requires internet
Tracks file changes          Hosts repositories
Free & open source           Free (with paid tiers)
Command line tool            Web interface + API
Created 2005                 Founded 2008
By Linus Torvalds            By Tom Preston-Werner et al.
Alternatives: Mercurial      Alternatives: GitLab, Bitbucket
```

---

## Common Misconceptions

### ❌ "Git and GitHub are the same thing"
**Reality:** Git is the version control software. GitHub is a hosting service that uses Git. You can use Git without GitHub. You cannot use GitHub without Git.

### ❌ "You need GitHub to use Git"
**Reality:** Git works completely offline on your local machine. GitHub is optional — it's just a convenient place to back up and share your repos.

### ❌ "GitHub owns your code"
**Reality:** GitHub hosts your code, but you own it. You can delete your repos, move them to another service, or keep them private.

### ❌ "Committing saves your code to GitHub"
**Reality:** Committing saves a snapshot locally (in your Git repo on your computer). You need to `git push` to send it to GitHub.

### ❌ "You should commit every time you save a file"
**Reality:** Commits should represent meaningful, logical units of work. Commit when you've completed a feature, fixed a bug, or reached a stable point — not every time you hit Ctrl+S.

---

## The Version Control Timeline

```
You write code
      ↓
git add (stage your changes)
      ↓
git commit (save a local snapshot)
      ↓
git push (send to GitHub)
      ↓
GitHub stores it safely in the cloud
```

---

## Why Version Control Matters

1. **Undo anything** — Go back to any previous version of your code
2. **See the history** — Know exactly what changed and when
3. **Collaborate safely** — Multiple people can work without overwriting each other
4. **Experiment freely** — Try new ideas in branches without risk
5. **Deploy easily** — Many hosting services deploy directly from GitHub
6. **Build your portfolio** — GitHub is your public coding resume

---

## Alternatives to GitHub

| Service | URL | Notes |
|---|---|---|
| **GitLab** | gitlab.com | Open source, can self-host |
| **Bitbucket** | bitbucket.org | Popular with Jira/Atlassian users |
| **Gitea** | gitea.io | Lightweight, self-hosted |
| **Azure DevOps** | dev.azure.com | Microsoft's enterprise option |

---

## Things to Remember

- Git ≠ GitHub (say this 10 times)
- A commit is a snapshot, not a save
- Push = local → remote (GitHub)
- Pull = remote (GitHub) → local
- Clone = first-time download of a repo
- Fork = your own copy of someone else's repo on GitHub
