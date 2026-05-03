# Class Work — Your First Git Repository

## Goal

You're going to create a real Git repository from scratch, make changes, and observe exactly what Git shows you at each step. Pay close attention to the output of `git status` — it changes at every step.

**Time:** 25–35 minutes

---

## Setup

Open your terminal and navigate to your Desktop or a folder where you keep projects:

```bash
# Mac/Linux
cd ~/Desktop

# Windows (Git Bash)
cd ~/Desktop
```

---

## Step 1 — Create a New Project Folder

```bash
mkdir my-first-git-project
cd my-first-git-project
```

You now have an empty folder. It is NOT a Git repo yet.

---

## Step 2 — Initialize Git

```bash
git init
```

**What you should see:**
```
Initialized empty Git repository in /path/to/my-first-git-project/.git/
```

Now run:
```bash
git status
```

**What you should see:**
```
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

📝 **Write down:** What does "No commits yet" mean?

---

## Step 3 — Create Your First File

Create an HTML file. You can use VS Code, nano, or any text editor:

```bash
# Using echo (quick way to create a file)
echo "<!DOCTYPE html><html><head><title>My Project</title></head><body><h1>Hello Git!</h1></body></html>" > index.html
```

Or open VS Code and create `index.html` manually with this content:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My First Git Project</title>
</head>
<body>
  <h1>Hello, Git!</h1>
  <p>This is my first version-controlled project.</p>
</body>
</html>
```

---

## Step 4 — Check Status (Before Adding)

```bash
git status
```

**What you should see:**
```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html

nothing added to commit but untracked files present (use "git add" to track)
```

📝 **Write down:** What does "Untracked files" mean? Why is `index.html` listed there?

---

## Step 5 — Stage the File

```bash
git add index.html
```

No output is normal — Git is quiet when things work.

Now run:
```bash
git status
```

**What you should see:**
```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   index.html
```

📝 **Write down:** What changed in the status output? What does "Changes to be committed" mean?

---

## Step 6 — Make Your First Commit

```bash
git commit -m "Initial commit: add index.html"
```

**What you should see:**
```
[main (root-commit) a1b2c3d] Initial commit: add index.html
 1 file changed, 10 insertions(+)
 create mode 100644 index.html
```

Now run:
```bash
git status
```

**What you should see:**
```
On branch main
nothing to commit, working tree clean
```

📝 **Write down:** What does "working tree clean" mean? Where did your file go?

---

## Step 7 — Make a Change and Observe

Open `index.html` and add a new paragraph:

```html
<p>I just learned how to make a commit!</p>
```

Save the file, then run:

```bash
git status
```

**What you should see:**
```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html
```

📝 **Write down:** What's the difference between "Untracked" (Step 4) and "modified" (this step)?

---

## Step 8 — Stage and Commit the Change

```bash
git add index.html
git status
git commit -m "Add second paragraph to index.html"
git status
```

Observe how the status changes at each step.

---

## Step 9 — Create a Second File

Create `about.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>About</title>
</head>
<body>
  <h1>About This Project</h1>
  <p>This project is for learning Git.</p>
</body>
</html>
```

Run `git status`. You'll see it as an untracked file.

Stage and commit it:

```bash
git add about.html
git commit -m "Add about.html page"
```

---

## Step 10 — View Your Commit History

```bash
git log
```

You should see all 3 commits listed with their hash, author, date, and message.

For a more compact view:

```bash
git log --oneline
```

📝 **Write down:** What information does each commit show? What is the long string of letters and numbers (the commit hash)?

---

## Reflection Questions

Answer these in your notes:

1. What is the difference between `git add` and `git commit`?
2. Why does Git have a staging area? Why not just commit directly?
3. What would happen if you ran `git commit` without running `git add` first?
4. What makes a good commit message?
5. What does `git status` tell you that `git log` doesn't?

---

## Bonus

If you finish early:

- Try running `git diff` after making a change but before staging it — what do you see?
- Try `git add .` instead of `git add filename` — what's the difference?
- Create a third file, stage it, then run `git status` — then unstage it with `git restore --staged filename` and run `git status` again
