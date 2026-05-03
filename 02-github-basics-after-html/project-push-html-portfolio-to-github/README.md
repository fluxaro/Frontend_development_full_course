# Project — Push Your HTML Portfolio to GitHub

## Project Overview

This is your first real project milestone. You will take everything you have built in the HTML module, push it to GitHub, and make it live on the internet using GitHub Pages.

**Time:** 2–3 hours  
**Outcome:** A live portfolio website accessible at a real URL

---

## What You Are Building

A complete HTML portfolio website with:
- `index.html` — Homepage with your name, bio, and navigation
- `about.html` — About page with your background and skills
- `projects.html` — Projects page showcasing your work
- `contact.html` — Contact page with a form and your contact info
- `style.css` — Basic CSS styling (optional but recommended)
- `README.md` — Project documentation
- `.gitignore` — Ignoring unnecessary files

---

## Requirements

### HTML Requirements

**index.html:**
- Your name as `<h1>`
- A short bio paragraph
- Navigation to all 4 pages
- A featured section (skills, latest project, or call to action)

**about.html:**
- Your background and story
- Skills list (what you are learning)
- Education or work history
- A photo (or placeholder)

**projects.html:**
- At least 3 projects (can be the exercises from this module)
- Each project has a title, description, and link to GitHub

**contact.html:**
- A contact form with name, email, and message
- Your email link
- Your GitHub and LinkedIn links

### Git Requirements

- At least 8 commits with meaningful messages
- A proper `.gitignore` file
- A `README.md` with project description

### GitHub Requirements

- Repository named `html-portfolio`
- Repository is public
- All files pushed to GitHub
- GitHub Pages enabled

---

## Step-by-Step Instructions

### Step 1: Create the Repository

1. Go to github.com and create a new repository
2. Name it `html-portfolio`
3. Make it public
4. Do NOT initialize with README (you will add your own)

### Step 2: Set Up Locally

```bash
mkdir html-portfolio
cd html-portfolio
git init
git branch -M main
```

### Step 3: Create Your Files

Create all 4 HTML files, the CSS file, README.md, and .gitignore.

### Step 4: Make Commits

```bash
# First commit
git add index.html
git commit -m "Add homepage with navigation and bio"

# Second commit
git add about.html
git commit -m "Add about page with skills and background"

# Continue for each file...
```

### Step 5: Push to GitHub

```bash
git remote add origin https://github.com/yourusername/html-portfolio.git
git push -u origin main
```

### Step 6: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click Settings → Pages
3. Under Source, select "Deploy from a branch"
4. Select "main" branch and "/ (root)" folder
5. Click Save
6. Wait 1–2 minutes, then visit `https://yourusername.github.io/html-portfolio`

---

## Submission

Share:
1. Your GitHub repository URL: `https://github.com/yourusername/html-portfolio`
2. Your live GitHub Pages URL: `https://yourusername.github.io/html-portfolio`
