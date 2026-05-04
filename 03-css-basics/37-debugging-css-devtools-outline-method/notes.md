# Notes — Debugging CSS

## Quick Debug Tricks

```css
/* Outline method — see all boxes */
* { outline: 1px solid red; }

/* Specific element */
.card { outline: 2px solid blue; }

/* Background method */
* { background: rgba(255,0,0,0.1); }
```

## DevTools Shortcuts

| Action | Chrome | Firefox |
|---|---|---|
| Open DevTools | F12 / Cmd+Option+I | F12 |
| Inspect element | Ctrl+Shift+C | Ctrl+Shift+C |
| Toggle device mode | Ctrl+Shift+M | Ctrl+Shift+M |

## Common CSS Bugs and Fixes

| Bug | Cause | Fix |
|---|---|---|
| Element wider than expected | Missing `box-sizing: border-box` | Add `* { box-sizing: border-box }` |
| Margin not working | Margin collapse | Use padding or flex/grid |
| z-index not working | Not positioned | Add `position: relative` |
| Flexbox not working | Wrong element | Apply to parent, not children |
| Image has gap below | Inline element | Add `display: block` to img |
| Overflow hidden not working | Missing `position` | Add `position: relative` |

## DevTools Workflow

1. Right-click element → Inspect
2. Check Styles panel for applied rules
3. Check Computed panel for final values
4. Check Layout panel for box model
5. Toggle rules on/off to isolate the issue
