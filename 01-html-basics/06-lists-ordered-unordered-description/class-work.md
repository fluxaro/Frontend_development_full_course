# Class Work — Build a Recipe Page with All List Types

## What You Will Build

A recipe page that uses all three list types: unordered list for ingredients, ordered list for steps, and description list for nutrition information.

**Time:** 35 minutes

---

## Step 1 — Set Up the Page

Create a file called `recipe-page.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Classic Spaghetti Bolognese Recipe</title>
  </head>
  <body>

  </body>
</html>
```

---

## Step 2 — Add the Title and Introduction

```html
<h1>Classic Spaghetti Bolognese</h1>
<p>A rich, hearty Italian meat sauce served over spaghetti. This recipe serves 4 people and takes about 45 minutes to make.</p>
```

---

## Step 3 — Add an Unordered List for Ingredients

Unordered because the order of ingredients does not matter — you just need them all.

```html
<h2>Ingredients</h2>

<h3>For the Sauce</h3>
<ul>
  <li>500g ground beef</li>
  <li>1 large onion, diced</li>
  <li>3 cloves garlic, minced</li>
  <li>2 cans (400g each) crushed tomatoes</li>
  <li>2 tablespoons tomato paste</li>
  <li>1 teaspoon dried oregano</li>
  <li>1 teaspoon dried basil</li>
  <li>Salt and pepper to taste</li>
  <li>2 tablespoons olive oil</li>
</ul>

<h3>For the Pasta</h3>
<ul>
  <li>400g spaghetti</li>
  <li>1 tablespoon salt (for pasta water)</li>
</ul>

<h3>To Serve</h3>
<ul>
  <li>Freshly grated Parmesan cheese</li>
  <li>Fresh basil leaves</li>
</ul>
```

**Why `<ul>`?** The order of ingredients does not matter. You just need all of them.

---

## Step 4 — Add an Ordered List for Instructions

Ordered because the steps must be followed in sequence.

```html
<h2>Instructions</h2>

<ol>
  <li>Heat olive oil in a large pan over medium heat.</li>
  <li>Add the diced onion and cook for 5 minutes until softened.</li>
  <li>Add the minced garlic and cook for 1 more minute.</li>
  <li>Add the ground beef and cook, breaking it up, until browned (about 8 minutes).</li>
  <li>Stir in the tomato paste and cook for 2 minutes.</li>
  <li>Add the crushed tomatoes, oregano, basil, salt, and pepper.</li>
  <li>Reduce heat to low and simmer for 20 minutes, stirring occasionally.</li>
  <li>While the sauce simmers, bring a large pot of salted water to a boil.</li>
  <li>Cook the spaghetti according to package instructions until al dente.</li>
  <li>Drain the pasta, reserving a cup of pasta water.</li>
  <li>Serve the sauce over the pasta. Add pasta water if the sauce is too thick.</li>
  <li>Top with Parmesan cheese and fresh basil.</li>
</ol>
```

**Why `<ol>`?** The steps must be done in this exact order. Step 8 cannot happen before step 1.

---

## Step 5 — Add a Nested List for Tips

```html
<h2>Chef's Tips</h2>

<ul>
  <li>For the best flavor:
    <ul>
      <li>Use fresh garlic, not garlic powder</li>
      <li>Let the sauce simmer for at least 20 minutes</li>
      <li>Add a splash of red wine with the tomatoes</li>
    </ul>
  </li>
  <li>For meal prep:
    <ul>
      <li>The sauce keeps in the fridge for 4 days</li>
      <li>It freezes well for up to 3 months</li>
    </ul>
  </li>
</ul>
```

---

## Step 6 — Add a Description List for Nutrition

```html
<h2>Nutrition Information</h2>
<p>Per serving (approximately):</p>

<dl>
  <dt>Calories</dt>
  <dd>520 kcal</dd>

  <dt>Protein</dt>
  <dd>32g</dd>

  <dt>Carbohydrates</dt>
  <dd>58g</dd>

  <dt>Fat</dt>
  <dd>16g</dd>

  <dt>Fiber</dt>
  <dd>4g</dd>

  <dt>Sodium</dt>
  <dd>680mg</dd>
</dl>
```

**Why `<dl>`?** Nutrition info is a set of term-value pairs — perfect for a description list.

---

## Step 7 — Add an Ordered List with Custom Start

```html
<h2>Variations to Try</h2>
<p>Once you have mastered the classic, try these variations in order of difficulty:</p>

<ol start="1">
  <li><strong>Vegetarian:</strong> Replace beef with lentils or mushrooms</li>
  <li><strong>Spicy:</strong> Add red pepper flakes and chili</li>
  <li><strong>Slow cooker:</strong> Cook on low for 6–8 hours</li>
  <li><strong>Authentic:</strong> Use a mix of beef and pork, add chicken livers</li>
</ol>
```

---

## Checklist

- [ ] `<ul>` used for ingredients (order does not matter)
- [ ] `<ol>` used for instructions (order matters)
- [ ] Nested `<ul>` inside a `<li>` for tips
- [ ] `<dl>`, `<dt>`, `<dd>` used for nutrition info
- [ ] `<ol start="...">` used for variations
- [ ] All lists are properly nested (no `<li>` outside a list)
- [ ] Page opens in browser with no errors

---

## Bonus Challenges

1. Add a `<nav>` at the top with anchor links to each section
2. Add a `<table>` for a shopping list version of the ingredients
3. Add a `reversed` attribute to one of the ordered lists
4. Add a `type="A"` attribute to an ordered list to use letters
