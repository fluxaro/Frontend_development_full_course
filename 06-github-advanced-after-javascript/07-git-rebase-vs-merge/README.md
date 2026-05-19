# 07 — git rebase vs merge

## What Is This Lesson About?

Both `rebase` and `merge` integrate changes from one branch into another, but they produce different commit histories.

---

## git merge

Creates a merge commit that ties together the histories of both branches:

```
Before:
main:    A → B → C
feature:     B → D → E

After merge:
main:    A → B → C → M (merge commit)
                 ↗
feature:     D → E
```

```bash
git switch main
git merge feature/navbar
```

**Pros:** Preserves complete history, non-destructive  
**Cons:** Can create a messy history with many merge commits

---

## git rebase

Moves your branch's commits to start from the tip of another branch — replays them one by one:

```
Before:
main:    A → B → C
feature:     B → D → E

After rebase:
main:    A → B → C
feature:         C → D' → E' (new commits)
```

```bash
git switch feature/navbar
git rebase main
```

**Pros:** Clean, linear history  
**Cons:** Rewrites commit history — never rebase shared branches

---

## Interactive Rebase

Lets you edit, squash, reorder, or drop commits:

```bash
git rebase -i HEAD~3  # edit last 3 commits

# In the editor:
pick abc1234 Add navbar HTML
squash def5678 Fix typo in navbar  # squash into previous
pick ghi9012 Add navbar CSS
```

---

## Golden Rule of Rebase

**Never rebase commits that have been pushed to a shared branch.**

Rebase rewrites history. If others have based work on those commits, their history diverges.

---

## When to Use Each

| | Merge | Rebase |
|---|---|---|
| Shared branches | ✅ | ❌ |
| Local feature branches | ✅ | ✅ |
| Preserves history | ✅ | ❌ (rewrites) |
| Clean linear history | ❌ | ✅ |

---

## Common Mistakes

- Rebasing a branch that others are working on
- Not resolving conflicts during rebase (use `git rebase --continue`)
- Using `git rebase --abort` when you get confused (safe to abort)
