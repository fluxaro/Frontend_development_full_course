# Assignment — Push Your HTML Portfolio to GitHub

## What You Are Doing

Take your HTML portfolio project from the previous lessons, connect it to a new GitHub repository, and push it. Then make 3 more improvements and push each one as a separate commit.

---

## Requirements

### Part 1: Initial Push

1. Create a new GitHub repository named `html-portfolio`
2. Connect your local portfolio project to it using `git remote add origin`
3. Push all existing commits with `git push -u origin main`
4. Verify all your files appear on GitHub

### Part 2: Three More Commits

After the initial push, make 3 separate improvements to your portfolio. Each improvement must be:
- A real, meaningful change (not just adding a space)
- Committed with a descriptive message
- Pushed to GitHub

**Ideas for improvements:**
- Add a new section to your portfolio (skills, education, contact)
- Improve the content of an existing section
- Add a new page (about.html, projects.html)
- Fix any HTML errors found by the W3C validator
- Add proper meta tags to the head section

### Part 3: Verify

After all 3 pushes, go to your GitHub repository and verify:
- All 3 new commits appear in the commit history
- The commit messages are descriptive and specific
- All files are up to date

---

## What Good Looks Like

- The GitHub repository URL is accessible (public repo)
- The commit history tells the story of how the project was built
- Each commit message explains what was changed and why
- The most recent commit matches the current state of the files
- Running `git log --oneline` locally matches what GitHub shows

---

## Submission

Share the URL of your GitHub repository. It should look like:
`https://github.com/yourusername/html-portfolio`

---

## Bonus Challenges

- Enable GitHub Pages on your repository so the portfolio is live at a real URL
- Add a `.gitignore` file to the project
- Add a `README.md` to the repository explaining what the project is
- Try changing the remote URL from HTTPS to SSH (or vice versa) using `git remote set-url`
