# Assignment — Git History Analysis

## Overview

Create a project with at least 5 commits, then use `git log` and `git diff` to analyze the history. The goal is to get comfortable reading Git output and understanding what it tells you.

**Due:** Next class  
**Submission:** A written analysis document + your project folder

---

## Part 1 — Build the Project with 5+ Commits

Create a small HTML project and make at least 5 separate, meaningful commits. Each commit should add something specific.

### Suggested Commit Plan

| Commit # | What to Add | Example Message |
|---|---|---|
| 1 | Basic HTML structure | `Initial commit: add index.html with basic structure` |
| 2 | Page heading and intro | `Add hero section with heading and intro text` |
| 3 | Navigation bar | `Add navigation bar with links to all pages` |
| 4 | CSS file with base styles | `Add style.css with typography and color variables` |
| 5 | A second HTML page | `Add about.html with bio section` |
| 6 (bonus) | Responsive styles | `Add media queries for mobile layout` |
| 7 (bonus) | Footer | `Add footer with copyright and contact info` |

---

## Part 2 — Capture the Log Output

Run the following commands and save the output:

### 2.1 Full log
```bash
git log
```
Copy the complete output into your analysis document.

### 2.2 Compact log
```bash
git log --oneline
```
Copy the output.

### 2.3 Graph view
```bash
git log --graph --oneline --decorate
```
Copy the output.

---

## Part 3 — Diff Analysis

### 3.1 Compare two adjacent commits

Pick any two consecutive commits from your log. Run:

```bash
git diff <older-hash> <newer-hash>
```

Copy the diff output into your document.

**Then write a 2–3 sentence explanation of what the diff shows.** For example:
> "This diff shows that I added 8 lines to index.html. The green `+` lines show the new navigation bar HTML that was added. No lines were removed in this commit."

### 3.2 Compare first and last commit

```bash
git diff <first-commit-hash> HEAD
```

Copy the output and write a brief explanation of what the total changes look like.

---

## Part 4 — Written Analysis

Answer these questions in your submission document:

1. **How many commits does your project have?** List them all using `git log --oneline`.

2. **Pick your best commit message.** Why is it a good message? What makes it clear and specific?

3. **Pick your worst commit message** (if you have one). How would you improve it?

4. **What does `HEAD` point to in your repo?** Run `git log -1` to find out.

5. **What changed between your first and last commit?** Describe in plain English what the diff shows.

6. **If someone else looked at your commit history, could they understand how the project was built?** Why or why not?

---

## Submission Requirements

Your submission should include:

- [ ] Your project folder with all HTML/CSS files
- [ ] Output of `git log` (full version)
- [ ] Output of `git log --oneline`
- [ ] Output of `git diff` between two commits
- [ ] Written explanation of what the diff shows
- [ ] Answers to the 6 analysis questions

---

## Grading Checklist

- [ ] Project has at least 5 commits
- [ ] All commit messages are specific and meaningful
- [ ] `git log` output included
- [ ] `git log --oneline` output included
- [ ] `git diff` output between two commits included
- [ ] Written explanation of the diff
- [ ] All 6 analysis questions answered

---

## Bonus Challenges

- Use `git log --since="3 days ago"` and include the output
- Use `git log --stat` to show which files changed in each commit
- Use `git show <hash>` on your most interesting commit and include the output
- Try `git blame index.html` and explain what it shows
- Use `git log --grep="Add"` to filter commits and include the output
