# 04 — Forking and Collaboration

## What Is This Lesson About?

Forking creates your own copy of someone else's repository. It's how open source contribution works — you fork, make changes, then submit a pull request to the original.

---

## Forking vs Cloning

| | Fork | Clone |
|---|---|---|
| Creates | A copy on GitHub | A local copy |
| Where | Your GitHub account | Your computer |
| Use for | Contributing to others' repos | Working on your own repos |

---

## Fork Workflow

```bash
# 1. Fork on GitHub (click Fork button)

# 2. Clone YOUR fork
git clone https://github.com/YOUR-USERNAME/repo-name.git

# 3. Add the original as "upstream"
git remote add upstream https://github.com/ORIGINAL-OWNER/repo-name.git

# 4. Verify remotes
git remote -v
# origin    https://github.com/YOUR-USERNAME/repo-name.git (fetch)
# upstream  https://github.com/ORIGINAL-OWNER/repo-name.git (fetch)

# 5. Create a feature branch
git switch -c fix/typo-in-readme

# 6. Make changes, commit, push to YOUR fork
git push origin fix/typo-in-readme

# 7. Open a PR from your fork to the original repo
```

---

## Keeping Your Fork Updated

```bash
# Fetch changes from the original
git fetch upstream

# Merge into your main
git switch main
git merge upstream/main

# Push to your fork
git push origin main
```

---

## Collaborating on a Shared Repo

```bash
# Add a collaborator (repo owner does this on GitHub)
# Settings → Collaborators → Add people

# Collaborator clones the repo
git clone https://github.com/owner/repo.git

# Each person works on their own branch
git switch -c feature/my-feature
# ... work ...
git push origin feature/my-feature
# Open PR on GitHub
```

---

## Common Mistakes

- Pushing directly to `main` on a shared repo
- Not adding `upstream` remote (can't sync with original)
- Forgetting to sync your fork before starting new work
- Opening a PR from `main` instead of a feature branch
