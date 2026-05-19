# 01 — Branching: git branch and git checkout

## What Is This Lesson About?

Branches let you work on features or fixes in isolation without affecting the main codebase. This is how professional teams collaborate on code.

---

## What is a Branch?

A branch is a pointer to a specific commit. The default branch is usually `main`. When you create a new branch, you get an independent line of development.

```
main:    A → B → C
feature:         C → D → E
```

---

## Creating and Switching Branches

```bash
# List all branches (* = current)
git branch

# Create a new branch
git branch feature/navbar

# Switch to a branch
git checkout feature/navbar

# Create AND switch in one command (modern)
git switch -c feature/navbar

# Switch to existing branch
git switch main
git checkout main
```

---

## Branch Naming Conventions

```bash
feature/user-authentication
feature/shopping-cart
fix/login-bug
fix/navbar-overflow
hotfix/security-patch
chore/update-dependencies
docs/api-documentation
```

---

## Viewing Branches

```bash
git branch          # local branches
git branch -r       # remote branches
git branch -a       # all branches
git branch -v       # with last commit
```

---

## Deleting Branches

```bash
git branch -d feature/navbar    # delete (safe — won't delete unmerged)
git branch -D feature/navbar    # force delete
git push origin --delete feature/navbar  # delete remote branch
```

---

## Common Mistakes

- Working directly on `main` instead of a feature branch
- Not pulling latest `main` before creating a new branch
- Using vague branch names like `fix` or `test`
- Forgetting to switch branches before making changes
