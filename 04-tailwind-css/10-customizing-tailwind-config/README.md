# 10 — Customizing Tailwind Config

## What Is This Lesson About?

Tailwind's real power comes from its configuration system. You can extend the default theme with custom colors, spacing, fonts, breakpoints, and more — without losing any of the built-in utilities. This lesson covers `tailwind.config.js` in depth and shows you how to use the CDN config approach for quick customization without a build step.

---

## The Config File

In a project with a build step, you configure Tailwind in `tailwind.config.js`:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./src/**/*.{html,js}'],
  theme: {
    extend: {
      // Your customizations go here
    },
  },
  plugins: [],
}
```

---

## CDN Config (No Build Step)

When using the CDN, you can configure Tailwind with a `<script>` block after the CDN script:

```html
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          brand: {
            50:  '#eff6ff',
            100: '#dbeafe',
            500: '#3b82f6',
            600: '#2563eb',
            900: '#1e3a8a',
          }
        }
      }
    }
  }
</script>
```

Now you can use `bg-brand-500`, `text-brand-600`, etc.

---

## theme vs theme.extend

| | `theme` | `theme.extend` |
|---|---|---|
| Effect | **Replaces** the default theme | **Adds to** the default theme |
| Use case | Complete custom design system | Adding custom values alongside defaults |
| Risk | Loses all built-in colors/spacing | Safe — keeps all defaults |

**Always use `theme.extend`** unless you intentionally want to replace the entire default theme.

```js
// ❌ This removes ALL default colors
theme: {
  colors: { brand: '#3b82f6' }
}

// ✅ This adds brand color alongside all defaults
theme: {
  extend: {
    colors: { brand: '#3b82f6' }
  }
}
```

---

## Custom Colors

```js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        // Simple single color
        brand: '#6366f1',

        // Color with shades
        primary: {
          50:  '#f0f9ff',
          100: '#e0f2fe',
          200: '#bae6fd',
          300: '#7dd3fc',
          400: '#38bdf8',
          500: '#0ea5e9',
          600: '#0284c7',
          700: '#0369a1',
          800: '#075985',
          900: '#0c4a6e',
        },

        // Semantic colors
        success: '#22c55e',
        warning: '#f59e0b',
        danger:  '#ef4444',
      }
    }
  }
}
```

Usage:

```html
<div class="bg-primary-500 text-white">Primary</div>
<div class="bg-success text-white">Success</div>
<div class="text-danger">Error message</div>
```

---

## Custom Spacing

```js
tailwind.config = {
  theme: {
    extend: {
      spacing: {
        '18': '4.5rem',   // w-18, p-18, m-18
        '88': '22rem',    // w-88
        '128': '32rem',   // max-w-128
      }
    }
  }
}
```

---

## Custom Font Families

```js
tailwind.config = {
  theme: {
    extend: {
      fontFamily: {
        sans: ['Inter', 'ui-sans-serif', 'system-ui'],
        display: ['Cal Sans', 'Inter', 'sans-serif'],
        mono: ['JetBrains Mono', 'ui-monospace'],
      }
    }
  }
}
```

Usage: `font-sans`, `font-display`, `font-mono`

---

## Custom Font Sizes

```js
tailwind.config = {
  theme: {
    extend: {
      fontSize: {
        'xxs': '0.625rem',          // text-xxs
        'display': ['4.5rem', {     // text-display with line-height
          lineHeight: '1',
          letterSpacing: '-0.02em',
          fontWeight: '700',
        }],
      }
    }
  }
}
```

---

## Custom Border Radius

```js
tailwind.config = {
  theme: {
    extend: {
      borderRadius: {
        '4xl': '2rem',
        '5xl': '2.5rem',
      }
    }
  }
}
```

---

## Custom Breakpoints

```js
tailwind.config = {
  theme: {
    extend: {
      screens: {
        'xs': '480px',    // sm: prefix for extra small
        '3xl': '1920px',  // 3xl: prefix for very large screens
      }
    }
  }
}
```

---

## Custom Box Shadows

```js
tailwind.config = {
  theme: {
    extend: {
      boxShadow: {
        'glow': '0 0 20px rgba(99, 102, 241, 0.5)',
        'card': '0 2px 8px rgba(0, 0, 0, 0.08), 0 0 1px rgba(0, 0, 0, 0.1)',
      }
    }
  }
}
```

Usage: `shadow-glow`, `shadow-card`

---

## Custom Animations

```js
tailwind.config = {
  theme: {
    extend: {
      keyframes: {
        'fade-in': {
          '0%': { opacity: '0', transform: 'translateY(10px)' },
          '100%': { opacity: '1', transform: 'translateY(0)' },
        },
        'slide-in': {
          '0%': { transform: 'translateX(-100%)' },
          '100%': { transform: 'translateX(0)' },
        }
      },
      animation: {
        'fade-in': 'fade-in 0.3s ease-out',
        'slide-in': 'slide-in 0.4s ease-out',
      }
    }
  }
}
```

Usage: `animate-fade-in`, `animate-slide-in`

---

## Using CSS Variables with Config

```js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        // Reference CSS variables for runtime theming
        primary: 'rgb(var(--color-primary) / <alpha-value>)',
      }
    }
  }
}
```

```css
:root { --color-primary: 99 102 241; }
.theme-blue { --color-primary: 59 130 246; }
```

---

## Common Mistakes

- Using `theme` instead of `theme.extend` — accidentally removes all default utilities
- Defining colors without shades — `brand: '#3b82f6'` works but you can't use `brand-500`
- Forgetting to add the CDN config script **after** the CDN script tag
- Using hex colors in CSS variable references — use space-separated RGB values instead
- Defining custom spacing with the same key as a default — it will override, not add
