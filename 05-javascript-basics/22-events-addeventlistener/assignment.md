# Assignment — Interactive Event Dashboard

## What You Are Building

An interactive dashboard that demonstrates all major event types with visual feedback, showing how events work in practice.

---

## Requirements

Create `event-dashboard.html` with:

### Part 1 — Mouse Events

A large interactive area that tracks and displays:
- Current mouse position (clientX, clientY) in real time
- Click count (left, middle, right separately)
- Double-click detection
- Mouse enter/leave with a colour change
- A "trail" effect that creates dots where the mouse moves

### Part 2 — Keyboard Events

A text input that shows:
- The last key pressed (`e.key`)
- The key code (`e.code`)
- Whether Ctrl, Shift, Alt, or Meta is held
- A live character count
- Keyboard shortcut: Ctrl+Enter to submit, Escape to clear

### Part 3 — Form Events

A form with:
- `input` event: live validation as the user types
- `change` event: log when a select or checkbox changes
- `focus`/`blur` events: highlight the active field
- `submit` event with `e.preventDefault()`: show a success message instead of reloading

### Part 4 — Window Events

A panel showing:
- Window dimensions (updated on `resize`)
- Scroll position (updated on `scroll`)
- A "Back to Top" button that appears after scrolling 200px

### Part 5 — Event Options

Demonstrate:
- `{ once: true }` — a button that can only be clicked once
- `{ passive: true }` — on a scroll listener
- `removeEventListener` — a button that removes its own listener after 3 clicks

---

## What Good Looks Like

- Mouse position updates smoothly in real time
- Keyboard events show the correct key information
- Form validation gives real-time feedback
- Window resize and scroll events update the display
- The `once` option button is visually disabled after first click

---

## Submission

Submit `event-dashboard.html`.
