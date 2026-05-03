# Notes — git init, add, commit, status

## The Three Areas (Always Remember This)

```
Working Directory  →  git add  →  Staging Area  →  git commit  →  Repository
   (your files)                    (the index)                    (.git folder)
```

- **Working Directory:** Files you're actively editing
- **Staging Area:** Changes selected for the next commit
- **Repository:** Permanent history of all commits

---

## Commands Cheat Sheet

```bash
# Initialize a new repo
git init

# Check current status (use this constantly!)
git status

# Stage a specific file
git add filename.html

# Stage all changes in current directory
git add .

# Stage all changes everywhere
git add -A

# Commit staged changes with a message
git commit -m "Your message here"

# Stage all tracked files AND commit (skips staging step)
git commit -am "Your message here"

# View commit history
git log

# View compact commit history
git log --oneline

# Unstage a file (keep changes in working directory)
git restore --staged filename.html

# Discard changes in working directory (CAREFUL - can't undo!)
git restore filename.html
```

---

## git status — Reading the Output

### Untracked file (new file Git doesn't know about)
```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        newfile.html
```
→ Run `git add newfile.html`

### Modified file (tracked file with unsaved changes)
```
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
        modified:   index.html
```
→ Run `git add index.html`

### Staged file (ready to commit)
```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   index.html
```
→ Run `git commit -m "message"`

### Clean working tree (nothing to do)
```
nothing to commit, working tree clean
```
→ All changes are committed. 

---

## Commit Message Conventions

### Format
```
<type>: <short description>

[optional longer body]
```

### Common Types (optional but useful)
- `feat:` — New feature
- `fix:` — Bug fix
- `style:` — CSS/formatting changes
- `docs:` — Documentation changes
- `refactor:` — Code restructuring

### Rules
1. Use imperative mood: "Add" not "Added" or "Adding"
2. First line under 72 characters
3. Be specific about what changed
4. Capital first letter, no period at end

### Examples
```
✅ Add navigation bar to header
✅ Fix broken link in footer
✅ Update hero section background color
✅ Add contact form with email validation
✅ Remove unused CSS from about page

❌ update
❌ fix stuff
❌ changes
❌ wip
❌ asdfgh
```

---

## The Git Workflow Diagram

```
1. Edit files in your editor
         ↓
2. git status  (see what changed)
         ↓
3. git add .   (stage changes)
         ↓
4. git status  (verify what's staged)
         ↓
5. git commit -m "message"  (save snapshot)
         ↓
6. git status  (confirm clean working tree)
         ↓
7. Repeat from step 1
```

---

## Common Mistakes

### Mistake 1: Committing everything at once
```bash
# ❌ Bad - one giant commit with everything
git add .
git commit -m "add all files"

# ✅ Good - incremental commits
git add index.html
git commit -m "Add homepage structure"
git add about.html
git commit -m "Add about page"
```

### Mistake 2: Vague commit messages
```bash
# ❌ Bad
git commit -m "update"
git commit -m "fix"
git commit -m "stuff"

# ✅ Good
git commit -m "Update navigation links to use relative paths"
git commit -m "Fix typo in contact form label"
git commit -m "Add footer with social media links"
```

### Mistake 3: Running git init in the wrong place
```bash
# ❌ Don't run git init in your home directory or Desktop
cd ~
git init  # BAD - now your entire home folder is a repo!

# ✅ Run it inside your specific project folder
cd ~/projects/my-portfolio
git init  # GOOD
```

### Mistake 4: Forgetting to stage before committing
```bash
# This won't commit your changes if you forgot git add
git commit -m "Add new feature"
# Output: nothing to commit, working tree clean
```

---

## What the .git Folder Contains

```
.git/
├── HEAD          ← "You are here" pointer
├── config        ← Local repo settings
├── objects/      ← All your data (commits, files, trees)
├── refs/
│   └── heads/
│       └── main  ← Points to latest commit on main branch
└── index         ← The staging area
```

**Never manually edit files in `.git`** — you could break your repo.

---

## Quick Reference Card

| Situation | Command |
|---|---|
| Start tracking a folder | `git init` |
| See what's going on | `git status` |
| Stage one file | `git add filename` |
| Stage everything | `git add .` |
| Save a snapshot | `git commit -m "message"` |
| See commit history | `git log --oneline` |
| Unstage a file | `git restore --staged filename` |
| Discard file changes | `git restore filename` |
