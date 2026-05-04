# Class Work — Typography Utilities

## What You Will Build

A typography showcase page that demonstrates every major Tailwind text utility in a visual, side-by-side format. You will see each class in action and understand what it produces.

**Time:** 40 minutes  
**Output:** `typography-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Typography Utilities Practice</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-800 p-8 font-sans max-w-4xl mx-auto">

  <h1 class="text-4xl font-bold tracking-tight text-gray-900 mb-2">Typography Utilities</h1>
  <p class="text-gray-500 mb-10">A visual reference for Tailwind's text utilities</p>

</body>
</html>
```

---

## Step 2 — Font Size Scale

Add this section inside `<body>` after the intro:

```html
<!-- FONT SIZE -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Font Size</h2>
  <div class="space-y-1">
    <p class="text-xs text-gray-700">text-xs — 0.75rem — The quick brown fox</p>
    <p class="text-sm text-gray-700">text-sm — 0.875rem — The quick brown fox</p>
    <p class="text-base text-gray-700">text-base — 1rem — The quick brown fox</p>
    <p class="text-lg text-gray-700">text-lg — 1.125rem — The quick brown fox</p>
    <p class="text-xl text-gray-700">text-xl — 1.25rem — The quick brown fox</p>
    <p class="text-2xl text-gray-700">text-2xl — 1.5rem — The quick brown fox</p>
    <p class="text-4xl text-gray-700">text-4xl — 2.25rem</p>
    <p class="text-6xl text-gray-700">text-6xl — 3.75rem</p>
  </div>
</section>
```

---

## Step 3 — Font Weight Scale

```html
<!-- FONT WEIGHT -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Font Weight</h2>
  <div class="space-y-1 text-xl text-gray-800">
    <p class="font-thin">font-thin — 100 — The quick brown fox</p>
    <p class="font-light">font-light — 300 — The quick brown fox</p>
    <p class="font-normal">font-normal — 400 — The quick brown fox</p>
    <p class="font-medium">font-medium — 500 — The quick brown fox</p>
    <p class="font-semibold">font-semibold — 600 — The quick brown fox</p>
    <p class="font-bold">font-bold — 700 — The quick brown fox</p>
    <p class="font-extrabold">font-extrabold — 800 — The quick brown fox</p>
    <p class="font-black">font-black — 900 — The quick brown fox</p>
  </div>
</section>
```

---

## Step 4 — Font Family

```html
<!-- FONT FAMILY -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Font Family</h2>
  <div class="space-y-3 text-lg">
    <p class="font-sans text-gray-700">font-sans — System sans-serif. Clean and modern. Used for most UI text.</p>
    <p class="font-serif text-gray-700">font-serif — Georgia, serif. Classic and editorial. Good for long-form reading.</p>
    <p class="font-mono text-gray-700">font-mono — Monospace. Perfect for code, numbers, and technical labels.</p>
  </div>
</section>
```

---

## Step 5 — Line Height and Letter Spacing

```html
<!-- LINE HEIGHT -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Line Height</h2>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-4 text-sm text-gray-700">
    <div class="bg-white rounded-lg p-4 border border-gray-200">
      <p class="text-xs font-bold text-gray-400 mb-2">leading-tight</p>
      <p class="leading-tight">This paragraph uses tight line height. Lines sit close together. Good for headings.</p>
    </div>
    <div class="bg-white rounded-lg p-4 border border-gray-200">
      <p class="text-xs font-bold text-gray-400 mb-2">leading-normal</p>
      <p class="leading-normal">This paragraph uses normal line height. The default browser spacing. Readable for short text.</p>
    </div>
    <div class="bg-white rounded-lg p-4 border border-gray-200">
      <p class="text-xs font-bold text-gray-400 mb-2">leading-relaxed</p>
      <p class="leading-relaxed">This paragraph uses relaxed line height. More breathing room. Best for body copy and articles.</p>
    </div>
  </div>
</section>

<!-- LETTER SPACING -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Letter Spacing</h2>
  <div class="space-y-2 text-base text-gray-700">
    <p class="tracking-tighter">tracking-tighter — Letters squeezed together</p>
    <p class="tracking-tight">tracking-tight — Slightly tighter than normal</p>
    <p class="tracking-normal">tracking-normal — Default spacing</p>
    <p class="tracking-wide">tracking-wide — Slightly more space</p>
    <p class="tracking-wider">tracking-wider — More space between letters</p>
    <p class="tracking-widest">tracking-widest — Maximum spacing — great for labels</p>
  </div>
</section>
```

---

## Step 6 — Text Transforms and Decoration

```html
<!-- TEXT TRANSFORM -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Text Transform</h2>
  <div class="space-y-2 text-lg text-gray-700">
    <p class="uppercase">uppercase — this text becomes all caps</p>
    <p class="lowercase">LOWERCASE — THIS TEXT BECOMES ALL LOWERCASE</p>
    <p class="capitalize">capitalize — each word gets a capital letter</p>
    <p class="normal-case">normal-case — No transformation applied</p>
  </div>
</section>

<!-- TEXT DECORATION -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Text Decoration</h2>
  <div class="space-y-2 text-lg text-gray-700">
    <p class="underline">underline — standard underline</p>
    <p class="underline decoration-dotted decoration-blue-500">underline decoration-dotted decoration-blue-500</p>
    <p class="underline decoration-wavy decoration-red-500">underline decoration-wavy decoration-red-500</p>
    <p class="line-through">line-through — strikethrough text</p>
    <p class="no-underline text-blue-600 cursor-pointer">no-underline — link with underline removed</p>
  </div>
</section>
```

---

## Step 7 — Truncate Demo

```html
<!-- TRUNCATE -->
<section class="mb-10">
  <h2 class="text-sm font-bold uppercase tracking-widest text-gray-400 border-b border-gray-200 pb-2 mb-4">Text Overflow / Truncate</h2>
  <div class="space-y-3">
    <div class="bg-white border border-gray-200 rounded-lg p-4 max-w-xs">
      <p class="text-xs text-gray-400 mb-1">Without truncate:</p>
      <p class="text-sm text-gray-700">This is a very long title that will wrap onto multiple lines inside this narrow container.</p>
    </div>
    <div class="bg-white border border-gray-200 rounded-lg p-4 max-w-xs">
      <p class="text-xs text-gray-400 mb-1">With truncate:</p>
      <p class="text-sm text-gray-700 truncate">This is a very long title that will wrap onto multiple lines inside this narrow container.</p>
    </div>
  </div>
</section>
```

---

## Step 8 — Verify

Open the file in your browser and check:

- [ ] Font sizes visually scale from tiny to huge
- [ ] Font weights show a clear progression from thin to black
- [ ] The three font families look noticeably different
- [ ] Line height cards show different text density
- [ ] Truncated text ends with `...` in the narrow container
- [ ] Text transforms change the case of the text

---

## Checklist

- [ ] CDN `<script>` tag is in the `<head>`
- [ ] Font size section shows at least 6 sizes
- [ ] Font weight section shows at least 6 weights
- [ ] All three font families are demonstrated
- [ ] Line height comparison uses at least 3 values
- [ ] Letter spacing section shows the full scale
- [ ] Text transform section shows all 4 values
- [ ] Truncate demo has a width constraint and shows `...`
- [ ] No custom CSS used — all Tailwind utilities

---

## Bonus Challenges

1. Add a gradient text effect: `class="text-transparent bg-clip-text bg-gradient-to-r from-purple-500 to-pink-500 text-4xl font-black"`
2. Build a "real" article header using: large title, category label (`uppercase tracking-widest text-xs`), author name, and a lead paragraph with `text-xl leading-relaxed`
3. Add a `<code>` element with `font-mono text-sm bg-gray-100 px-1.5 py-0.5 rounded text-pink-600`
