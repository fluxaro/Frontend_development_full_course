# Notes — git clone and git pull

## Quick Reference

### Clone a repository
```bash
git clone https://github.com/username/repo.git
```

### Clone into a specific folder
```bash
git clone https://github.com/username/repo.git my-folder-name
```

### Pull latest changes
```bash
git pull
```

### Pull from a specific remote and branch
```bash
git pull origin main
```

### Fetch without merging
```bash
git fetch origin
```

---

## git clone vs git pull

| | git clone | git pull |
|---|---|---|
| When to use | First time downloading a repo | Updating an existing local repo |
| Creates new folder? | Yes | No |
| Sets up remote? | Yes, automatically | No (already set up) |
| Requires existing local repo? | No | Yes |

---

## git pull = git fetch + git merge

```bash
git pull
# is the same as:
git fetch origin
git merge origin/main
```

`git fetch` downloads new commits but does not change your files.
`git merge` applies those commits to your current branch.

---

## Common Scenarios

**Starting a new job:**
```bash
git clone https://github.com/company/project.git
cd project
```

**Starting work each morning:**
```bash
git pull
```

**Before pushing your changes:**
```bash
git pull
git push
```

---

## Common Errors

| Error | Cause | Fix |
|---|---|---|
| `fatal: repository not found` | Wrong URL or no access | Check the URL and your permissions |
| `Already up to date` | No new commits on remote | Nothing to do — you are current |
| `CONFLICT` | Remote and local changed the same file | Resolve the merge conflict manually |
| `Please commit or stash your changes` | You have uncommitted changes | Commit or stash before pulling |

---

## Key Terms

**Clone:** Download a complete copy of a remote repository to your computer.

**Pull:** Download new commits from the remote and merge them into your current branch.

**Fetch:** Download new commits from the remote without merging them.

**Upstream:** The remote branch that your local branch tracks.

**Fast-forward:** A merge where no conflicts exist — Git simply moves the branch pointer forward.
