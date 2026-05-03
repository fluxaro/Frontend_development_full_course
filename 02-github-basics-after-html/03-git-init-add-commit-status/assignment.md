# Assignment — Three-File HTML Project with Git History

## Overview

Build a small HTML project with at least 3 files, initialize a Git repository, and make at least 3 separate commits — each one adding a different, meaningful feature. The goal is to practice the Git workflow and write good commit messages.

**Due:** Next class  
**Submission:** Share your project folder (or push to GitHub if you've learned that yet)

---

## Project Requirements

### The HTML Project

Create a simple website with at least these 3 files:

1. **`index.html`** — Homepage with a heading, intro paragraph, and navigation links
2. **`about.html`** — About page with some information about you (or a fictional person)
3. **`style.css`** — Basic CSS styling for both pages

You can add more files if you want (contact page, images, etc.).

---

### The Git Requirements

This is the most important part:

- [ ] Initialize a Git repository in your project folder (`git init`)
- [ ] Make **at least 3 separate commits**, each with a meaningful message
- [ ] Each commit should add or change something specific
- [ ] No commit should be "add everything" — build up the project incrementally

---

## Commit Strategy

Here's a suggested approach — build the project one piece at a time:

**Commit 1:** Set up the basic HTML structure
```
git commit -m "Initial commit: add basic HTML structure for index.html"
```

**Commit 2:** Add content to the homepage
```
git commit -m "Add hero section and intro paragraph to homepage"
```

**Commit 3:** Create the about page
```
git commit -m "Add about.html with personal bio section"
```

**Commit 4 (bonus):** Add CSS styling
```
git commit -m "Add style.css with base styles and typography"
```

**Commit 5 (bonus):** Add navigation
```
git commit -m "Add navigation links between index and about pages"
```

---

## What to Submit

1. **Your project folder** with all HTML/CSS files
2. **A screenshot or copy** of your `git log --oneline` output showing all your commits
3. **A brief explanation** (3–5 sentences) of what each commit added

---

## Example `git log --oneline` Output

Your log should look something like this (with your own messages):

```
f3a9c12 Add navigation links between pages
b7e2d45 Add style.css with base styles and typography
9c1f8a3 Add about.html with personal bio section
4d6e7b1 Add hero section and intro paragraph to homepage
a2c3d4e Initial commit: add basic HTML structure for index.html
```

Notice:
- Messages are specific and descriptive
- Each commit represents one logical change
- Messages use imperative mood ("Add", not "Added")
- The history tells a story of how the project was built

---

## Grading Checklist

- [ ] Project has at least 3 HTML/CSS files
- [ ] Git repository initialized
- [ ] At least 3 commits made
- [ ] Each commit has a meaningful, specific message
- [ ] Commits are incremental (not one big "add everything" commit)
- [ ] `git log --oneline` output included in submission
- [ ] Brief explanation of what each commit added

---

## Bonus Challenges

- Make 5+ commits instead of 3
- Add a `contact.html` page
- Use `git diff` to compare two commits and include the output in your submission
- Add a `.gitignore` file (we'll cover this in detail later, but try it!)
- Try making a mistake and then using `git restore` to undo it

---

## Tips

- Run `git status` constantly — before and after every command
- Commit often. Small, focused commits are better than one giant commit
- If you mess up a commit message, you can fix the most recent one with `git commit --amend -m "New message"` (only before pushing!)
- Look at the `examples/sample-project/` folder for a reference project structure
