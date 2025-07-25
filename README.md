# 🎯 The Ultimate Guide to HTML & CSS Selectors

A comprehensive deep-dive covering **everything** about selectors in HTML and CSS — from beginner to expert level.

---

## 📌 Table of Contents

1. Introduction to Selectors
2. Basic CSS Selectors
3. Grouping Selectors
4. Combinator Selectors (Relationships)
5. Attribute Selectors
6. Pseudo-Classes
7. Pseudo-Elements
8. Specificity and Priority
9. Advanced Selectors (Level 4)
10. Scoping and Component CSS
11. Real-World Examples
12. Practice Resources & Tools
13. Summary Tables

---

## 1. Introduction to Selectors

Selectors in CSS are used to target HTML elements for styling. They act as queries that match elements based on types, classes, IDs, attributes, relationships, states, and more.

**Syntax:**

```css
selector {
  property: value;
}
```

---

## 2. Basic CSS Selectors

| Selector  | Syntax     | Description                       |
| --------- | ---------- | --------------------------------- |
| Universal | `*`        | Selects all elements              |
| Type      | `div`, `p` | Selects all elements of that type |
| Class     | `.class`   | Selects all elements with a class |
| ID        | `#id`      | Selects the element with that ID  |

**Example:**

```css
* {
  box-sizing: border-box;
}
p {
  font-size: 16px;
}
.box {
  padding: 10px;
}
#main {
  margin: 0 auto;
}
```

---

## 3. Grouping Selectors

Apply the same styles to multiple elements:

```css
h1, h2, h3 {
  font-family: Arial, sans-serif;
}
```

---

## 4. Combinator Selectors (Relationships)

### 4.1 Descendant Selector (`A B`)

* Selects all `B` elements that are **inside** `A`, at any depth.

```css
div p {
  color: green;
}
```

### 4.2 Child Selector (`A > B`)

* Selects all `B` elements that are **direct children** of `A`.

```css
ul > li {
  list-style: none;
}
```

### 4.3 Adjacent Sibling Selector (`A + B`)

* Selects the **first `B` sibling** immediately following `A`.

```css
h1 + p {
  font-weight: bold;
}
```

### 4.4 General Sibling Selector (`A ~ B`)

* Selects **all `B` siblings** that follow `A`.

```css
h1 ~ p {
  color: gray;
}
```

---

## 5. Attribute Selectors

| Syntax          | Description                 |
| --------------- | --------------------------- |
| `[attr]`        | Element with that attribute |
| `[attr=value]`  | Attribute equal to value    |
| `[attr~=value]` | Attribute contains word     |
| `[attr^=value]` | Starts with value           |
| `[attr$=value]` | Ends with value             |
| `[attr*=value]` | Contains value              |

```css
input[type="text"] {
  border: 1px solid black;
}
a[href^="https"] {
  color: green;
}
```

---

## 6. Pseudo-Classes

Pseudo-classes select elements in a specific **state** or **position**.

### 6.1 User Interaction

```css
a:hover {
  color: orange;
}
input:focus {
  outline: 2px solid green;
}
button:active {
  transform: scale(0.98);
}
```

### 6.2 Structural

```css
ul li:first-child {
  font-weight: bold;
}
ul li:nth-child(odd) {
  background: #f0f0f0;
}
p:only-child {
  color: red;
}
```

### 6.3 Form-Related

```css
input:required {
  border-color: red;
}
input:checked + label {
  font-weight: bold;
}
```

### 6.4 Negation and Matching

```css
button:not(.primary) {
  background: gray;
}
```

### 6.5 Level 4 Pseudo-Classes

```css
:is(h1, h2, h3) {
  font-family: sans-serif;
}
:where(section, article) {
  margin: 0;
}
article:has(img) {
  border: 1px solid gray;
}
```

---

## 7. Pseudo-Elements

Pseudo-elements let you style **parts** of an element.

| Pseudo-element   | Description                  |
| ---------------- | ---------------------------- |
| `::before`       | Content before the element   |
| `::after`        | Content after the element    |
| `::first-letter` | First letter of element text |
| `::first-line`   | First line of text           |
| `::selection`    | Selected text                |
| `::placeholder`  | Placeholder text in input    |
| `::marker`       | Bullet in lists              |

**Examples:**

```css
.card::before {
  content: "🔥 ";
}
input::placeholder {
  color: gray;
}
p::first-letter {
  font-size: 2em;
  color: red;
}
```

---

## 8. Specificity and Priority

| Selector           | Specificity Score    |
| ------------------ | -------------------- |
| `*`                | 0                    |
| `element`          | 1                    |
| `.class`, `:hover` | 10                   |
| `#id`              | 100                  |
| Inline styles      | 1000                 |
| `!important`       | Overrides everything |

---

## 9. Advanced Selectors (Level 4)

### `:is()` and `:where()`

```css
:is(h1, h2, h3) {
  color: darkblue;
}
:where(header, footer) {
  margin: 0;
}
```

### `:has()`

```css
div:has(img) {
  padding: 1rem;
}
```

---

## 10. CSS Scoping & Component-Level Styling

* **CSS Modules**
* **BEM naming convention**
* **Utility-first (Tailwind)**
* **Scoped styles (Vue, Svelte)**

Example BEM:

```css
.card__title {
  font-size: 20px;
}
.card--highlighted {
  border-color: orange;
}
```

---

## 11. Real-World Examples

### Navigation

```css
nav ul > li:first-child a {
  color: red;
}
```

### FAQ Accordion

```css
h3 + p {
  font-style: italic;
}
```

### Highlight Search

```css
p mark {
  background: yellow;
}
```

### Input Validation

```css
input:invalid {
  border-color: red;
}
```

---

## 12. Practice Tools & Resources

* 🧪 CSS Diner: [https://flukeout.github.io](https://flukeout.github.io)
* 🎯 CSS Battle: [https://cssbattle.dev](https://cssbattle.dev)
* ✅ Specificity Calculator: [https://specificity.keegan.st](https://specificity.keegan.st)
* 📘 Selector Cheatsheet: [https://frontend30.com/css-selectors-cheatsheet](https://frontend30.com/css-selectors-cheatsheet)

---

## 13. Summary Tables

### Selector Types

| Type           | Example            | Target                      |
| -------------- | ------------------ | --------------------------- |
| Universal      | `*`                | All elements                |
| Type           | `div`              | All `div` elements          |
| Class          | `.box`             | Elements with class `box`   |
| ID             | `#main`            | Element with ID `main`      |
| Attribute      | `[type="text"]`    | Input fields with type text |
| Pseudo-class   | `:hover`           | Hovered elements            |
| Pseudo-element | `::after`          | Content after an element    |
| Combinators    | `div > p`, `a + p` | Relational targets          |

---

> ✅ This guide is designed to be your one-stop reference. Bookmark it, practice it, and you'll master selectors in no time.

---
