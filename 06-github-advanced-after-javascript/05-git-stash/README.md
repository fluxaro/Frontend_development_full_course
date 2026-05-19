# 05 — git stash

## What Is This Lesson About?

`git stash` temporarily saves your uncommitted changes so you can switch branches or pull updates without losing your work.

---

## Basic Stash

```bash
# Save current changes (staged and unstaged)
git stash

# Save with a description
git stash push -m "WIP: navbar responsive styles"

# List all stashes
git stash list
# stash@{0}: WIP: navbar responsive styles
# stash@{1}: On main: half-done login form

# Apply the most recent stash (keeps it in stash list)
git stash apply

# Apply and remove from stash list
git stash pop

# Apply a specific stash
git stash apply stash@{1}
```

---

## Stash Untracked Files

```bash
# By default, stash doesn't include untracked files
git stash push -u  # include untracked files
git stash push -a  # include untracked AND ignored files
```

---

## Managing Stashes

```bash
# Show what's in a stash
git stash show stash@{0}
git stash show -p stash@{0}  # full diff

# Delete a specific stash
git stash drop stash@{0}

# Delete all stashes
git stash clear
```

---

## Practical Workflow

```bash
# You're working on feature/navbar when an urgent bug comes in

# 1. Stash your current work
git stash push -m "WIP: navbar dropdown"

# 2. Switch to main and create a hotfix branch
git switch main
git switch -c hotfix/login-crash

# 3. Fix the bug, commit, push, merge

# 4. Return to your feature
git switch feature/navbar
git stash pop  # restore your work
```

---

## Common Mistakes

- Forgetting you have stashes (use `git stash list` regularly)
- Stash conflicts when applying to a different branch
- Not using `-m` to describe stashes (hard to remember what's in them)
- Using stash as long-term storage (use branches instead)
