# Assignment — Interactive UI with Dark Mode

## What You Are Building

An interactive UI page with hover cards, accessible focus states, active button effects, and a working dark mode toggle — all using Tailwind state variants.

---

## Requirements

Create `interactive-ui.html` with the Tailwind CDN.

### Dark Mode Toggle
- [ ] A toggle button in the navbar that switches between light and dark mode
- [ ] Use `tailwind.config = { darkMode: 'class' }` and toggle the `dark` class on `<html>`
- [ ] The button shows a sun icon in dark mode and a moon icon in light mode
- [ ] The entire page adapts: backgrounds, text, borders, and cards all change

### Hover Cards Section
- [ ] At least 4 cards using `group` + `group-hover:` pattern
- [ ] On hover: card lifts (`hover:shadow-xl hover:-translate-y-1`), title changes color (`group-hover:text-blue-600`), and a "Read more →" link fades in (`opacity-0 group-hover:opacity-100`)
- [ ] All transitions use `transition-all duration-200`

### Button Variants Section
- [ ] Primary button: `hover:bg-blue-700 active:bg-blue-800 active:scale-95`
- [ ] Secondary button: `hover:bg-gray-100 active:bg-gray-200`
- [ ] Danger button: `hover:bg-red-700 active:scale-95`
- [ ] Disabled button: `disabled:opacity-50 disabled:cursor-not-allowed`
- [ ] All buttons have `focus-visible:ring-2 focus-visible:ring-offset-2`

### Form Section
- [ ] An email input with `focus:ring-2 focus:ring-blue-500 focus:border-transparent`
- [ ] A password input with the same focus styles
- [ ] A custom checkbox using `peer` + `peer-checked:bg-blue-600`
- [ ] All inputs have dark mode variants: `dark:bg-gray-800 dark:border-gray-600 dark:text-white`

---

## What Good Looks Like

- Dark mode toggle works instantly and the whole page changes
- Hover cards have smooth, satisfying animations
- Buttons feel responsive — they visually react to hover, press, and focus
- The custom checkbox looks polished and works correctly
- Tab through the page with keyboard — focus rings are visible and accessible

---

## Submission

Submit `interactive-ui.html`. Test it by:
1. Clicking the dark mode toggle
2. Hovering over each card
3. Pressing (not just hovering) each button
4. Tabbing through the form with the keyboard
