# Notes — HTML Accessibility and ARIA

## WCAG Principles (POUR)

| Principle | Key Requirements |
|---|---|
| Perceivable | Alt text, captions, sufficient contrast |
| Operable | Keyboard navigation, no seizure content |
| Understandable | Clear language, predictable behavior |
| Robust | Works with assistive technologies |

## Quick Accessibility Checklist

- [ ] All images have `alt` text (or `alt=""` if decorative)
- [ ] All form inputs have `<label>` elements
- [ ] Heading hierarchy is sequential (h1 → h2 → h3)
- [ ] Page has a `lang` attribute on `<html>`
- [ ] All interactive elements are keyboard accessible
- [ ] Color is not the only way to convey information
- [ ] Links have descriptive text (not "click here")
- [ ] Videos have captions
- [ ] Skip link is present

## ARIA Quick Reference

```html
<!-- Label an element -->
<button aria-label="Close dialog">X</button>

<!-- Point to a label -->
<section aria-labelledby="heading-id">
  <h2 id="heading-id">Section Title</h2>
</section>

<!-- Point to a description -->
<input aria-describedby="hint-id">
<p id="hint-id">Hint text here</p>

<!-- Hide from screen readers -->
<span aria-hidden="true">★★★</span>

<!-- Announce changes -->
<div aria-live="polite">Status updates here</div>

<!-- Mark as expanded/collapsed -->
<button aria-expanded="false">Toggle</button>

<!-- Mark as required -->
<input aria-required="true">

<!-- Mark as invalid -->
<input aria-invalid="true">
```

## Common Mistakes

- Using `<div>` or `<span>` for buttons (not keyboard accessible)
- Missing `alt` on images
- Using `placeholder` instead of `<label>`
- Removing focus outlines with `outline: none`
- Using color alone to indicate errors
- Writing "click here" as link text
- Skipping heading levels
- Missing `lang` attribute on `<html>`

## Screen Reader Shortcuts (VoiceOver Mac)

| Action | Shortcut |
|---|---|
| Start/stop | Cmd + F5 |
| Next heading | VO + Cmd + H |
| Next link | VO + Cmd + L |
| Next form field | VO + Cmd + J |
| Read page | VO + A |
