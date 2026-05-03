# Notes — .gitignore

## Quick Reference

```gitignore
# Ignore a specific file
secret.txt

# Ignore all files with extension
*.log
*.env

# Ignore a folder
node_modules/
dist/

# Ignore a folder anywhere in the project
**/temp/

# Exception: do NOT ignore this file
!important.log

# Ignore files in a specific folder only
logs/*.log

# Ignore files in folder and all subfolders
logs/**/*.log
```

## Standard Frontend .gitignore

```gitignore
node_modules/
dist/
build/
.next/
.env
.env.local
.env.*.local
.DS_Store
Thumbs.db
.vscode/
.idea/
*.log
coverage/
.cache/
```

## Pattern Syntax

| Pattern | Matches |
|---|---|
| `*.log` | Any file ending in .log |
| `temp/` | The temp folder |
| `**/temp/` | temp folder anywhere |
| `!keep.log` | Exception — do not ignore |
| `doc/*.txt` | .txt in doc folder only |
| `doc/**/*.txt` | .txt in doc and subdirs |

## Untrack Already-Committed Files

```bash
# Untrack a file (keep on disk)
git rm --cached filename

# Untrack a folder
git rm --cached -r foldername/

# Then commit
git add .gitignore
git commit -m "Remove tracked files that should be ignored"
```

## Global .gitignore

```bash
# Create global gitignore
touch ~/.gitignore_global

# Configure Git to use it
git config --global core.excludesfile ~/.gitignore_global
```

Put OS-specific files here (.DS_Store, Thumbs.db) so you do not repeat them in every project.

## Common Mistakes

- Not adding `.gitignore` before the first commit
- Committing `node_modules/` (can be 100MB+)
- Committing `.env` files with API keys
- Forgetting the trailing `/` on folder names (without it, it also matches files)
- Adding `.gitignore` after already committing the files (must untrack them)
