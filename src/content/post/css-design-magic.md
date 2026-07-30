---
title: Building a Coffee Cup with Pure CSS and Pseudo-elements
description: Create a lightweight coffee cup icon using only HTML and CSS. No SVG, no images, and no external libraries. A simple CSS illustration built with shapes and pseudo-elements.
publishDate: "2026-07-30T10:00:00Z"
tags: [css, frontend, ui, webdev, icons, design]
draft: false
pinned: true
---

> *"CSS is not drawing an image. It is describing geometry."*

While building a floating **Buy Me a Coffee** button for my website, I wanted something simple:

- no images
- no SVGs
- no icon library
- only HTML and CSS

A tiny component that lives completely inside the browser. With Code.

## Why CSS instead of SVG?

SVG icons are great.

But sometimes a small UI element does not need another file, another dependency, or another request.

And the interesting part?

The browser has no idea that we are creating a coffee cup.

It only sees:

```

shapes
+
positions
+
colors
+
pixels
    ↓
    ☕
````

The meaning comes from humans.

The browser only does the math.

---

## The HTML structure

The markup is intentionally minimal.

```html
<a class="coffee-widget">
    <span class="coffee-icon">
        <span class="cup"></span>
        
    </span>
    <span class="text">
        Buy me a coffee
    </span>
</a>
````

One element.

Everything else is created with CSS.

---

## Creating the cup body

The cup starts as a simple rectangle.

```css
.cup {
    width: 12px;
    height: 11px;

    background: #222;;

    border-radius: 2px 2px 5px 5px;

    position: relative;
}
```

At this point the browser sees:

```
████████████
████████████
████████████
████████████
```

Just a rectangle.

Nothing exciting.

Then we add rounded corners:

```
   ______
  /      \
 |        |
 |        |
  \______/
```

Ah!

A cup is starting to appear.

But the computer does not see a cup.

It only sees a rectangle with curved corners.

---

## Adding the coffee

The coffee surface is created with a pseudo-element.

```css
.cup::before {
    content: "";

    position: absolute;

    top: -3px;
    left: 1px;

    width: 10px;
    height: 3px;

    background: #222;;

    border-radius: 999px;
}
```

The browser adds another small shape:

```
      ______
     (______)
     |      |
     |      |
     |______|
```

To us:

☕ Coffee!

To the browser:

"Another rounded rectangle."

---

## Drawing the handle

The handle is created using only borders.

```css
.cup::after {
    content: "";

    position: absolute;

    right: -5px;
    top: 2px;

    width: 5px;
    height: 6px;

    border: 2px solid var(--accent);
    border-left: 0;

    border-radius: 0 6px 6px 0;
}
```

The result:

```
    ______
   |      |)
   |      |)
   |______|)
```

The funny thing about UI design is that we do not need to draw everything.

The human brain fills the missing pieces.

A few pixels are enough to communicate an idea.

---

## Adding interaction with CSS

The button starts as a small floating circle.

When the user hovers, it expands and reveals the text.

```css
.coffee-widget:hover {
    width: 180px;
    transform: translateY(-3px);
}
```

No JavaScript.

No event listeners.

Only CSS transitions.

The browser handles:

* size changes
* movement
* shadows
* smooth animation

Simple animations are often the best ones.

---

## How does the browser actually draw it?

The rendering process looks like this:

```
HTML
 |
 v
DOM Tree
 |
 v
CSS Rules
 |
 v
Layout calculations
 |
 v
Pixels
```

The browser calculates:

* dimensions
* positions
* curves
* colors
* layers

Then the GPU paints everything on the screen.

It never creates a coffee cup.

It creates tiny colored pixels that our brain interprets as one.

---

## Why this approach is useful

For a small decorative icon, this approach gives you:

* fewer dependencies
* no external assets
* easy customization
* lightweight performance

The final component contains:

* one anchor
* one wrapper
* one cup element
* two pseudo-elements

No JavaScript.

No SVG.

No images.

Just CSS.

---

## Final thoughts

Modern CSS is capable of creating much more than layouts.

With a few properties, we can build small illustrations directly in the browser.

The computer provides the geometry.

The developer provides the imagination.

```
rectangle
+
rounded corners
+
border
+
positioning
        ↓
        ☕
```