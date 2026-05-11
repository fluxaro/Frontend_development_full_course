# Notes — Customizing Tailwind Config

## CDN Config (No Build Step)

```html
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        // customizations here
      }
    }
  }
</script>
```

---

## theme vs theme.extend

```js
// ❌ Replaces ALL defaults
theme: { colors: { brand: '#6366f1' } }

// ✅ Adds to defaults
theme: { extend: { colors: { brand: '#6366f1' } } }
```

---

## Custom Colors

```js
theme: {
  extend: {
    colors: {
      // Single color
      brand: '#6366f1',

      // With shades
      primary: {
        50: '#f0f9ff',
        500: '#0ea5e9',
        900: '#0c4a6e',
      },

      // Semantic
      success: '#22c55e',
      warning: '#f59e0b',
      danger:  '#ef4444',
    }
  }
}
// Usage: bg-brand, bg-primary-500, text-danger
```

---

## Custom Spacing

```js
theme: {
  extend: {
    spacing: {
      '18': '4.5rem',   // w-18, p-18, m-18
      '88': '22rem',
      '128': '32rem',
    }
  }
}
```

---

## Custom Fonts

```js
theme: {
  extend: {
    fontFamily: {
      sans: ['Inter', 'ui-sans-serif'],
      display: ['Cal Sans', 'Inter', 'sans-serif'],
      mono: ['JetBrains Mono', 'monospace'],
    }
  }
}
// Usage: font-sans, font-display, font-mono
```

---

## Custom Font Sizes

```js
theme: {
  extend: {
    fontSize: {
      'xxs': '0.625rem',
      'display': ['4.5rem', { lineHeight: '1', letterSpacing: '-0.02em' }],
    }
  }
}
// Usage: text-xxs, text-display
```

---

## Custom Border Radius

```js
theme: {
  extend: {
    borderRadius: {
      '4xl': '2rem',
      '5xl': '2.5rem',
    }
  }
}
// Usage: rounded-4xl, rounded-5xl
```

---

## Custom Breakpoints

```js
theme: {
  extend: {
    screens: {
      'xs': '480px',
      '3xl': '1920px',
    }
  }
}
// Usage: xs:text-sm, 3xl:grid-cols-6
```

---

## Custom Shadows

```js
theme: {
  extend: {
    boxShadow: {
      'glow': '0 0 20px rgba(99, 102, 241, 0.5)',
      'card': '0 2px 8px rgba(0,0,0,0.08)',
    }
  }
}
// Usage: shadow-glow, shadow-card
```

---

## Custom Animations

```js
theme: {
  extend: {
    keyframes: {
      'fade-in': {
        '0%': { opacity: '0', transform: 'translateY(10px)' },
        '100%': { opacity: '1', transform: 'translateY(0)' },
      }
    },
    animation: {
      'fade-in': 'fade-in 0.3s ease-out',
    }
  }
}
// Usage: animate-fade-in
```

---

## Dark Mode Config

```js
tailwind.config = {
  darkMode: 'class',  // or 'media'
  theme: { extend: { ... } }
}
```

---

## Common Mistakes

- `theme` instead of `theme.extend` — removes all defaults
- Config script must come **after** the CDN script
- Single color `brand: '#hex'` — can't use `brand-500`, only `brand`
- Hex in CSS variable colors — use space-separated RGB: `'99 102 241'`
