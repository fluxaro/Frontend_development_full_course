# Class Work — Connect a Local Repo to GitHub and Push

## What You Will Do

You will take a local Git repository, connect it to a new GitHub repository, and push your commits to GitHub for the first time.

**Time:** 30 minutes  
**Prerequisites:** You have a local Git repo with at least 2 commits from the previous lesson.

---

## Step 1 — Verify Your Local Repo

Open your terminal and navigate to your project folder:

```bash
cd ~/Desktop/my-first-git-project
```

Check that you have commits:

```bash
git log --oneline
```

You should see at least 2 commits listed. If not, go back to Lesson 03 and create them.

Check your current remotes:

```bash
git remote -v
```

You should see no output — that means no remotes are connected yet.

---

## Step 2 — Create a New Repository on GitHub

1. Go to `https://github.com` and sign in
2. Click the **+** button in the top right corner
3. Click **New repository**
4. Fill in the details:
   - **Repository name:** `my-first-git-project` (match your local folder name)
   - **Description:** "My first project tracked with Git"
   - **Visibility:** Public
   - **IMPORTANT:** Do NOT check "Add a README file" — your local repo already has files
5. Click **Create repository**

GitHub will show you a page with setup instructions. Keep this page open.

---

## Step 3 — Copy the Repository URL

On the GitHub page that just appeared, find the section that says "…or push an existing repository from the command line".

You will see a URL that looks like one of these:
- SSH: `git@github.com:yourusername/my-first-git-project.git`
- HTTPS: `https://github.com/yourusername/my-first-git-project.git`

Copy the URL. Use SSH if you have set up SSH keys. Use HTTPS if you have not.

---

## Step 4 — Add the Remote

Back in your terminal, run:

```bash
git remote add origin YOUR_URL_HERE
```

Replace `YOUR_URL_HERE` with the URL you copied. For example:

```bash
git remote add origin git@github.com:alexrivera/my-first-git-project.git
```

Now verify it was added:

```bash
git remote -v
```

You should see:

```
origin  git@github.com:alexrivera/my-first-git-project.git (fetch)
origin  git@github.com:alexrivera/my-first-git-project.git (push)
```

---

## Step 5 — Make Sure Your Branch is Named "main"

Check your current branch name:

```bash
git branch
```

If it says `master`, rename it to `main`:

```bash
git branch -M main
```

If it already says `main`, skip this step.

---

## Step 6 — Push to GitHub

```bash
git push -u origin main
```

**What the flags mean:**
- `-u` — sets the upstream, so future pushes only need `git push`
- `origin` — the name of the remote (the one you just added)
- `main` — the branch you are pushing

You should see output like:

```
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Writing objects: 100% (6/6), 1.23 KiB | 1.23 MiB/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To github.com:alexrivera/my-first-git-project.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

---

## Step 7 — Verify on GitHub

Go back to your GitHub repository page and refresh it. You should see your files and commit history there.

Click on "commits" to see your commit history on GitHub.

---

## Step 8 — Make a Change and Push Again

Make a small change to `index.html` — add a new paragraph or change the heading.

Then:

```bash
git add index.html
git commit -m "Update index.html with new content"
git push
```

Notice you only need `git push` this time — no `-u origin main` needed because you set the upstream in Step 6.

Refresh GitHub and verify your new commit appears.

---

## Checklist

- [ ] Local repo has at least 2 commits
- [ ] GitHub repository created (without README)
- [ ] Remote added with `git remote add origin`
- [ ] `git remote -v` shows the correct URL
- [ ] Branch renamed to `main` if needed
- [ ] First push done with `git push -u origin main`
- [ ] Files visible on GitHub
- [ ] Second push done with just `git push`
- [ ] New commit visible on GitHub

---

## Discussion Questions

1. What is the difference between `git push -u origin main` and just `git push`?
2. Why should you NOT initialize the GitHub repo with a README when you already have local commits?
3. What does "origin" mean? Could you name it something else?
4. What would happen if you tried to push before adding a remote?
