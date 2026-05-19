# 02 — Merging and Git Merge Conflicts

## What Is This Lesson About?

Merging combines changes from one branch into another. Conflicts happen when two branches change the same lines — Git needs your help to resolve them.

---

## Merging a Branch

```bash
# Switch to the branch you want to merge INTO
git checkout main

# Merge the feature branch
git merge feature/navbar

# If successful: fast-forward or merge commit created
```

---

## Fast-Forward vs Merge Commit

**Fast-forward** (no divergence — main hasn't moved):
```
main:    A → B
feature:     B → C → D
After merge: A → B → C → D (main)
```

**Merge commit** (both branches have new commits):
```
main:    A → B → C
feature:     B → D → E
After merge: A → B → C → M (merge commit)
                   ↗
                  D → E
```

---

## Resolving Conflicts

When Git can't auto-merge, it marks the conflict:

```
<<<<<<< HEAD (current branch — main)
const color = 'blue';
=======
const color = 'red';
>>>>>>> feature/navbar (incoming branch)
```

To resolve:
1. Edit the file — keep what you want, remove the markers
2. `git add` the resolved file
3. `git commit` to complete the merge

---

## Aborting a Merge

```bash
git merge --abort  # cancel and go back to pre-merge state
```

---

## Common Mistakes

- Merging into the wrong branch (always check `git branch` first)
- Leaving conflict markers in the code
- Not testing after resolving conflicts
- Committing without resolving all conflicts
