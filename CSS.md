# 🎯 CSS Sheet

---

## 🔹 Selectors

Use selectors to target HTML elements:

- **Element Selector**: Targets all elements of a type.
- **Class Selector**: Targets elements with a class (`.`).
- **ID Selector**: Targets elements with a specific ID (`#`).

```css
div {
  color: blue;
}

.box {
  padding: 10px;
}

#header {
  background-color: lightgray;
}
```

---

## 🔹 Specificity

Specificity decides which rule wins when multiple rules apply.

**Hierarchy (lowest → highest):**

```
Element < Class < ID < Inline Style
```

```css
div { color: blue; }        /* 1 point */
.box { color: red; }        /* 10 points */
#main { color: green; }     /* 100 points */
```

The color will be green because `#main` has the highest specificity.

---

## 🔹 Flexbox (Responsive Layout)

Use Flexbox to arrange items responsively.

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}
```

- `flex-direction`: `row` or `column`
- `justify-content`: horizontal alignment
- `align-items`: vertical alignment
- `flex-wrap`: wraps items to new line

---

## 🔹 Typography

Control font styles, size, spacing, and alignment.

```css
body {
  font-family: 'Arial', sans-serif;
  font-size: 16px;
  line-height: 1.6;
  text-align: center;
}
```

---

## 🔹 Colors and Backgrounds

```css
h1 {
  color: #333;
  background-color: #f0f0f0;
  background-image: url('background.jpg');
  background-size: cover;
}
```

- `color`: Text color
- `background-color`: Element background
- `background-image`: Add an image
- `background-size`: Resize image (`cover`, `contain`, etc.)

---

## 🔹 Display Properties

- `block`: Starts on a new line
- `inline`: In line with text
- `none`: Hides the element
- `flex`: Enables Flexbox layout

```css
.box {
  display: block;
}

.inline-text {
  display: inline;
}

.hidden {
  display: none;
}
```

---

## 🔹 Positioning

```css
.element {
  position: relative;
  top: 10px;
  left: 20px;
}
```

| Type       | Description                                  |
|------------|----------------------------------------------|
| `static`   | Default (no special positioning)             |
| `relative` | Offset from original position                |
| `absolute` | Relative to closest positioned ancestor      |
| `fixed`    | Fixed to viewport                            |
| `sticky`   | Sticks until scrolling threshold             |

---

## 🔹 Responsive Design (Media Queries)

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }

  .item {
    width: 100%;
  }
}
```

- Adapts layout based on screen size.
- Use `min-width` and `max-width` to control breakpoints.

---

## 🔹 Pseudo-classes

```css
button:hover {
  background-color: blue;
}

input:focus {
  border: 2px solid green;
}

li:nth-child(2) {
  color: red;
}
```

- `:hover`: When mouse is over
- `:focus`: When input is selected
- `:nth-child(n)`: Targets specific children

---
