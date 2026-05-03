# Assignment — Clone, Explore, and Pull

## What You Are Doing

You will clone a classmate's or a public repository, review the code, document what you find, and then pull any updates.

---

## Requirements

### Part 1: Clone a Repository

Clone one of the following (your choice):
- A classmate's `html-portfolio` repository
- Any public repository on GitHub that interests you
- The MDN content repository: `https://github.com/mdn/content`

After cloning, run these commands and write down the output:

```bash
git log --oneline
git remote -v
git branch
```

### Part 2: Explore the Code

Open the cloned repository in VS Code. Look through the files and answer these questions in a file called `code-review-notes.md`:

1. What is this project about?
2. How many files does it have?
3. How many commits are in the history?
4. What was the most recent change made?
5. What is one thing you learned from looking at this code?

### Part 3: Pull Updates

If you cloned a classmate's repo:
- Ask them to make a change and push it
- Run `git pull` to get their change
- Verify the change appeared in your local copy

If you cloned a public repo:
- Wait a day and run `git pull` to see if any new commits came in
- Or make a change on GitHub directly (if it is your own repo) and pull it

### Part 4: Document the Workflow

In your `code-review-notes.md`, add a section called "Clone and Pull Workflow" that explains in your own words:
- When you would use `git clone`
- When you would use `git pull`
- The difference between the two

---

## What Good Looks Like

- The cloned repository is on your computer and opens in VS Code
- `git log --oneline` shows the commit history
- `git remote -v` shows the correct remote URL
- The `code-review-notes.md` file has real, thoughtful answers
- You successfully pulled at least one update

---

## Submission

Submit your `code-review-notes.md` file via GitHub or file upload.
