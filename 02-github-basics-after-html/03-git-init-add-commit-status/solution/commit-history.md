# Example: What Good Commit History Looks Like

## The Goal

A good commit history tells the story of how a project was built. Someone reading your commits should be able to understand what changed and why — without looking at the code.

---

## Example `git log --oneline` Output

```
f8a3c21 Add footer with copyright and social links
e7b2d14 Add responsive styles for mobile screens
d6c1e03 Style navigation with flexbox and hover effects
c5b0f92 Add contact.html with email form
b4a9e81 Add projects.html with portfolio grid
a3f8d70 Add about.html with bio and skills section
9e2c7b6 Add style.css with base styles and color variables
8d1b6a5 Add navigation links to index.html
7c0a5f4 Add hero section with heading and call-to-action
6b9e4d3 Add initial HTML structure to index.html
5a8d3c2 Initial commit: add project folder and README
```

---

## Why This History is Good

### ✅ Each commit is one logical change
Every commit does exactly one thing. You can look at any commit and understand what it added or changed.

### ✅ Messages use imperative mood
"Add footer" not "Added footer" or "Adding footer". This is the Git convention.

### ✅ Messages are specific
"Add footer with copyright and social links" tells you exactly what's in the footer. Compare to just "update footer" — that tells you nothing.

### ✅ The history builds incrementally
You can see the project grow step by step:
1. Initial setup
2. Basic HTML structure
3. Hero section
4. Navigation
5. CSS styles
6. More pages
7. Responsive styles
8. Footer

### ✅ No "WIP" or "fix" commits
Every commit is a complete, working unit. No half-finished work committed.

---

## Example `git log` Full Output (for one commit)

```
commit d6c1e03f4a8b2c1d9e7f6a5b4c3d2e1f0a9b8c7
Author: Alex Rivera <alex@example.com>
Date:   Mon Jan 15 14:32:18 2024 -0500

    Style navigation with flexbox and hover effects

    Used flexbox to align logo and nav links horizontally.
    Added hover color transition for better UX.
    Set active link color to white to show current page.
```

The first line is the short summary. The blank line + paragraph below is the optional body — use it when you need to explain *why* you made a change, not just *what* you changed.

---

## Bad Commit History (What to Avoid)

```
# ❌ This tells you nothing
a1b2c3d update
b2c3d4e fix
c3d4e5f changes
d4e5f6a more stuff
e5f6a7b final
f6a7b8c FINAL FINAL
a7b8c9d ok now actually final
```

Problems:
- No idea what was changed
- "final" appears 3 times (classic)
- Can't use this history to find when a bug was introduced
- Can't use this to understand the project's evolution

---

## Commit Message Templates

### Simple feature
```
Add [feature name] to [location]

Examples:
Add dark mode toggle to settings page
Add search bar to navigation header
Add image gallery to projects page
```

### Bug fix
```
Fix [what was broken] in [location]

Examples:
Fix broken link in footer navigation
Fix form not submitting on mobile Safari
Fix hero image not loading on slow connections
```

### Style change
```
Style [element] with [technique]

Examples:
Style hero section with gradient background
Style cards with box shadow and border radius
Style navigation with sticky positioning
```

### Content update
```
Update [what] in [location]

Examples:
Update bio text in about page
Update project descriptions in portfolio
Update contact email address in footer
```

---

## The Commit Frequency Question

**How often should you commit?**

A good rule of thumb: **commit when you complete a small, working unit of work.**

- ✅ After adding a new section to a page
- ✅ After fixing a specific bug
- ✅ After adding a new CSS component
- ✅ After writing a new function
- ❌ Every time you save a file
- ❌ Only once at the end of the day
- ❌ Only when you "finish" the project

Think of commits like checkpoints in a game. Place them at meaningful moments, not randomly.
