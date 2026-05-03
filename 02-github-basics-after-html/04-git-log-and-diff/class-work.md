# Class Work — Exploring Git History

## Goal

Practice using `git log` and `git diff` on a real repository. You'll learn to read the output and understand what it tells you about a project's history.

**Time:** 25–30 minutes  
**Prerequisite:** You need a Git repo with at least 2–3 commits. Use the project from the previous lesson, or create a quick one.

---

## Setup (if you need a repo)

If you don't have a repo with commits yet, run this to create one quickly:

```bash
mkdir git-log-practice
cd git-log-practice
git init

echo "<h1>Version 1</h1>" > index.html
git add .
git commit -m "Initial commit: add index.html"

echo "<p>Added a paragraph</p>" >> index.html
git add .
git commit -m "Add paragraph to index.html"

echo "<h2>Section 2</h2>" >> index.html
git add .
git commit -m "Add section heading to index.html"
```

---

## Part 1 — Exploring git log

### Exercise 1.1 — Full log

```bash
git log
```

Look at the output carefully. For each commit, identify:
- The full commit hash (40 characters)
- The author name and email
- The date and time
- The commit message

📝 **Write down:** How many commits are in your repo?

---

### Exercise 1.2 — Compact log

```bash
git log --oneline
```

📝 **Write down:** What's the difference between this and the full `git log`? When would you prefer each?

---

### Exercise 1.3 — Graph view

```bash
git log --graph --oneline
```

📝 **Write down:** What do the `*` characters represent? (Hint: they'll be more interesting when you have branches)

---

### Exercise 1.4 — Limit output

```bash
git log -2
git log -1
```

📝 **Write down:** What does `-2` do? When would this be useful?

---

### Exercise 1.5 — Filter by message

```bash
git log --grep="add"
git log --grep="initial"
```

📝 **Write down:** What commits matched? How could this be useful on a large project?

---

### Exercise 1.6 — Show commits for a specific file

```bash
git log -- index.html
```

📝 **Write down:** What does this show? How is it different from `git log` without the filename?

---

## Part 2 — Exploring git diff

### Exercise 2.1 — Make a change (don't stage it yet)

Open `index.html` and add a new line:

```html
<p>This is a new change I haven't staged yet.</p>
```

Save the file, then run:

```bash
git diff
```

📝 **Write down:**
- What does the `+` symbol mean on the new line?
- What does `@@` at the top of the diff mean?
- What color is the new line in your terminal?

---

### Exercise 2.2 — Stage the change and diff again

```bash
git add index.html
git diff
```

📝 **Write down:** Why does `git diff` show nothing now?

Now run:

```bash
git diff --staged
```

📝 **Write down:** What does `--staged` show that regular `git diff` doesn't?

---

### Exercise 2.3 — Commit and compare to previous

```bash
git commit -m "Add new paragraph to index.html"
```

Now compare the last two commits:

```bash
git diff HEAD~1 HEAD
```

📝 **Write down:** What does `HEAD~1` mean? What does this command show?

---

### Exercise 2.4 — Compare specific commits

Get your commit hashes from `git log --oneline`. Then compare the first and last commit:

```bash
# Replace these with your actual hashes
git diff <first-commit-hash> <latest-commit-hash>
```

📝 **Write down:** What does this show? How is it different from comparing adjacent commits?

---

## Part 3 — git show

### Exercise 3.1 — Show the latest commit

```bash
git show HEAD
```

📝 **Write down:** What information does `git show` give you that `git log` doesn't?

### Exercise 3.2 — Show a specific commit

Pick any commit hash from your log and run:

```bash
git show <commit-hash>
```

You only need the first 7 characters of the hash.

---

## Part 4 — Putting It Together

Answer these questions using the commands you've learned:

1. **What was the very first commit in your repo?**
   ```bash
   git log --oneline | tail -1
   ```

2. **What files were changed in the most recent commit?**
   ```bash
   git show --stat HEAD
   ```

3. **How many lines were added across all commits?**
   ```bash
   git log --stat --oneline
   ```

---

## Reflection Questions

1. When would you use `git log` vs `git log --oneline`?
2. What's the difference between `git diff` and `git diff --staged`?
3. How could `git log --grep` help you find when a bug was introduced?
4. Why is it important to write good commit messages? (Think about how `git log` looks with bad messages)
5. What does `HEAD` refer to in Git?

---

## Bonus

- Try `git log --stat` — what extra information does it show?
- Try `git log --format="%h %an %s"` — what does each `%` placeholder mean?
- Try `git shortlog` — what does this show?
- Try `git blame index.html` — what does this command do?
