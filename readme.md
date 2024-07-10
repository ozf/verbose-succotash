# HTML & CSS Tips and Tricks

## Table of Contents
- [HTML](#html)
  - [Use Semantic Elements](#use-semantic-elements)
  - [Use Proper HTML Structure](#use-proper-html-structure)
  - [Use Short and Clean Code](#use-short-and-clean-code)
  - [Accessibility](#accessibility)
  - [Language and Encoding](#language-and-encoding)
  - [Performance](#performance)
- [CSS](#css)
  - [Always Use Semicolons](#always-use-semicolons)
  - [Box Model](#box-model)
  - [Don't Change Element Flow](#dont-change-element-flow)
  - [Use Modern Layout Techniques](#use-modern-layout-techniques)
  - [Simple and Specific Selectors](#simple-and-specific-selectors)
  - [Avoid !important](#avoid-important)
  - [Don't Override Styles Unnecessarily](#dont-override-styles-unnecessarily)
  - [Inherit Styles When Possible](#inherit-styles-when-possible)
  - [Keep Code Short](#keep-code-short)
  - [Use Readable Units](#use-readable-units)
  - [Use Hexadecimal Colors](#use-hexadecimal-colors)
  - [Create Simple Shapes with CSS](#create-simple-shapes-with-css)
  - [Avoid Hacks](#avoid-hacks)
  - [CSS Variables](#css-variables)
  - [CSS Grid Layout](#css-grid-layout)
  - [Flexbox Tips](#flexbox-tips)
- [Browser Compatibility](#browser-compatibility)
- [Debugging Tools](#debugging-tools)
- [Accessibility Enhancements](#accessibility-enhancements)
- [SEO Best Practices](#seo-best-practices)

## HTML

### Use Semantic Elements
Semantic elements help structure your content better.

```html
<!-- bad -->
<div id="main">
  <div class="article">
    <div class="header">
      <h1>Blog post</h1>
      <p>Published: <span>21st Feb, 2015</span></p>
    </div>
    <p>…</p>
  </div>
</div>

<!-- good -->
<main>
  <article>
    <header>
      <h1>Blog post</h1>
      <p>Published: <time datetime="2015-02-21">21st Feb, 2015</time></p>
    </header>
    <p>…</p>
  </article>
</main>
```

### Use Proper HTML Structure
Use proper HTML5 structure to make your code cleaner and easier to read.

```html
<!-- bad -->
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Web Page</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>

<!-- good -->
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Web Page</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

### Use Short and Clean Code
HTML5 allows for shorter and cleaner code.

```html
<!-- bad -->
<!doctype html>
<html lang="en">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>Contact</title>
    <link rel="stylesheet" href="style.css" type="text/css">
  </head>
  <body>
    <h1>Contact me</h1>
    <label>
      Email address:
      <input type="email" placeholder="you@email.com" required="required">
    </label>
    <script src="main.js" type="text/javascript"></script>
  </body>
</html>

<!-- good -->
<!doctype html>
<html lang="en">
  <meta charset="UTF-8">
  <title>Contact</title>
  <link rel="stylesheet" href="style.css">
  <body>
    <h1>Contact me</h1>
    <label>
      Email address:
      <input type="email" placeholder="you@email.com" required>
    </label>
    <script src="main.js"></script>
  </body>
</html>
```

### Accessibility
Improve accessibility with simple steps like proper `alt` attributes and clear labels.

```html
<!-- bad -->
<h1><img src="logo.png" alt=""></h1>

<!-- good -->
<h1><img src="logo.png" alt="Company"></h1>
```

### Language and Encoding
Always define the language and use UTF-8 encoding.

```html
<!-- bad -->
<!doctype html>
<title>Hello, world.</title>

<!-- good -->
<!doctype html>
<html lang="en">
  <meta charset="UTF-8">
  <title>Hello, world.</title>
</html>
```

### Performance
Load scripts after the content to improve page load times.

```html
<!-- bad -->
<!doctype html>
<meta charset="UTF-8">
<script src="analytics.js"></script>
<title>Hello, world.</title>
<p>...</p>

<!-- good -->
<!doctype html>
<meta charset="UTF-8">
<title>Hello, world.</title>
<p>...</p>
<script src="analytics.js"></script>
```

## CSS

### Always Use Semicolons
Even though semicolons are separators, always use them.

```css
/* bad */
div {
  color: red
}

/* good */
div {
  color: red;
}
```

### Box Model
Use the same box model for the entire document.

```css
/* bad */
div {
  width: 100%;
  padding: 10px;
  box-sizing: border-box;
}

/* good */
* {
  box-sizing: border-box;
}
```

### Don't Change Element Flow
Avoid changing the default flow of elements.

```css
/* bad */
img {
  display: block;
}

/* good */
img {
  vertical-align: middle;
}
```

### Use Modern Layout Techniques
Prefer Flexbox and Grid over older layout methods.

```css
/* bad */
div {
  width: 100px;
  position: absolute;
  right: 0;
}

/* good */
.container {
  display: flex;
  justify-content: flex-end;
}
```

### Simple and Specific Selectors
Keep selectors simple and specific.

```css
/* bad */
div:first-of-type :last-child > p ~ *

/* good */
div:first-of-type .info
```

### Avoid !important
Avoid using `!important` to make styles easier to override.

```css
/* bad */
.bar {
  color: green !important;
}
.foo {
  color: red;
}

/* good */
.foo.bar {
  color: green;
}
.foo {
  color: red;
}
```

### Don't Override Styles Unnecessarily
Minimize style overrides to keep code clean.

```css
/* bad */
li {
  visibility: hidden;
}
li:first-child {
  visibility: visible;
}

/* good */
li + li {
  visibility: hidden;
}
```

### Inherit Styles When Possible
Use inheritance to avoid repetitive styles.

```css
/* bad */
div h1, div p {
  text-shadow: 0 1px 0 #fff;
}

/* good */
div {
  text-shadow: 0 1px 0 #fff;
}
```

### Keep Code Short
Use shorthand properties and concise code.

```css
/* bad */
div {
  transition: all 1s;
  top: 50%;
  margin-top: -10px;
  padding-top: 5px;
  padding-right: 10px;
  padding-bottom: 20px;
  padding-left: 10px;
}

/* good */
div {
  transition: 1s;
  top: calc(50% - 10px);
  padding: 5px 10px 20px;
}
```

### Use Readable Units
Prefer `rem` and unitless values when possible.

```css
/* bad */
div {
  margin: 0px;
  font-size: .9em;
  line-height: 22px;
  transition: 500ms;
}

/* good */
div {
  margin: 0;
  font-size: .9rem;
  line-height: 1.5;
  transition: .5s;
}
```

### Use Hexadecimal Colors
Use hex colors for simplicity unless you need transparency.

```css
/*

 bad */
div {
  color: hsl(103, 54%, 43%);
}

/* good */
div {
  color: #5a3;
}
```

### Create Simple Shapes with CSS
Avoid additional HTTP requests by creating shapes with CSS.

```css
/* bad */
div::before {
  content: url(white-circle.svg);
}

/* good */
div::before {
  content: "";
  display: block;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #fff;
}
```

### Avoid Hacks
Use clean and standard solutions instead of hacks.

```css
/* bad */
div {
  // position: relative;
  transform: translateZ(0);
}

/* good */
div {
  /* position: relative; */
  will-change: transform;
}
```

### CSS Variables
CSS variables make it easier to maintain and update your styles.

```css
:root {
  --main-bg-color: #fff;
  --main-text-color: #333;
}

body {
  background-color: var(--main-bg-color);
  color: var(--main-text-color);
}
```

### CSS Grid Layout
Use CSS Grid for complex layouts.

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}

.item {
  background-color: #ccc;
  padding: 20px;
}
```

### Flexbox Tips
Flexbox is great for 1D layouts.

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.item {
  padding: 10px;
  background-color: #ccc;
}
```

## Browser Compatibility
Use tools like Autoprefixer to ensure compatibility across different browsers.

```css
/* bad */
.box {
  display: flex;
}

/* good */
.box {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}
```

## Debugging Tools
Use browser developer tools to debug and test your HTML and CSS.

- Chrome DevTools
- Firefox Developer Tools
- Safari Web Inspector

## Accessibility Enhancements
Enhance accessibility by using ARIA roles and ensuring color contrast.

```html
<!-- bad -->
<button>Click</button>

<!-- good -->
<button aria-label="Close">X</button>
```

## SEO Best Practices
Improve SEO with proper HTML structure and meta tags.

```html
<!-- bad -->
<title>Page</title>

<!-- good -->
<title>My Awesome Page</title>
<meta name="description" content="This is a description of my awesome page.">
```
