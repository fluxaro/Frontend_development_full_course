# Class Work — Specificity Battles

## What You Will Do

Experiment with specificity conflicts and learn to predict which styles win.

**Time:** 30 minutes

---

## Activity 1: Predict the Winner (10 minutes)

Create `specificity-test.html` and `specificity-test.css`. Add these rules and predict the color before opening in browser:

```css
/* Test 1 */
p { color: blue; }
.text { color: red; }
/* Which wins on <p class="text">? */

/* Test 2 */
.card p { color: green; }
p.highlight { color: orange; }
/* Which wins on <p class="highlight"> inside <div class="card">? */

/* Test 3 */
#main .card p { color: purple; }
.card p.text { color: pink; }
/* Which wins on <p class="text"> inside <div class="card"> inside <div id="main">? */
```

Write your predictions, then open in browser to check.

---

## Activity 2: Fix Specificity Without !important (10 minutes)

You have this CSS that is not working as expected:

```css
/* This should make all buttons blue */
button { background: blue; color: white; }

/* This should make danger buttons red */
.btn-danger { background: red; }

/* This should make the submit button in the form green */
form button { background: green; }
```

The problem: `form button` (specificity 0,0,0,2) beats `.btn-danger` (0,0,1,0) — wait, no it doesn't. Work out the specificity for each and figure out why the danger button inside a form might not be red.

Fix it by increasing the specificity of `.btn-danger` without using `!important`.

---

## Activity 3: Inheritance Explorer (10 minutes)

Create a page with this structure:

```html
<div class="parent">
  <p class="child">I am a child paragraph</p>
  <div class="grandchild">
    <span>I am a grandchild span</span>
  </div>
</div>
```

Apply these styles to `.parent` only:
```css
.parent {
  color: #e74c3c;
  font-family: Georgia, serif;
  font-size: 18px;
  border: 2px solid blue;
  background: #f0f0f0;
  padding: 20px;
}
```

Observe:
- Which properties did the child and grandchild inherit?
- Which properties did NOT inherit?
- Add `border: inherit;` to `.child` — what happens?

---

## Checklist

- [ ] Predicted specificity winners correctly
- [ ] Fixed specificity conflict without `!important`
- [ ] Identified which properties inherit and which do not
- [ ] Used `inherit` keyword to force inheritance
