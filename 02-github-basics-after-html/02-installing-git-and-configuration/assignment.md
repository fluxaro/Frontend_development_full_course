# Assignment — Complete Git Setup Checklist

## Overview

Your task is to complete the full Git and GitHub setup and document each step. This is a practical assignment — you're actually doing the setup, not just reading about it.

**Submission:** A written document (text file, markdown, or notes) showing you completed each step.

---

## The Checklist

Work through each item. For each one, write a brief note confirming you completed it (or describe what you saw/did).

---

### Part 1 — Install Git

- [ ] **Install Git** on your computer using the method appropriate for your OS
- [ ] **Verify installation** by running `git --version` in your terminal
  - Write down the version number you see: `git version ___________`

---

### Part 2 — Configure Git

- [ ] **Set your name:**
  ```bash
  git config --global user.name "Your Name"
  ```
  
- [ ] **Set your email:**
  ```bash
  git config --global user.email "your@email.com"
  ```

- [ ] **Set default branch to main:**
  ```bash
  git config --global init.defaultBranch main
  ```

- [ ] **Set your editor** (choose one):
  ```bash
  git config --global core.editor "code --wait"
  ```

- [ ] **Verify all settings** with `git config --list`
  - Copy and paste the output into your submission document

---

### Part 3 — Create a GitHub Account

- [ ] **Create a GitHub account** at https://github.com (or confirm you already have one)
- [ ] **Verify your email** address with GitHub
- [ ] **Write down your GitHub username:** `@___________`
- [ ] **Set a profile picture** (optional but recommended for your portfolio)
- [ ] **Add a bio** to your GitHub profile (optional)

---

### Part 4 — Generate and Add an SSH Key

- [ ] **Generate an SSH key:**
  ```bash
  ssh-keygen -t ed25519 -C "your@email.com"
  ```

- [ ] **Start the SSH agent and add your key:**
  ```bash
  eval "$(ssh-agent -s)"
  ssh-add ~/.ssh/id_ed25519
  ```

- [ ] **Copy your public key** to clipboard

- [ ] **Add the public key to GitHub:**
  - Go to GitHub → Settings → SSH and GPG keys → New SSH key
  - Give it a descriptive title (e.g., "MacBook Pro 2024")
  - Paste the key and save

- [ ] **Confirm the key appears** in your GitHub SSH keys list

---

### Part 5 — Test the Connection

- [ ] **Test your SSH connection:**
  ```bash
  ssh -T git@github.com
  ```

- [ ] **Write down the response you got:**
  ```
  ___________________________________________
  ```

  Expected: `Hi username! You've successfully authenticated...`

---

## Documentation Requirements

Your submission should include:

1. **Your Git version** (from `git --version`)
2. **Your `git config --list` output** (copy-paste it)
3. **Your GitHub username**
4. **The response from `ssh -T git@github.com`**
5. **Any issues you ran into** and how you solved them (this is valuable — document your troubleshooting!)

---

## Bonus Challenges

- [ ] **Explore GitHub profile settings** — add a README to your profile (GitHub lets you create a special repo with your username that shows on your profile page)
- [ ] **Set up a GPG key** for signed commits (advanced — look up "GitHub GPG key setup")
- [ ] **Install GitHub CLI** (`gh`) and authenticate with `gh auth login`
- [ ] **Configure Git aliases** for common commands:
  ```bash
  git config --global alias.st status
  git config --global alias.co checkout
  git config --global alias.lg "log --oneline --graph"
  ```

---

## Grading Checklist

- [ ] Git installed and version documented
- [ ] Name and email configured correctly
- [ ] Default branch set to `main`
- [ ] `git config --list` output included
- [ ] GitHub account created and email verified
- [ ] SSH key generated and added to GitHub
- [ ] SSH connection test successful and output documented
- [ ] Any troubleshooting steps documented

---

## Notes

- If you're on a shared/school computer, you may need to redo the SSH setup on each machine you use
- Keep your private key (`~/.ssh/id_ed25519`) safe — never share it or commit it to a repo
- If you change computers, generate a new SSH key for the new machine and add it to GitHub
