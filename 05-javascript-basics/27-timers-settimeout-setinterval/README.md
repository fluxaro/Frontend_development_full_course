# 27 — Timers: setTimeout and setInterval

## What Is This Lesson About?

Timers let you delay code execution or repeat it at intervals. They are asynchronous — they don't block the rest of your code.

---

## setTimeout

Runs a function once after a delay (in milliseconds):

```javascript
// Run once after 2 seconds
const timerId = setTimeout(() => {
  console.log('2 seconds later!');
}, 2000);

// Cancel before it fires
clearTimeout(timerId);

// setTimeout with 0ms — runs after current call stack clears
setTimeout(() => console.log('after'), 0);
console.log('before'); // 'before' logs first!
```

---

## setInterval

Runs a function repeatedly at a fixed interval:

```javascript
let count = 0;
const intervalId = setInterval(() => {
  count++;
  console.log('Count:', count);
  if (count >= 5) {
    clearInterval(intervalId); // stop after 5 times
  }
}, 1000);

// Always store the ID so you can clear it
const id = setInterval(fn, 1000);
clearInterval(id);
```

---

## Countdown Timer Example

```javascript
function startCountdown(seconds) {
  let remaining = seconds;

  const id = setInterval(() => {
    console.log(remaining);
    remaining--;

    if (remaining < 0) {
      clearInterval(id);
      console.log('Done!');
    }
  }, 1000);

  return id; // return so caller can cancel
}

const timer = startCountdown(10);
// Cancel early: clearInterval(timer);
```

---

## requestAnimationFrame

For smooth animations, use `requestAnimationFrame` instead of `setInterval`:

```javascript
function animate() {
  // update animation
  requestAnimationFrame(animate); // schedule next frame
}
requestAnimationFrame(animate);
```

---

## Common Mistakes

- Not storing the timer ID (can't cancel it)
- Using `setInterval` for animations (use `requestAnimationFrame`)
- Expecting `setTimeout(fn, 0)` to run immediately (it runs after the call stack)
- Forgetting to `clearInterval` when a component unmounts (memory leak)
