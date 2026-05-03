# Notes — git log and git diff Cheat Sheet

## git log — All the Flags

```bash
# Basic log (full details)
git log

# Compact one-line format
git log --oneline

# Visual graph of branches
git log --graph --oneline

# Show all branches
git log --all --oneline --graph

# Show last N commits
git log -5
git log -1

# Show commits by author
git log --author="Alex"

# Filter by date
git log --since="2024-01-01"
git log --since="1 week ago"
git log --since="yesterday"
git log --until="2024-06-01"

# Search commit messages
git log --grep="navigation"
git log --grep="fix"

# Show commits that changed a specific file
git log -- index.html

# Show stats (which files changed, how many lines)
git log --stat

# Show stats in compact form
git log --stat --oneline

# Custom format
git log --format="%h %an %s"
# %h = short hash, %an = author name, %s = subject (message)

# Combine flags
git log --oneline --graph --all --decorate
```

---

## git diff — All the Variations

```bash
# Changes in working directory (not yet staged)
git diff

# Changes in staging area (staged, not yet committed)
git diff --staged
git diff --cached   # same thing

# Compare two commits
git diff abc1234 def5678

# Compare commit to current state
git diff HEAD~1        # last commit vs current
git diff HEAD~3        # 3 commits ago vs current

# Compare specific file
git diff index.html
git diff HEAD~1 index.html

# Compare two commits for a specific file
git diff abc1234 def5678 -- index.html

# Show only file names that changed (no diff content)
git diff --name-only HEAD~1

# Show stats (lines added/removed)
git diff --stat HEAD~1
```

---

## git show — Inspect a Commit

```bash
# Show most recent commit
git show

# Show specific commit
git show a3f8d70

# Show commit relative to HEAD
git show HEAD~1    # one before current
git show HEAD~3    # three before current

# Show only the files that changed
git show --stat HEAD

# Show a specific file at a specific commit
git show HEAD~1:index.html
```

---

## Reading git diff Output

```diff
diff --git a/index.html b/index.html
index 3f4a2b1..8c9d0e2 100644
--- a/index.html          ← old version
+++ b/index.html          ← new version
@@ -10,7 +10,10 @@       ← line numbers: old file line 10, new file line 10
   <body>                 ← unchanged context line
     <h1>Hello</h1>       ← unchanged context line
-    <p>Old text</p>      ← REMOVED line (shown in red)
+    <p>New text</p>      ← ADDED line (shown in green)
+    <p>Extra line</p>    ← ADDED line (shown in green)
   </body>                ← unchanged context line
```

| Symbol | Color | Meaning |
|---|---|---|
| `-` | Red | Line was removed |
| `+` | Green | Line was added |
| ` ` | White/gray | Unchanged context |
| `@@` | Cyan | Hunk header (line numbers) |

---

## Understanding HEAD

`HEAD` is a pointer to your current position in the commit history. Usually it points to the latest commit on your current branch.

```
Commit A → Commit B → Commit C ← HEAD (you are here)
```

`HEAD~1` means "one commit before HEAD"  
`HEAD~3` means "three commits before HEAD"  
`HEAD^` is the same as `HEAD~1`

---

## Useful Combinations

```bash
# See everything that changed in the last commit
git show HEAD

# See what you're about to commit
git diff --staged

# See what changed since your last commit
git diff HEAD

# Find when a specific word was added
git log -S "search term" --oneline

# See the full history of one file
git log --follow -- filename.html

# See who changed each line of a file
git blame filename.html
```

---

## git log Format Placeholders

| Placeholder | Output |
|---|---|
| `%h` | Short commit hash |
| `%H` | Full commit hash |
| `%an` | Author name |
| `%ae` | Author email |
| `%ad` | Author date |
| `%s` | Subject (first line of message) |
| `%b` | Body (rest of message) |

Example:
```bash
git log --format="%h | %an | %s"
# Output: a3f8d70 | Alex Rivera | Add about.html
```

---

## Quick Reference

| Question | Command |
|---|---|
| What commits exist? | `git log --oneline` |
| What changed in the last commit? | `git show HEAD` |
| What have I changed but not staged? | `git diff` |
| What have I staged but not committed? | `git diff --staged` |
| What changed between two commits? | `git diff hash1 hash2` |
| When did this file last change? | `git log -- filename` |
| Who changed this line? | `git blame filename` |
