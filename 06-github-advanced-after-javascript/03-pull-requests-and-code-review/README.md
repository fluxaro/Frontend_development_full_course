# 03 — Pull Requests and Code Review

## What Is This Lesson About?

Pull Requests (PRs) are the standard way to propose and review code changes before merging them into the main branch. They are central to professional team workflows.

---

## What is a Pull Request?

A PR is a request to merge your branch into another branch. It provides:
- A diff showing exactly what changed
- A place for discussion and feedback
- A review and approval process
- A record of why changes were made

---

## Creating a Pull Request

```bash
# 1. Create and work on a feature branch
git switch -c feature/user-auth
# ... make commits ...

# 2. Push the branch to GitHub
git push -u origin feature/user-auth

# 3. Go to GitHub → your repo → "Compare & pull request"
# Or use the GitHub CLI:
gh pr create --title "Add user authentication" --body "Implements login/logout"
```

---

## Good PR Description

```markdown
## What this PR does
Adds user authentication with email/password login and JWT tokens.

## Changes
- Added `LoginForm` component
- Added `useAuth` hook
- Added `/api/auth/login` endpoint
- Updated navbar to show user avatar when logged in

## How to test
1. Run `npm run dev`
2. Click "Login" in the navbar
3. Enter test credentials: test@example.com / password123
4. Verify the navbar shows the user avatar

## Screenshots
[attach screenshots]
```

---

## Code Review Best Practices

**As a reviewer:**
- Review the logic, not just the style
- Ask questions rather than making demands
- Approve when satisfied, request changes when not
- Be specific: "Line 42: this could throw if `user` is null"

**As the author:**
- Keep PRs small and focused (one feature per PR)
- Respond to all comments
- Don't take feedback personally

---

## Common Mistakes

- Giant PRs with hundreds of changes (hard to review)
- Vague PR titles like "fix stuff" or "updates"
- Not testing before opening a PR
- Merging without at least one approval
