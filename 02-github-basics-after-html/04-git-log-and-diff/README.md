# 04 — git log and git diff

## Overview

Once you have a commit history, you need tools to explore it. `git log` shows you the history of commits, and `git diff` shows you exactly what changed between versions. These are essential for understanding your project's evolution and debugging problems.

---

## git log — View Commit History

`git log` shows the full list of commits in reverse chronological order (newest first).

```bash
git log
```

**Example output:**
```
commit a3f8d70c2b1e4f9a8d7c6b5a4f3e2d1c0b9a8f7
Author: Alex Rivera <alex@example.com>
Date:   Mon Jan 15 14:32:18 2024 -0500

    Add about.html with bio and skills section

commit 9e2c7b6a1f0d3e8c7b6a5f4e3d2c1b0a9f8e7d6
Author: Alex Rivera <alex@example.com>
Date:   Mon Jan 15 11:15:42 2024 -0500

    Add style.css with base styles and color variables

commit 5a8d3c2b1e0f9a8d7c6b5a4f3e2d1c0b9a8f7e6
Author: Alex Rivera <alex@example.com>
Date:   Sun Jan 14 16:45:30 2024 -0500

    Initial commit: add project folder and README
```

Each commit shows:
- **Commit hash** — a unique 40-character identifier (SHA-1)
- **Author** — who made the commit
- **Date** — when it was committed
- **Message** — what was changed

---

## git log Flags

### `--oneline` — Compact view

```bash
git log --oneline
```

```
a3f8d70 Add about.html with bio and skills section
9e2c7b6 Add style.css with base styles and color variables
5a8d3c2 Initial commit: add project folder and README
```

Shows just the short hash (first 7 characters) and the commit message. Much easier to read.

### `--graph` — Visual branch diagram

```bash
git log --graph --oneline
```

```
* a3f8d70 Add about.html with bio and skills section
* 9e2c7b6 Add style.css with base styles and color variables
* 5a8d3c2 Initial commit: add project folder and README
```

The `*` characters form a visual graph. More useful when you have branches.

### `--all` — Show all branches

```bash
git log --all --oneline --graph
```

### `-n` — Limit number of commits

```bash
git log -5           # Show last 5 commits
git log -1           # Show only the most recent commit
```

### `--author` — Filter by author

```bash
git log --author="Alex"
```

### `--since` and `--until` — Filter by date

```bash
git log --since="2024-01-01"
git log --since="1 week ago"
git log --since="yesterday"
```

### `--grep` — Search commit messages

```bash
git log --grep="navigation"
```

### `-- filename` — Show commits that touched a file

```bash
git log -- index.html
```

### Combining flags

```bash
git log --oneline --graph --all --decorate
```

---

## git diff — See What Changed

`git diff` shows the exact line-by-line differences between versions of your files.

### Compare working directory to staging area

```bash
git diff
```

Shows changes you've made but haven't staged yet.

### Compare staging area to last commit

```bash
git diff --staged
# or
git diff --cached
```

Shows changes you've staged but haven't committed yet.

### Compare two commits

```bash
git diff abc1234 def5678
```

### Compare a commit to the current state

```bash
git diff HEAD~1        # Compare last commit to the one before it
git diff HEAD~3        # Compare 3 commits ago to current
```

### Compare a specific file

```bash
git diff index.html
git diff HEAD~1 index.html
```

---

## Reading git diff Output

```diff
diff --git a/index.html b/index.html
index 3f4a2b1..8c9d0e2 100644
--- a/index.html
+++ b/index.html
@@ -10,7 +10,10 @@
   <body>
     <h1>Hello, Git!</h1>
     <p>This is my first version-controlled project.</p>
+    <p>I just added this new paragraph.</p>
+    <ul>
+      <li>Version control is useful</li>
+    </ul>
   </body>
 </html>
```

| Symbol | Meaning |
|---|---|
| `---` | The old version of the file |
| `+++` | The new version of the file |
| `-` (red) | Lines that were removed |
| `+` (green) | Lines that were added |
| ` ` (no symbol) | Lines that didn't change (context) |
| `@@` | Shows which line numbers the change is at |

---

## git show — Inspect a Specific Commit

`git show` displays the details of a specific commit — what changed and the diff.

```bash
# Show the most recent commit
git show

# Show a specific commit by hash
git show a3f8d70

# Show a commit relative to HEAD
git show HEAD~1    # One commit before current
git show HEAD~3    # Three commits before current
```

---

## Practical Use Cases

### "What did I change since my last commit?"
```bash
git diff
```

### "What am I about to commit?"
```bash
git diff --staged
```

### "What changed in the last commit?"
```bash
git show HEAD
# or
git diff HEAD~1 HEAD
```

### "When did this file last change?"
```bash
git log -- filename.html
```

### "What did this specific commit change?"
```bash
git show a3f8d70
```

### "What changed between two points in time?"
```bash
git diff HEAD~5 HEAD
```

---

## Learning Objectives

By the end of this lesson you should be able to:

- [ ] View commit history with `git log`
- [ ] Use `git log --oneline` for a compact view
- [ ] Use `git log --graph` to visualize branches
- [ ] Filter log output with flags like `--author`, `--since`, `--grep`
- [ ] Use `git diff` to see unstaged changes
- [ ] Use `git diff --staged` to see staged changes
- [ ] Read and interpret `git diff` output (+ and - lines)
- [ ] Use `git show` to inspect a specific commit
