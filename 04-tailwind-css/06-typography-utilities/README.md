# Typography Utilities in Tailwind CSS

Typography is one of the most-used areas of Tailwind. Instead of writing `font-size`, `font-weight`, `line-height`, and `letter-spacing` in a CSS file, you apply them directly in HTML with single-purpose utility classes.

---

## Font Size — `text-*`

Tailwind provides a full type scale from `text-xs` to `text-9xl`:

```html
<p class="text-xs">Extra small — 0.75rem</p>
<p class="text-sm">Small — 0.875rem</p>
<p class="text-base">Base — 1rem (default)</p>
<p class="text-lg">Large — 1.125rem</p>
<p class="text-xl">XL — 1.25rem</p>
<p class="text-2xl">2XL — 1.5rem</p>
<p class="text-4xl">4XL — 2.25rem</p>
<p class="text-6xl">6XL — 3.75rem</p>
<p class="text-9xl">9XL — 8rem</p>
```

---

## Font Weight — `font-*`

```html
<p class="font-thin">Thin — 100</p>
<p class="font-light">Light — 300</p>
<p class="font-normal">Normal — 400</p>
<p class="font-medium">Medium — 500</p>
<p class="font-semibold">Semibold — 600</p>
<p class="font-bold">Bold — 700</p>
<p class="font-extrabold">Extrabold — 800</p>
<p class="font-black">Black — 900</p>
```

---

## Font Family — `font-sans`, `font-serif`, `font-mono`

```html
<p class="font-sans">System sans-serif stack (default)</p>
<p class="font-serif">Georgia, serif stack</p>
<p class="font-mono">Monospace — great for code</p>
```

---

## Line Height — `leading-*`

Controls the space between lines of text:

```html
<p class="leading-none">No extra line spacing (1)</p>
<p class="leading-tight">Tight (1.25)</p>
<p class="leading-snug">Snug (1.375)</p>
<p class="leading-normal">Normal (1.5)</p>
<p class="leading-relaxed">Relaxed (1.625)</p>
<p class="leading-loose">Loose (2)</p>
```

---

## Letter Spacing — `tracking-*`

Controls the space between characters:

```html
<p class="tracking-tighter">Tighter — -0.05em</p>
<p class="tracking-tight">Tight — -0.025em</p>
<p class="tracking-normal">Normal — 0em</p>
<p class="tracking-wide">Wide — 0.025em</p>
<p class="tracking-wider">Wider — 0.05em</p>
<p class="tracking-widest">Widest — 0.1em</p>
```

---

## Text Alignment — `text-left`, `text-center`, `text-right`, `text-justify`

```html
<p class="text-left">Left aligned</p>
<p class="text-center">Center aligned</p>
<p class="text-right">Right aligned</p>
<p class="text-justify">Justified — spreads text to fill the full width of the container</p>
```

---

## Text Decoration — `underline`, `line-through`, `no-underline`

```html
<p class="underline">Underlined text</p>
<p class="line-through">Strikethrough text</p>
<a class="no-underline">Link with no underline</a>
<p class="underline decoration-dotted decoration-red-500">Custom underline style</p>
```

---

## Text Transform — `uppercase`, `lowercase`, `capitalize`, `normal-case`

```html
<p class="uppercase">becomes ALL CAPS</p>
<p class="lowercase">BECOMES all lowercase</p>
<p class="capitalize">each word gets Capitalized</p>
<p class="normal-case">No transformation applied</p>
```

---

## Text Overflow — `truncate`, `text-ellipsis`, `text-clip`

```html
<!-- truncate requires a width constraint -->
<p class="truncate w-48">This long text will be cut off with an ellipsis...</p>
<p class="overflow-hidden text-ellipsis whitespace-nowrap w-48">Same effect, explicit</p>
```

---

## Text Color — `text-*`

```html
<p class="text-gray-900">Near black</p>
<p class="text-gray-500">Medium gray</p>
<p class="text-blue-600">Blue</p>
<p class="text-red-500">Red</p>
<p class="text-green-600">Green</p>
<p class="text-transparent bg-clip-text bg-gradient-to-r from-purple-500 to-pink-500">Gradient text</p>
```

---

## Common Patterns

**Article heading hierarchy:**
```html
<h1 class="text-4xl font-bold tracking-tight text-gray-900">Main Title</h1>
<h2 class="text-2xl font-semibold text-gray-800 mt-8">Section Heading</h2>
<p class="text-base text-gray-600 leading-relaxed mt-4">Body text with comfortable reading line height.</p>
```

**Label / badge text:**
```html
<span class="text-xs font-bold uppercase tracking-widest text-blue-600">Category</span>
```

---

## Common Mistakes

- Using `text-*` for both font size and text color — context makes it clear, but `text-lg` is size and `text-blue-500` is color
- Forgetting `truncate` needs a width constraint — without `w-*` or `max-w-*`, it won't clip
- Using `capitalize` when you want `uppercase` — `capitalize` only capitalizes the first letter of each word
- Setting `leading-none` on multi-line body text — lines will overlap; use `leading-relaxed` for readability
