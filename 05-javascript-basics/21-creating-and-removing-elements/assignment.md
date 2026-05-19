# Assignment — Dynamic Todo List

## What You Are Building

A fully functional todo list that creates, removes, and reorders DOM elements dynamically — without using `innerHTML` for the list items.

---

## Requirements

Create `dynamic-todo.html` with:

### Core Features

- **Add todo**: Input field + button. Creates a new `<li>` element using `createElement` (not `innerHTML`)
- **Delete todo**: Each todo has a delete button that calls `el.remove()`
- **Complete todo**: Checkbox that toggles a `.done` class (strikethrough + opacity)
- **Edit todo**: Double-click a todo text to edit it inline
- **Reorder**: "Move Up" and "Move Down" buttons on each todo

### Categories

- A category dropdown (Work, Personal, Shopping, Other)
- Each todo is tagged with its category
- Filter buttons to show only todos of a specific category

### Statistics

A live stats bar showing:
- Total todos
- Completed count
- Remaining count
- Completion percentage (as a progress bar)

### Persistence

- Save todos to `localStorage` as JSON on every change
- Load todos from `localStorage` on page load
- A "Clear All" button that removes all todos and clears localStorage

### Performance

- Use `DocumentFragment` when loading todos from localStorage (batch insert)

---

## What Good Looks Like

- All todos are created with `createElement`, not `innerHTML`
- Deleting a todo uses `el.remove()`
- Stats update in real time
- Todos persist across page reloads
- The list is smooth and responsive

---

## Submission

Submit `dynamic-todo.html`.
