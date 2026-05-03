# Assignment — User Preferences Page

## What You Are Building

Create an HTML page called `user-preferences.html` that saves user preferences to localStorage and restores them on page reload.

This is the first lesson where JavaScript is required — but keep it minimal and focused on the localStorage API.

---

## Requirements

### Preferences to Save

Your page must save and restore all of the following:

1. **Username** — text input, saved to `localStorage.setItem('username', value)`
2. **Theme** — radio buttons (Light / Dark / System), saved as a string
3. **Font size** — range slider (12–24px), saved as a number
4. **Language** — select dropdown (at least 5 options), saved as a string
5. **Notifications** — checkbox (on/off), saved as a boolean

### Behavior

- On page load: read all preferences from localStorage and apply them
- On any change: immediately save the new value to localStorage
- A "Reset to Defaults" button that clears all preferences from localStorage and reloads the page
- A "Current Settings" section that displays all saved values

### HTML Structure

- Proper `<!DOCTYPE html>`, `<html lang>`, `<head>`, `<body>`
- `<form>` wrapping all preference inputs
- `<fieldset>` grouping related preferences
- All inputs have `<label>` elements
- A `<section>` showing current saved values

---

## What Good Looks Like

- Preferences survive a page reload
- Preferences survive closing and reopening the browser
- The "Current Settings" section updates when preferences change
- The reset button works correctly
- The page is accessible (all inputs have labels)

---

## Bonus Challenges

- Save the entire preferences object as one JSON string instead of individual keys
- Add a "Last saved" timestamp
- Add an "Export settings" button that shows the JSON in a `<pre>` block
- Use `sessionStorage` for a "session notes" textarea that clears on tab close

---

## Submission

Save as `user-preferences.html` and submit via GitHub.
