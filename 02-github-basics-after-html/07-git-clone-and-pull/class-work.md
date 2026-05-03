# Class Work — Clone a Repository and Pull Changes

## What You Will Do

You will clone a public GitHub repository, explore its contents, then simulate pulling updates by making a change on GitHub directly and pulling it to your local machine.

**Time:** 30 minutes

---

## Activity 1: Clone a Public Repository (10 minutes)

### Step 1 — Find a Repository to Clone

Go to `https://github.com/explore` and find any small, interesting public repository. Or use this one for practice:

```
https://github.com/github/gitignore
```

This is GitHub's official collection of `.gitignore` templates — a useful real-world repo.

### Step 2 — Clone It

Open your terminal and navigate to your Desktop:

```bash
cd ~/Desktop
```

Clone the repository:

```bash
git clone https://github.com/github/gitignore.git
```

Watch the output. You will see Git downloading the files.

### Step 3 — Explore the Cloned Repository

```bash
cd gitignore
ls
```

You should see many files. Now check:

```bash
git log --oneline
```

You will see the full commit history of the project — potentially hundreds of commits.

```bash
git remote -v
```

Notice that `origin` is already set up pointing to the GitHub URL. This happened automatically when you cloned.

Write down:
- How many files are in the repository?
- How many commits are in the history?
- What is the most recent commit message?

---

## Activity 2: Simulate Pulling Changes (15 minutes)

For this activity, you will use your own repository from the previous lesson.

### Step 1 — Make a Change Directly on GitHub

1. Go to your `html-portfolio` repository on GitHub
2. Click on `index.html`
3. Click the pencil icon (Edit this file)
4. Add a comment to the HTML: `<!-- Updated directly on GitHub -->`
5. Scroll down and click "Commit changes"
6. Add a commit message: "Add comment via GitHub web editor"
7. Click "Commit changes"

### Step 2 — Check Your Local Repo

Back in your terminal, navigate to your local portfolio folder:

```bash
cd ~/Desktop/html-portfolio
```

Check the current status:

```bash
git status
git log --oneline
```

Your local repo does not have the new commit yet. The change only exists on GitHub.

### Step 3 — Pull the Changes

```bash
git pull
```

You should see output like:

```
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
Unpacking objects: 100% (3/3), done.
From github.com:yourusername/html-portfolio
   a1b2c3d..e4f5g6h  main -> origin/main
Updating a1b2c3d..e4f5g6h
Fast-forward
 index.html | 1 +
 1 file changed, 1 insertion(+)
```

### Step 4 — Verify the Change

```bash
git log --oneline
```

The new commit should now appear in your local history.

Open `index.html` in VS Code and verify the comment is there.

---

## Activity 3: Document What You Learned (5 minutes)

Create a file called `clone-pull-notes.md` in your portfolio folder with:
- The command you used to clone a repository
- The command you used to pull changes
- One thing that surprised you about how clone works
- One situation where you would use `git pull` in a real job

---

## Checklist

- [ ] Successfully cloned a public repository
- [ ] Ran `git log --oneline` on the cloned repo
- [ ] Made a change on GitHub directly
- [ ] Pulled the change to your local machine
- [ ] Verified the change appeared locally

---

## Discussion Questions

1. What is the difference between `git clone` and `git pull`?
2. Why does `git clone` automatically set up the `origin` remote?
3. What would happen if two people edited the same file at the same time and both tried to push?
4. When would you use `git fetch` instead of `git pull`?
