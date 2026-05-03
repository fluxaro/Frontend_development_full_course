# Notes — Forms Validation

## Validation Attributes Cheat Sheet

| Attribute | Works On | Example |
|---|---|---|
| `required` | All inputs | `required` |
| `minlength` | text, email, password, search, url, tel | `minlength="3"` |
| `maxlength` | text, email, password, search, url, tel | `maxlength="20"` |
| `min` | number, date, time, range | `min="18"` |
| `max` | number, date, time, range | `max="120"` |
| `pattern` | text, email, password, search, url, tel | `pattern="[A-Za-z]+"` |
| `type` | input | `type="email"` |

## Common Patterns

```
Letters only:           [A-Za-z]+
Letters and numbers:    [A-Za-z0-9]+
Username (safe chars):  [A-Za-z0-9_\-]{3,20}
US phone:               \d{3}[\-\s]?\d{3}[\-\s]?\d{4}
International phone:    \+?[\d\s\-\(\)]{7,15}
US zip code:            \d{5}(-\d{4})?
Strong password:        (?=.*[A-Z])(?=.*\d).{8,}
```

## CSS Validation Pseudo-classes

```css
input:valid { border-color: green; }
input:invalid { border-color: red; }
input:required { border-left: 4px solid orange; }
input:optional { border-left: 4px solid gray; }

/* Only show invalid state after user has typed */
input:invalid:not(:placeholder-shown) { border-color: red; }
```

## Common Mistakes

- Using `pattern` without `title` (user gets no helpful error message)
- Setting `max` on date without knowing the correct ISO format (YYYY-MM-DD)
- Using `minlength` on `type="number"` (use `min` instead)
- Forgetting that `pattern` must match the ENTIRE value (it is implicitly anchored)
- Using `novalidate` and forgetting to add JavaScript validation

## novalidate

```html
<form novalidate>
  <!-- Browser won't validate — you handle it with JavaScript -->
</form>
```

Use `novalidate` when you want full control over validation with JavaScript.
