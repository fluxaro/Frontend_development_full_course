# Notes — Typography Utilities

## Font Size

```html
text-xs    <!-- 0.75rem  -->
text-sm    <!-- 0.875rem -->
text-base  <!-- 1rem     -->
text-lg    <!-- 1.125rem -->
text-xl    <!-- 1.25rem  -->
text-2xl   <!-- 1.5rem   -->
text-3xl   <!-- 1.875rem -->
text-4xl   <!-- 2.25rem  -->
text-5xl   <!-- 3rem     -->
text-6xl   <!-- 3.75rem  -->
text-7xl   <!-- 4.5rem   -->
text-8xl   <!-- 6rem     -->
text-9xl   <!-- 8rem     -->
```

## Font Weight

```html
font-thin       <!-- 100 -->
font-extralight <!-- 200 -->
font-light      <!-- 300 -->
font-normal     <!-- 400 -->
font-medium     <!-- 500 -->
font-semibold   <!-- 600 -->
font-bold       <!-- 700 -->
font-extrabold  <!-- 800 -->
font-black      <!-- 900 -->
```

## Font Family

```html
font-sans   <!-- ui-sans-serif, system-ui, ... -->
font-serif  <!-- ui-serif, Georgia, ...        -->
font-mono   <!-- ui-monospace, monospace, ...  -->
```

## Line Height

```html
leading-none    <!-- 1     -->
leading-tight   <!-- 1.25  -->
leading-snug    <!-- 1.375 -->
leading-normal  <!-- 1.5   -->
leading-relaxed <!-- 1.625 -->
leading-loose   <!-- 2     -->
leading-3 through leading-10  <!-- fixed rem values -->
```

## Letter Spacing

```html
tracking-tighter <!-- -0.05em -->
tracking-tight   <!-- -0.025em -->
tracking-normal  <!-- 0em      -->
tracking-wide    <!-- 0.025em  -->
tracking-wider   <!-- 0.05em   -->
tracking-widest  <!-- 0.1em    -->
```

## Text Alignment

```html
text-left
text-center
text-right
text-justify
text-start
text-end
```

## Text Decoration

```html
underline
overline
line-through
no-underline

decoration-solid
decoration-dashed
decoration-dotted
decoration-double
decoration-wavy

decoration-{color}   <!-- decoration-red-500 -->
decoration-1 through decoration-8  <!-- thickness -->
underline-offset-1 through underline-offset-8
```

## Text Transform

```html
uppercase
lowercase
capitalize
normal-case
```

## Text Overflow

```html
truncate          <!-- overflow:hidden + text-overflow:ellipsis + whitespace:nowrap -->
text-ellipsis     <!-- text-overflow: ellipsis -->
text-clip         <!-- text-overflow: clip     -->
overflow-hidden   <!-- needed with text-ellipsis -->
whitespace-nowrap <!-- prevents wrapping        -->
```

## Text Color

```html
text-black
text-white
text-gray-{50-950}
text-red-{50-950}
text-blue-{50-950}
text-green-{50-950}
text-yellow-{50-950}
text-purple-{50-950}
text-pink-{50-950}
text-transparent  <!-- use with bg-clip-text for gradients -->
```

## Common Combos

```html
<!-- Hero heading -->
<h1 class="text-5xl font-bold tracking-tight leading-tight text-gray-900">

<!-- Body copy -->
<p class="text-base font-normal leading-relaxed text-gray-600">

<!-- Label / badge -->
<span class="text-xs font-bold uppercase tracking-widest text-blue-600">

<!-- Code snippet -->
<code class="font-mono text-sm text-pink-600">

<!-- Truncated card title -->
<h3 class="text-lg font-semibold truncate w-full">
```
