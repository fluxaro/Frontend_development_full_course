# Example: Reading git log Output

## Full git log Output

Here's what `git log` looks like on a real project:

```
commit f8a3c21d4b5e6f7a8b9c0d1e2f3a4b5c6d7e8f9
Author: Alex Rivera <alex@example.com>
Date:   Wed Jan 17 16:45:22 2024 -0500

    Add footer with copyright and social links

    Added a sticky footer with copyright year and links to
    GitHub and LinkedIn profiles. Used flexbox for layout.

commit e7b2d14c3a4f5e6d7c8b9a0f1e2d3c4b5a6f7e8
Author: Alex Rivera <alex@example.com>
Date:   Wed Jan 17 14:20:11 2024 -0500

    Add responsive styles for mobile screens

commit d6c1e03b2a3f4e5d6c7b8a9f0e1d2c3b4a5f6e7
Author: Alex Rivera <alex@example.com>
Date:   Tue Jan 16 11:32:45 2024 -0500

    Style navigation with flexbox and hover effects

commit c5b0f92a1b2e3d4c5b6a7f8e9d0c1b2a3f4e5d6
Author: Alex Rivera <alex@example.com>
Date:   Tue Jan 16 09:15:30 2024 -0500

    Add contact.html with email form

commit b4a9e81f0a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5
Author: Alex Rivera <alex@example.com>
Date:   Mon Jan 15 17:55:18 2024 -0500

    Add projects.html with portfolio grid

commit a3f8d70e9f0a1b2c3d4e5f6a7b8c9d0e1f2a3b4
Author: Alex Rivera <alex@example.com>
Date:   Mon Jan 15 14:32:18 2024 -0500

    Add about.html with bio and skills section

commit 9e2c7b6d8e9f0a1b2c3d4e5f6a7b8c9d0e1f2a3
Author: Alex Rivera <alex@example.com>
Date:   Mon Jan 15 11:15:42 2024 -0500

    Add style.css with base styles and color variables

commit 5a8d3c2b1c2d3e4f5a6b7c8d9e0f1a2b3c4d5e6
Author: Alex Rivera <alex@example.com>
Date:   Sun Jan 14 16:45:30 2024 -0500

    Initial commit: add index.html and README
```

---

## Breaking Down Each Part

### The Commit Hash
```
commit f8a3c21d4b5e6f7a8b9c0d1e2f3a4b5c6d7e8f9
```
- This is a **SHA-1 hash** — a unique 40-character identifier for this commit
- No two commits in the world have the same hash
- You can reference any commit by its first 7 characters: `f8a3c21`
- Git generates this automatically — you don't choose it

### The Author
```
Author: Alex Rivera <alex@example.com>
```
- This comes from your `git config user.name` and `git config user.email`
- On collaborative projects, this shows you who made each change
- This is why configuring your name and email correctly matters

### The Date
```
Date:   Wed Jan 17 16:45:22 2024 -0500
```
- Full timestamp of when the commit was made
- `-0500` is the timezone offset (EST in this case)
- Useful for understanding when work happened

### The Message
```
    Add footer with copyright and social links

    Added a sticky footer with copyright year and links to
    GitHub and LinkedIn profiles. Used flexbox for layout.
```
- First line: the **subject** (short summary, under 72 chars)
- Blank line separates subject from body
- Body: optional longer explanation of *why* the change was made

---

## git log --oneline Output

The same history in compact form:

```
f8a3c21 Add footer with copyright and social links
e7b2d14 Add responsive styles for mobile screens
d6c1e03 Style navigation with flexbox and hover effects
c5b0f92 Add contact.html with email form
b4a9e81 Add projects.html with portfolio grid
a3f8d70 Add about.html with bio and skills section
9e2c7b6 Add style.css with base styles and color variables
5a8d3c2 Initial commit: add index.html and README
```

- Left column: short hash (first 7 chars of the full hash)
- Right column: commit message subject line
- Newest commits at the top

---

## git log --graph --oneline Output

On a project with branches:

```
*   f8a3c21 Merge branch 'feature/dark-mode' into main
|\
| * e7b2d14 Add dark mode CSS variables
| * d6c1e03 Add dark mode toggle button
* | c5b0f92 Fix typo in about page
|/
* b4a9e81 Add projects.html with portfolio grid
* a3f8d70 Add about.html with bio and skills section
* 5a8d3c2 Initial commit: add index.html and README
```

Reading the graph:
- `*` = a commit
- `|` = a branch line
- `\` and `/` = branch diverging or merging
- The merge commit (`f8a3c21`) has two parents

---

## git log --stat Output

Shows which files changed in each commit:

```
commit f8a3c21
Author: Alex Rivera <alex@example.com>
Date:   Wed Jan 17 16:45:22 2024

    Add footer with copyright and social links

 index.html | 12 ++++++++++++
 style.css  |  8 ++++++++
 2 files changed, 20 insertions(+)
```

- Shows file names that were modified
- `+++` = lines added, `---` = lines removed
- Summary at the bottom: files changed, insertions, deletions

---

## What the Commit Hash Tells You

The hash `f8a3c21d4b5e6f7a8b9c0d1e2f3a4b5c6d7e8f9` is:
- **Unique** — no other commit anywhere has this hash
- **Deterministic** — based on the content of the commit
- **Immutable** — if you change anything about the commit, the hash changes
- **Verifiable** — you can always check if a commit was tampered with

This is why Git is trustworthy — the history can't be secretly changed without the hashes changing too.
