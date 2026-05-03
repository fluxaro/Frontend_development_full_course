# Assignment — Complete .gitignore for a Frontend Project

## What You Are Doing

Create a comprehensive `.gitignore` file for a frontend project and document what each section ignores and why.

---

## Requirements

### Part 1: Create the .gitignore

Create a `.gitignore` file that covers all of the following categories:

1. **OS files** — .DS_Store, Thumbs.db, desktop.ini
2. **Editor files** — .vscode/, .idea/, *.swp, *.swo
3. **Environment variables** — .env, .env.local, .env.*.local
4. **Node.js** — node_modules/, npm-debug.log*, yarn-error.log*
5. **Build output** — dist/, build/, .next/, out/
6. **Testing** — coverage/, .nyc_output/
7. **Caching** — .cache/, .parcel-cache/
8. **Logs** — *.log

### Part 2: Document It

Create a file called `gitignore-explained.md` that explains:
- What each section ignores
- Why each category should be ignored
- What would happen if you accidentally committed each type of file

### Part 3: Test It

In your portfolio project:
1. Add the `.gitignore` file
2. Create test files for each category
3. Run `git status` and confirm none of the ignored files appear
4. Commit the `.gitignore`
5. Push to GitHub

---

## What Good Looks Like

- The `.gitignore` covers all common frontend project files
- The documentation explains the "why" not just the "what"
- The file is committed and pushed to GitHub
- `git status` shows a clean working tree after adding test files

---

## Bonus Challenges

- Set up a global `.gitignore` for OS-specific files
- Add a `.gitkeep` file to an empty folder to track it in Git
- Research and add patterns for your specific editor
- Add patterns for common testing frameworks (Jest, Vitest)

---

## Submission

Push the `.gitignore` and `gitignore-explained.md` to your GitHub portfolio repository.
