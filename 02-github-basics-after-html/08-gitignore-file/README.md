# 08 — The .gitignore File

## What Is This Lesson About?

Not every file in your project should be tracked by Git. Some files are generated automatically, contain sensitive information, or are specific to your machine. The `.gitignore` file tells Git which files and folders to ignore.

---

## Why You Need .gitignore

Without `.gitignore`, you might accidentally commit:
- `node_modules/` — thousands of dependency files (can be 100MB+)
- `.env` — environment variables with API keys and passwords
- `.DS_Store` — macOS metadata files
- `build/` or `dist/` — generated output files
- `.vscode/` — your personal editor settings

---

## Creating a .gitignore File

Create a file named exactly `.gitignore` (with the dot, no extension) in the root of your project:

```bash
touch .gitignore
```

Then add patterns — one per line:

```
# Dependencies
node_modules/

# Environment variables
.env
.env.local
.env.production

# Build output
dist/
build/
.next/

# OS files
.DS_Store
Thumbs.db

# Editor files
.vscode/
.idea/
*.swp
```

---

## .gitignore Pattern Syntax

| Pattern | What It Ignores |
|---|---|
| `node_modules/` | The node_modules folder |
| `*.log` | All files ending in .log |
| `*.env` | All files ending in .env |
| `build/` | The build folder |
| `!important.log` | Exception — do NOT ignore this file |
| `**/temp` | temp folder anywhere in the project |
| `doc/*.txt` | .txt files in the doc folder only |
| `doc/**/*.txt` | .txt files in doc and all subdirectories |

---

## Standard .gitignore for Frontend Projects

```gitignore
# Dependencies
node_modules/
.pnp
.pnp.js

# Environment variables
.env
.env.local
.env.development.local
.env.test.local
.env.production.local

# Build output
dist/
build/
.next/
out/

# OS files
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Editor files
.vscode/
.idea/
*.swp
*.swo
*~

# Logs
npm-debug.log*
yarn-debug.log*
yarn-error.log*
*.log

# Testing
coverage/
.nyc_output/

# Misc
.cache/
.parcel-cache/
```

---

## Untracking Already-Tracked Files

If you accidentally committed a file before adding it to `.gitignore`, you need to untrack it:

```bash
# Remove from Git tracking but keep the file on disk
git rm --cached filename

# Remove a folder from tracking
git rm --cached -r node_modules/

# Then commit the change
git commit -m "Remove node_modules from tracking"
```

---

## Global .gitignore

You can create a global `.gitignore` that applies to all your Git repos:

```bash
git config --global core.excludesfile ~/.gitignore_global
```

Put OS-specific files here (`.DS_Store`, `Thumbs.db`) so you do not have to add them to every project.
