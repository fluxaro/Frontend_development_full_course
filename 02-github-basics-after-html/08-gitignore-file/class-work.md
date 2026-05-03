# Class Work — Create a .gitignore File

## What You Will Do

Create a `.gitignore` file for your portfolio project, test that it works, and learn how to untrack files that were accidentally committed.

**Time:** 25 minutes

---

## Activity 1: Create a .gitignore File (10 minutes)

Navigate to your portfolio project folder:

```bash
cd ~/Desktop/html-portfolio
```

Create the `.gitignore` file:

```bash
touch .gitignore
```

Open it in VS Code and add these patterns:

```
# OS files
.DS_Store
Thumbs.db
desktop.ini

# Editor files
.vscode/
.idea/
*.swp
*~

# Logs
*.log
npm-debug.log*

# Environment variables (never commit these!)
.env
.env.local
.env.production

# Build output
dist/
build/
node_modules/

# Temporary files
*.tmp
*.temp
.cache/
```

Save the file.

---

## Activity 2: Test That .gitignore Works (10 minutes)

### Step 1 — Create files that should be ignored

```bash
touch .DS_Store
touch secret.env
mkdir node_modules
touch node_modules/test.js
```

### Step 2 — Check git status

```bash
git status
```

You should see `.gitignore` listed as a new file, but NOT `.DS_Store`, `secret.env`, or `node_modules/`.

If they are still showing, double-check your `.gitignore` patterns.

### Step 3 — Commit the .gitignore

```bash
git add .gitignore
git commit -m "Add .gitignore file"
```

### Step 4 — Clean up test files

```bash
rm .DS_Store
rm secret.env
rm -rf node_modules
```

---

## Activity 3: Untrack an Already-Committed File (5 minutes)

Simulate accidentally committing a file:

```bash
# Create and commit a file that should be ignored
touch accidental.log
git add accidental.log
git commit -m "Oops: accidentally committed a log file"
```

Now add `*.log` to `.gitignore` and untrack the file:

```bash
# Add *.log to .gitignore
echo "*.log" >> .gitignore

# Remove from Git tracking (but keep the file on disk)
git rm --cached accidental.log

# Commit the fix
git add .gitignore
git commit -m "Remove log file from tracking and update .gitignore"
```

Check that `accidental.log` still exists on disk but is no longer tracked:

```bash
ls accidental.log    # File still exists
git status           # File is not shown
```

---

## Checklist

- [ ] `.gitignore` file created in project root
- [ ] OS files (.DS_Store, Thumbs.db) are ignored
- [ ] Editor files (.vscode/) are ignored
- [ ] `.env` files are ignored
- [ ] `node_modules/` is ignored
- [ ] `git status` does not show ignored files
- [ ] `.gitignore` is committed to the repo
- [ ] Successfully untracked an accidentally committed file
