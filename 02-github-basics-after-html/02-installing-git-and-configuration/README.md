# 02 — Installing Git and Configuration

## Overview

Before you can use Git, you need to install it and tell it who you are. This lesson walks through the full setup process on any operating system.

---

## Installing Git

### macOS

**Option 1 — Homebrew (recommended):**
```bash
brew install git
```

**Option 2 — Xcode Command Line Tools:**
```bash
xcode-select --install
```
A dialog will appear asking you to install the tools. Click Install.

**Option 3 — Download the installer:**
Go to https://git-scm.com/download/mac and download the `.dmg` file.

---

### Windows

**Option 1 — Git for Windows (recommended):**
1. Go to https://git-scm.com/download/win
2. Download the installer (it auto-detects 32/64-bit)
3. Run the installer — the defaults are fine for most settings
4. When asked about the default editor, choose VS Code if you have it
5. When asked about line endings, choose "Checkout Windows-style, commit Unix-style"

This installs **Git Bash** — a terminal that lets you use Git commands on Windows.

**Option 2 — winget:**
```bash
winget install --id Git.Git -e --source winget
```

---

### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git
```

### Linux (Fedora/RHEL)

```bash
sudo dnf install git
```

---

## Verify the Installation

After installing, open your terminal (or Git Bash on Windows) and run:

```bash
git --version
```

You should see something like:
```
git version 2.43.0
```

Any version 2.x is fine. If you see "command not found", Git isn't installed correctly.

---

## Configure Git — Tell It Who You Are

Git needs to know your name and email so it can attach them to your commits. This is how collaborators know who made each change.

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

**Important:** Use the same email address you'll use for your GitHub account.

### Set the Default Branch Name

Modern Git uses `main` as the default branch name (older versions used `master`). Set it to `main`:

```bash
git config --global init.defaultBranch main
```

### Set Your Default Editor

Tell Git which editor to open when you need to write a commit message:

```bash
# VS Code
git config --global core.editor "code --wait"

# Nano (simple terminal editor)
git config --global core.editor "nano"
```

---

## Verify Your Configuration

See all your Git settings:

```bash
git config --list
```

Check a specific setting:

```bash
git config user.name
git config user.email
```

---

## SSH Keys vs HTTPS

When you push code to GitHub, you need to authenticate. There are two ways:

### HTTPS
- Uses your GitHub username and password (or a Personal Access Token)
- Easier to set up initially
- You may be prompted for credentials each time

### SSH (Recommended)
- Uses a cryptographic key pair stored on your computer
- More secure
- Once set up, you never need to enter a password again

**How SSH works:**
1. You generate a key pair: a private key (stays on your computer) and a public key
2. You add the public key to your GitHub account
3. When you push, GitHub verifies your identity using the key pair

---

## Setting Up SSH Keys

### Step 1 — Generate a key pair

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

When prompted for a file location, press Enter to accept the default.
When prompted for a passphrase, you can press Enter for no passphrase (or add one for extra security).

### Step 2 — Add the key to the SSH agent

```bash
# Start the SSH agent
eval "$(ssh-agent -s)"

# Add your key
ssh-add ~/.ssh/id_ed25519
```

### Step 3 — Copy your public key

```bash
# macOS
cat ~/.ssh/id_ed25519.pub | pbcopy

# Linux
cat ~/.ssh/id_ed25519.pub

# Windows (Git Bash)
cat ~/.ssh/id_ed25519.pub | clip
```

### Step 4 — Add to GitHub

1. Go to GitHub → Settings → SSH and GPG keys
2. Click "New SSH key"
3. Give it a title (e.g., "My Laptop")
4. Paste your public key
5. Click "Add SSH key"

### Step 5 — Test the connection

```bash
ssh -T git@github.com
```

You should see:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

---

## Creating a GitHub Account

1. Go to https://github.com
2. Click "Sign up"
3. Choose a username (this will be public — choose wisely, it's your developer identity)
4. Enter your email and create a password
5. Verify your email address
6. Choose the free plan

**Username tips:**
- Use your real name or a professional handle
- Keep it short and memorable
- Avoid numbers and underscores if possible
- This will appear on your portfolio and resume

---

## Learning Objectives

By the end of this lesson you should be able to:

- [ ] Install Git on your operating system
- [ ] Verify Git is installed with `git --version`
- [ ] Configure your name and email with `git config`
- [ ] Set the default branch to `main`
- [ ] Explain the difference between SSH and HTTPS authentication
- [ ] Generate an SSH key and add it to GitHub
- [ ] Test your SSH connection with `ssh -T git@github.com`
