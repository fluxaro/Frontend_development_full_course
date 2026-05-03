# Notes — Forms and Input Types

## Form Cheat Sheet

```html
<form action="/submit" method="POST">
  <label for="field-id">Label Text</label>
  <input type="text" id="field-id" name="field_name">
  <button type="submit">Submit</button>
</form>
```

## All Input Types

| Type | Use For |
|---|---|
| `text` | General text |
| `email` | Email addresses |
| `password` | Passwords (hidden) |
| `number` | Numbers |
| `date` | Date picker |
| `time` | Time picker |
| `datetime-local` | Date + time |
| `tel` | Phone numbers |
| `url` | Web addresses |
| `search` | Search queries |
| `color` | Color picker |
| `range` | Slider |
| `file` | File upload |
| `checkbox` | Multiple selections |
| `radio` | Single selection from group |
| `hidden` | Hidden data |
| `submit` | Submit button |
| `reset` | Reset button |

## Key Attributes

| Attribute | Purpose |
|---|---|
| `name` | Key sent to server |
| `id` | Links to label |
| `value` | Default value |
| `placeholder` | Hint text |
| `required` | Must be filled |
| `disabled` | Cannot interact |
| `readonly` | Can read, not edit |
| `autofocus` | Focus on load |
| `minlength/maxlength` | Text length limits |
| `min/max` | Number/date limits |
| `pattern` | Regex validation |
| `accept` | File type filter |

## Common Mistakes

- Missing `name` attribute (data won't be sent to server)
- Missing `id` on input and `for` on label (breaks accessibility)
- Using `<input type="button">` instead of `<button>` (less flexible)
- Not grouping related inputs in `<fieldset>`
- Using `placeholder` as a replacement for `<label>` (accessibility failure)
- Forgetting `type="button"` on buttons inside forms (they default to `type="submit"`)

## Radio vs Checkbox

| | Radio | Checkbox |
|---|---|---|
| Selection | One from group | Multiple |
| `name` | Same for all in group | Can be same or different |
| `value` | Unique per option | Unique per option |

## GET vs POST

| | GET | POST |
|---|---|---|
| Data location | URL query string | Request body |
| Visible in URL? | Yes | No |
| Use for | Search, filters | Login, signup, sensitive data |
| Bookmarkable? | Yes | No |
| Max data size | Limited | Unlimited |
