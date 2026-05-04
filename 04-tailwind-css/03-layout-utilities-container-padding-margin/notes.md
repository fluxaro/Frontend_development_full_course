# Notes — Layout Utilities

## Spacing Scale (1 unit = 4px)

| Class | Value |
|---|---|
| `p-1` / `m-1` | 4px |
| `p-2` / `m-2` | 8px |
| `p-3` / `m-3` | 12px |
| `p-4` / `m-4` | 16px (1rem) |
| `p-5` / `m-5` | 20px |
| `p-6` / `m-6` | 24px (1.5rem) |
| `p-8` / `m-8` | 32px (2rem) |
| `p-10` / `m-10` | 40px |
| `p-12` / `m-12` | 48px (3rem) |
| `p-16` / `m-16` | 64px (4rem) |

## Container Pattern

```html
<div class="container mx-auto px-4">
  <!-- centered, max-width, side padding -->
</div>
```

## Centering Patterns

```html
<!-- Center a block element -->
<div class="mx-auto max-w-lg">...</div>

<!-- Center content inside a div -->
<div class="flex items-center justify-center">...</div>

<!-- Center text -->
<p class="text-center">...</p>
```

## Overflow

```html
overflow-hidden   <!-- clip content -->
overflow-auto     <!-- scroll when needed -->
overflow-x-auto   <!-- horizontal scroll only -->
truncate          <!-- single-line ellipsis -->
```

## Common Mistakes

- `container` alone does nothing — always add `mx-auto`
- `w-full` on a flex child may not work as expected — use `flex-1` instead
- Negative margins (`-mt-4`) are powerful but can cause layout issues
- `space-y-*` adds margin to all children except the first — don't add extra `mt-*` on children
