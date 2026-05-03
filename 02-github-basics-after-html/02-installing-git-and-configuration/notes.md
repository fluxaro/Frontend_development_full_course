# Notes — Git Installation & Configuration Cheat Sheet

## Installation Commands by OS

### macOS
```bash
# Option 1: Homebrew (recommended)
brew install git

# Option 2: Xcode tools
xcode-select --install

# Verify
git --version
```

### Windows
```
# Download from: https://git-scm.com/download/win
# Or via winget:
winget install --id Git.Git -e --source winget
```

### Linux (Ubuntu/Debian)
```bash
sudo apt update && sudo apt install git
```

### Linux (Fedora)
```bash
sudo dnf install git
```

---

## Configuration Commands

```bash
# Set your name (appears in commits)
git config --global user.name "Your Name"

# Set your email (use same as GitHub)
git config --global user.email "you@example.com"

# Set default branch name
git config --global init.defaultBranch main

# Set default editor (VS Code)
git config --global core.editor "code --wait"

# Set default editor (nano - simpler)
git config --global core.editor "nano"

# View all settings
git config --list

# View a specific setting
git config user.name
git config user.email

# Edit config file directly
git config --global --edit
```

---

## Config Scope Levels

| Flag | Scope | Config file location |
|---|---|---|
| `--global` | Your user account | `~/.gitconfig` |
| `--local` | Current repo only | `.git/config` |
| `--system` | All users on machine | `/etc/gitconfig` |

Most of the time you want `--global`.

---

## SSH Key Setup (Step by Step)

```bash
# 1. Generate key pair
ssh-keygen -t ed25519 -C "you@example.com"

# 2. Start SSH agent
eval "$(ssh-agent -s)"

# 3. Add private key to agent
ssh-add ~/.ssh/id_ed25519

# 4. Copy public key to clipboard
cat ~/.ssh/id_ed25519.pub          # Linux: copy manually
cat ~/.ssh/id_ed25519.pub | pbcopy # macOS
cat ~/.ssh/id_ed25519.pub | clip   # Windows Git Bash

# 5. Add to GitHub: Settings → SSH Keys → New SSH Key

# 6. Test connection
ssh -T git@github.com
```

**Success message:**
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

---

## SSH vs HTTPS

| | SSH | HTTPS |
|---|---|---|
| **Setup** | More steps upfront | Easier initially |
| **Daily use** | No password needed | May prompt for credentials |
| **Security** | Key-based (very secure) | Token-based |
| **Recommended?** | ✅ Yes | Works fine too |

**SSH remote URL format:** `git@github.com:username/repo.git`  
**HTTPS remote URL format:** `https://github.com/username/repo.git`

---

## Common Setup Issues

### "git: command not found"
Git isn't installed or not in your PATH.
- Reinstall Git
- On Mac: run `xcode-select --install`
- On Windows: make sure you're using Git Bash, not regular Command Prompt

### "Permission denied (publickey)"
SSH key isn't set up correctly.
- Check that you added the `.pub` key (not the private key) to GitHub
- Run `ssh-add ~/.ssh/id_ed25519` again
- Run `ssh -T git@github.com` to test

### "Could not open a connection to your authentication agent"
SSH agent isn't running.
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### Commits show wrong name/email
You configured with `--local` instead of `--global`, or you're in a repo with local overrides.
```bash
git config --global user.name "Correct Name"
git config --global user.email "correct@email.com"
```

### On Windows: `eval "$(ssh-agent -s)"` fails
Try running in Git Bash (not PowerShell or CMD), or use:
```bash
ssh-agent bash
ssh-add ~/.ssh/id_ed25519
```

---

## Useful Git Config Aliases

```bash
# Short status
git config --global alias.st status

# Short log
git config --global alias.lg "log --oneline --graph --decorate"

# Undo last commit (keep changes)
git config --global alias.undo "reset HEAD~1 --mixed"
```

After setting aliases, you can use `git st` instead of `git status`, etc.

---

## Where Config Files Live

```
~/.gitconfig          ← global config (your user)
~/.ssh/id_ed25519     ← private SSH key (NEVER share this)
~/.ssh/id_ed25519.pub ← public SSH key (safe to share)
.git/config           ← local repo config (inside each project)
```

---

## Quick Verification Checklist

Run these commands and verify the output:

```bash
git --version          # Should show 2.x.x
git config user.name   # Should show your name
git config user.email  # Should show your email
ssh -T git@github.com  # Should show "Hi username!"
```
