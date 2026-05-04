# Assignment — Refactor a Component Library with CSS Nesting

## What You Are Building

Take a flat CSS component library and refactor it to use CSS nesting throughout.

---

## Requirements

Create `nested-components.html` and `nested-components.css` with these components, all using CSS nesting:

### Components to Build

1. **Navigation** — nested `&__logo`, `&__links`, `&__link`, `&__link:hover`, `&__link--active`
2. **Card** — nested `&__image`, `&__body`, `&__title`, `&__text`, `&__footer`
3. **Button** — nested `&--primary`, `&--secondary`, `&--danger`, `&:hover`, `&:active`, `&:disabled`
4. **Form** — nested `&__group`, `&__label`, `&__input`, `&__input:focus`, `&__error`
5. **Alert** — nested `&--success`, `&--warning`, `&--error`, `&__icon`, `&__message`

### Nesting Requirements

- Use `&` for all child selectors
- Use `&:hover`, `&:focus`, `&:active` for state selectors
- Use `&--modifier` for BEM modifiers
- Use `@media` queries nested inside selectors

---

## Submission

Submit `nested-components.html` and `nested-components.css`.
