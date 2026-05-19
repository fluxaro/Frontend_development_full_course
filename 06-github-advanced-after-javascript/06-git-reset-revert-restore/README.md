# 06 — git reset, revert, restore

## What Is This Lesson About?

Three commands for undoing changes — each with different scope and safety levels.

---

## git restore — Undo Working Directory Changes

Safe — only affects your working directory, not commits:

```bash
# Discard changes to a file (restore to last commit)
git restore index.html

# Discard all unstaged changes
git restore .

# Unstage a file (keep changes in working directory)
git restore --staged index.html
```

---

## git reset — Move HEAD and Branch Pointer

```bash
# Soft reset — undo commit, keep changes staged
git reset --soft HEAD~1

# Mixed reset (default) — undo commit, keep changes unstaged
git reset HEAD~1
git reset --mixed HEAD~1

# Hard reset — undo commit AND discard changes (DESTRUCTIVE)
git reset --hard HEAD~1

# Reset to a specific commit
git reset --hard abc1234
```

**Warning:** Never `reset --hard` on commits that have been pushed to a shared repo.

---

## git revert — Safe Undo for Shared History

Creates a new commit that undoes a previous commit — safe for shared branches:

```bash
# Revert the last commit
git revert HEAD

# Revert a specific commit
git revert abc1234

# Revert without opening editor
git revert HEAD --no-edit
```

---

## When to Use Each

| Command | Use when | Safe for shared? |
|---|---|---|
| `restore` | Discard working directory changes | ✅ |
| `reset --soft` | Undo commit, keep changes staged | ⚠️ Local only |
| `reset --mixed` | Undo commit, keep changes unstaged | ⚠️ Local only |
| `reset --hard` | Completely undo commits | ❌ Never on shared |
| `revert` | Undo a pushed commit | ✅ |

---

## Common Mistakes

- Using `reset --hard` on pushed commits (rewrites history, breaks teammates)
- Confusing `restore` (working directory) with `reset` (commits)
- Not using `revert` for shared branches
