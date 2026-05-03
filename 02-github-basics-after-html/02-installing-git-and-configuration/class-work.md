# Class Work — Git Setup Walkthrough

## Goal

By the end of this class work session, Git will be installed, configured, and ready to use on your computer. Work through each step in order and don't skip ahead.

**Time:** 30–45 minutes  
**Ask for help** if you get stuck — setup issues are common and fixable.

---

## Step 1 — Install Git

Follow the instructions for your operating system from the README.

After installing, open your terminal:
- **Mac:** Applications → Utilities → Terminal (or press Cmd+Space and type "terminal")
- **Windows:** Search for "Git Bash" in the Start menu
- **Linux:** Open your terminal application

Run this command:

```bash
git --version
```

**Expected output:** Something like `git version 2.43.0`

✅ **Checkpoint:** Can you see a version number? If yes, move on. If not, raise your hand.

---

## Step 2 — Configure Your Name and Email

Run these two commands, replacing the values with your actual name and email:

```bash
git config --global user.name "Jane Smith"
git config --global user.email "jane@example.com"
```

**Important:** Use the same email you'll use for GitHub.

Verify it worked:

```bash
git config user.name
git config user.email
```

**Expected output:** Your name and email printed on separate lines.

✅ **Checkpoint:** Do you see your name and email? Good.

---

## Step 3 — Set the Default Branch to `main`

```bash
git config --global init.defaultBranch main
```

This ensures new repos use `main` instead of the older `master` name.

---

## Step 4 — Set Your Default Editor (Optional but Recommended)

If you use VS Code:

```bash
git config --global core.editor "code --wait"
```

If you prefer a simpler terminal editor:

```bash
git config --global core.editor "nano"
```

---

## Step 5 — Verify All Your Config Settings

```bash
git config --list
```

You should see output that includes:
```
user.name=Your Name
user.email=your@email.com
init.defaultbranch=main
```

Write down what you see. You'll refer to this later.

✅ **Checkpoint:** Can you see your name, email, and default branch in the list?

---

## Step 6 — Create a GitHub Account (if you haven't already)

1. Go to https://github.com
2. Click "Sign up"
3. Use the same email you configured in Step 2
4. Choose a username you're happy with — this is your developer identity
5. Verify your email

✅ **Checkpoint:** Are you logged into GitHub?

---

## Step 7 — Generate an SSH Key

In your terminal, run:

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

When it asks:
- **"Enter file in which to save the key"** → Press Enter (use the default location)
- **"Enter passphrase"** → Press Enter (no passphrase for now, or add one if you want)
- **"Enter same passphrase again"** → Press Enter

You should see output like:
```
Your identification has been saved in /Users/you/.ssh/id_ed25519
Your public key has been saved in /Users/you/.ssh/id_ed25519.pub
```

✅ **Checkpoint:** Did you see the key fingerprint output?

---

## Step 8 — Add the SSH Key to the Agent

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

**Windows (Git Bash):** If `eval "$(ssh-agent -s)"` doesn't work, try:
```bash
ssh-agent bash
ssh-add ~/.ssh/id_ed25519
```

---

## Step 9 — Copy Your Public Key

**Mac:**
```bash
cat ~/.ssh/id_ed25519.pub | pbcopy
```

**Linux:**
```bash
cat ~/.ssh/id_ed25519.pub
```
Then manually select and copy the output.

**Windows (Git Bash):**
```bash
cat ~/.ssh/id_ed25519.pub | clip
```

Your public key is now in your clipboard. It looks like:
```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAA... your@email.com
```

---

## Step 10 — Add the Key to GitHub

1. Go to https://github.com/settings/keys
2. Click **"New SSH key"**
3. Title: "My Laptop" (or whatever describes this computer)
4. Key type: Authentication Key
5. Paste your public key in the "Key" field
6. Click **"Add SSH key"**

✅ **Checkpoint:** Can you see your key listed on the SSH keys page?

---

## Step 11 — Test the SSH Connection

```bash
ssh -T git@github.com
```

You may see a warning the first time:
```
The authenticity of host 'github.com' can't be established.
Are you sure you want to continue connecting? (yes/no)?
```

Type `yes` and press Enter.

**Expected output:**
```
Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.
```

✅ **Checkpoint:** Did you see the success message with your username?

---

## 🎉 You're Set Up!

If you completed all 11 steps, your Git environment is fully configured. Here's a summary of what you did:

| Step | What You Did |
|---|---|
| 1 | Installed Git |
| 2 | Configured your name and email |
| 3 | Set default branch to `main` |
| 4 | Set your default editor |
| 5 | Verified all config settings |
| 6 | Created a GitHub account |
| 7 | Generated an SSH key pair |
| 8 | Added key to SSH agent |
| 9 | Copied your public key |
| 10 | Added public key to GitHub |
| 11 | Tested the SSH connection |

---

## Troubleshooting

**"git: command not found"**
→ Git isn't installed or isn't in your PATH. Try reinstalling.

**SSH test shows "Permission denied (publickey)"**
→ The key wasn't added to GitHub correctly. Check that you copied the `.pub` file (not the private key).

**"Could not open a connection to your authentication agent"**
→ Run `eval "$(ssh-agent -s)"` again before `ssh-add`.

**On Windows, `pbcopy` doesn't work**
→ Use `clip` instead, or open the file in VS Code and copy manually.
