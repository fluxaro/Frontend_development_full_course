# Assignment — Create a Portfolio Repository with a Great README

## Overview

Create a GitHub repository for your HTML portfolio project and write a professional README.md. This repo will be the home of your portfolio — something you'll show to employers and share with the world.

**Due:** Next class  
**Submission:** Share the link to your GitHub repository

---

## Part 1 — Create the Repository

1. Go to https://github.com/new
2. Name it something professional:
   - ✅ `my-portfolio`
   - ✅ `frontend-portfolio`
   - ✅ `alex-rivera-portfolio` (your name)
   - ❌ `test123`
   - ❌ `asdfgh`
   - ❌ `untitled`
3. Add a description (1–2 sentences)
4. Set to **Public**
5. **Do NOT initialize with README** (you'll push your own)
6. Click **Create repository**

---

## Part 2 — Write a Professional README

Create a `README.md` file in your project folder with the following sections:

### Required Sections

#### 1. Project Title and Description
```markdown
# My Frontend Portfolio

A personal portfolio website built with HTML and CSS, showcasing my projects
and skills as a frontend developer.
```

#### 2. Live Demo Link (if you have GitHub Pages set up)
```markdown
## 🌐 Live Demo
[View the live site](https://yourusername.github.io/my-portfolio)
```

#### 3. Technologies Used
```markdown
## 🛠️ Technologies Used
- HTML5 (semantic markup)
- CSS3 (flexbox, custom properties)
- Git & GitHub (version control)
```

#### 4. Pages / Features
```markdown
## 📄 Pages
- **Home** (`index.html`) — Hero section, skills overview
- **About** (`about.html`) — Bio, background, learning journey
- **Projects** (`projects.html`) — Portfolio of completed projects
- **Contact** (`contact.html`) — Contact form and social links
```

#### 5. How to View Locally
```markdown
## 🚀 How to Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/my-portfolio.git
   ```
2. Open `index.html` in your browser
```

#### 6. About the Author
```markdown
## 👤 Author
**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your@email.com
```

---

## Part 3 — Push Your Portfolio to GitHub

After creating the repo and writing the README, push your portfolio:

```bash
# In your portfolio project folder
git init  # (if not already a git repo)
git add .
git commit -m "Initial commit: add portfolio with README"
git branch -M main
git remote add origin git@github.com:yourusername/my-portfolio.git
git push -u origin main
```

---

## Part 4 — Verify on GitHub

After pushing, check that:
- [ ] All your files appear in the repo
- [ ] The README renders correctly on the repo page
- [ ] The commit history shows your commits
- [ ] The repo is set to Public

---

## Grading Checklist

### Repository
- [ ] Repository created with a professional name
- [ ] Repository is public
- [ ] All portfolio files are pushed

### README
- [ ] Project title and description
- [ ] Technologies used section
- [ ] Pages/features section
- [ ] How to run locally section
- [ ] Author section with GitHub link
- [ ] README renders correctly on GitHub (check formatting)

### Content Quality
- [ ] README is written in your own words
- [ ] No placeholder text left in (like "Your Name Here")
- [ ] Markdown formatting is correct (headers, code blocks, lists)

---

## Bonus Challenges

- [ ] Add badges to your README (shields.io provides free badges)
  ```markdown
  ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
  ```
- [ ] Add screenshots of your portfolio pages to the README
- [ ] Enable GitHub Pages and add the live URL to the README
- [ ] Add a "What I Learned" section to the README
- [ ] Add a table of contents with anchor links

---

## README Best Practices

1. **Write for a stranger** — assume the reader knows nothing about your project
2. **Keep it updated** — a README that's out of date is worse than no README
3. **Use markdown formatting** — headers, code blocks, and lists make it readable
4. **Include a live link** — if the project is deployed, link to it prominently
5. **Be specific** — "Built with HTML and CSS" is better than "Built with web technologies"
6. **Show, don't tell** — screenshots are worth a thousand words

---

## Example README Structure

See `examples/good-readme.md` for a complete example of a well-written README.
