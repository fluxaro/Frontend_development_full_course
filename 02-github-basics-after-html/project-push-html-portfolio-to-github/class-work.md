# Class Work — Deploy Your Portfolio to GitHub Pages

## What You Will Do

Push your HTML portfolio to GitHub and enable GitHub Pages to make it live on the internet.

**Time:** 45 minutes

---

## Step 1 — Prepare Your Portfolio Files

Make sure you have these files in your portfolio folder:
- `index.html`
- `about.html`
- `projects.html`
- `contact.html`
- `.gitignore`

If any are missing, create them now with basic content.

---

## Step 2 — Initialize Git (if not done)

```bash
cd ~/Desktop/html-portfolio
git init
git branch -M main
```

---

## Step 3 — Create a .gitignore

```bash
touch .gitignore
```

Add to `.gitignore`:
```
.DS_Store
Thumbs.db
.vscode/
*.log
```

---

## Step 4 — Make Your Initial Commits

Commit each file separately with a meaningful message:

```bash
git add .gitignore
git commit -m "Add .gitignore"

git add index.html
git commit -m "Add homepage with navigation and bio"

git add about.html
git commit -m "Add about page with skills"

git add projects.html
git commit -m "Add projects page"

git add contact.html
git commit -m "Add contact page with form"
```

---

## Step 5 — Create GitHub Repository

1. Go to `https://github.com/new`
2. Repository name: `html-portfolio`
3. Description: "My HTML portfolio — Frontend Bootcamp"
4. Visibility: Public
5. Do NOT check "Add a README file"
6. Click "Create repository"

---

## Step 6 — Connect and Push

```bash
git remote add origin https://github.com/YOURUSERNAME/html-portfolio.git
git push -u origin main
```

Verify on GitHub that all your files are there.

---

## Step 7 — Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top right area)
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select **Deploy from a branch**
5. Select **main** branch and **/ (root)** folder
6. Click **Save**

---

## Step 8 — Wait and Verify

Wait 1–2 minutes. Then visit:
```
https://YOURUSERNAME.github.io/html-portfolio
```

Your portfolio is now live on the internet!

---

## Step 9 — Make a Change and Redeploy

Make a small change to `index.html` (update your bio or add a sentence).

```bash
git add index.html
git commit -m "Update bio on homepage"
git push
```

Wait 1–2 minutes and refresh your GitHub Pages URL. The change should appear.

---

## Checklist

- [ ] All 4 HTML files are in the repository
- [ ] `.gitignore` is committed
- [ ] At least 5 commits with meaningful messages
- [ ] Repository is public on GitHub
- [ ] GitHub Pages is enabled
- [ ] Live URL works and shows your portfolio
- [ ] Made a change and redeployed successfully
