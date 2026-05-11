# Notes — Hover, Focus, Active, and Dark Mode

## State Variant Syntax

```html
{variant}:{utility}

hover:bg-blue-700
focus:ring-2
active:scale-95
dark:bg-gray-900
group-hover:opacity-100
peer-checked:bg-blue-600
focus-visible:ring-2
disabled:opacity-50
```

---

## Hover

```html
hover:bg-blue-700          <!-- background on hover -->
hover:text-gray-900        <!-- text color on hover -->
hover:shadow-xl            <!-- shadow on hover -->
hover:scale-105            <!-- scale up on hover -->
hover:opacity-100          <!-- opacity on hover -->
hover:underline            <!-- underline on hover -->
hover:-translate-y-1       <!-- lift on hover -->
```

---

## Focus

```html
focus:outline-none         <!-- remove default outline -->
focus:ring-2               <!-- add ring -->
focus:ring-blue-500        <!-- ring color -->
focus:ring-offset-2        <!-- gap between element and ring -->
focus:border-blue-500      <!-- border color on focus -->
```

---

## Focus Visible (Accessible)

```html
<!-- Only shows ring on keyboard focus, not mouse click -->
focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500
```

---

## Active

```html
active:bg-blue-800         <!-- darker on press -->
active:scale-95            <!-- shrink on press -->
active:shadow-inner        <!-- inset shadow on press -->
```

---

## Disabled

```html
disabled:opacity-50
disabled:cursor-not-allowed
disabled:pointer-events-none
```

---

## Group Hover

```html
<!-- Parent -->
<div class="group">

<!-- Children react to parent hover -->
<h3 class="group-hover:text-blue-600">
<span class="opacity-0 group-hover:opacity-100">
<div class="translate-x-0 group-hover:translate-x-2">
```

---

## Peer

```html
<!-- Sibling reacts to peer's state -->
<input class="peer" type="checkbox">
<label class="peer-checked:text-blue-600">

<input class="peer" type="email" required>
<p class="hidden peer-invalid:block text-red-500">Invalid email</p>
```

---

## Dark Mode

```html
<!-- Enable class-based dark mode -->
<script>tailwind.config = { darkMode: 'class' }</script>

<!-- Toggle -->
<button onclick="document.documentElement.classList.toggle('dark')">

<!-- Usage -->
bg-white dark:bg-gray-900
text-gray-900 dark:text-white
text-gray-600 dark:text-gray-400
border-gray-200 dark:border-gray-700
bg-white dark:bg-gray-800
```

---

## Transitions

```html
transition              <!-- common properties -->
transition-all          <!-- all properties -->
transition-colors       <!-- color only -->
transition-opacity      <!-- opacity only -->
transition-transform    <!-- transform only -->
transition-shadow       <!-- shadow only -->

duration-75    duration-100    duration-150
duration-200   duration-300    duration-500

ease-linear    ease-in    ease-out    ease-in-out
```

---

## Common Combos

```html
<!-- Interactive button -->
<button class="bg-blue-600 hover:bg-blue-700 active:bg-blue-800 active:scale-95 
               focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2
               transition-all duration-150 text-white px-4 py-2 rounded-lg">

<!-- Hover card -->
<div class="group bg-white hover:shadow-xl transition-shadow cursor-pointer rounded-xl p-6">
  <h3 class="group-hover:text-blue-600 transition-colors font-bold">Title</h3>
  <span class="opacity-0 group-hover:opacity-100 transition-opacity">Read more →</span>
</div>

<!-- Dark mode card -->
<div class="bg-white dark:bg-gray-800 border border-gray-100 dark:border-gray-700 rounded-xl p-6">
  <h3 class="text-gray-900 dark:text-white font-bold">Title</h3>
  <p class="text-gray-500 dark:text-gray-400">Description</p>
</div>

<!-- Accessible input -->
<input class="border border-gray-300 dark:border-gray-600 rounded-lg px-3 py-2
              bg-white dark:bg-gray-800 text-gray-900 dark:text-white
              focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent">
```

---

## Common Mistakes

- Forgetting `transition-*` — state changes are instant
- Using `focus:` instead of `focus-visible:` for keyboard accessibility
- `dark:text-white` without a light mode color
- `group-hover:` without `group` on the parent
- Forgetting `outline-none` when adding custom focus rings
