# Frontend Mentor — Testimonials Grid Section

A solution to the [Testimonials Grid Section challenge](https://www.frontendmentor.io/challenges/testimonials-grid-section-Nnw6J7Un7) on Frontend Mentor.

---

## Table of Contents

- [Overview](#overview)
  - [The Challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My Process](#my-process)
  - [Built With](#built-with)
  - [What I Learned](#what-i-learned)
  - [Continued Development](#continued-development)
- [Author](#author)

---

## Overview

### The Challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size (mobile-first approach)

### Screenshot

![Project Screenshot](/images/design.png)

### Links

- **Solution URL:** [Git Repository](https://github.com/Ismaellerakotoson/Testimonials-grid-section.git)
- **Live Site URL:** [Add your live site URL here](#)

---

## My Process

### Built With

- Semantic HTML5 markup
- SCSS (variables, nesting, media queries)
- CSS Grid for the desktop layout
- CSS Flexbox for component-level alignment (avatar row)
- Mobile-first responsive design
- [Barlow Semi Condensed](https://fonts.google.com/specimen/Barlow+Semi+Condensed) — Google Fonts

---

### What I Learned

This project was focused on understanding how **CSS Grid really works** in practice. Key takeaways:

**1. Grid placement with `grid-column` and `grid-row`**

The desktop layout required cards to span across multiple columns or rows. I used explicit line-based placement to position each card exactly where it needed to go:

```scss
.first  { grid-column: 1 / 3; }         // spans 2 columns
.forth  { grid-column: 2 / 4; }         // spans 2 columns, starting at col 2
.fifth  { grid-column: 4 / 5; grid-row: 1 / 3; } // spans 2 rows
```

This clicked for me: the numbers in `grid-column` refer to **grid lines**, not track indexes. So `1 / 3` means "from line 1 to line 3", which covers 2 column tracks.

**2. Grid auto-placement fills in the gaps**

Cards without explicit placement (`.second`, `.third`) are placed automatically by the browser's grid algorithm. Understanding when to be explicit vs. letting auto-placement do the work was a real insight.

**3. `grid-row` for vertical spanning**

The fifth card needed to stretch across two rows. Using `grid-row: 1 / 3` alongside `grid-column: 4 / 5` let me achieve that without any extra wrappers or hacks.

**4. SCSS custom properties for a consistent design system**

Defining all colors as CSS custom properties in `:root` made theming each card clean and maintainable:

```scss
:root {
  --color-Purple-500: hsl(263, 55%, 52%);
  --color-Dark-blue:  hsl(219, 29%, 14%);
  --color-White:      hsl(0, 0%, 100%);
  // ...
}
```

---

### Continued Development

In future projects, I want to keep improving on:

- **CSS Grid** — specifically implicit grids, `minmax()`, and `auto-fill` / `auto-fit` for more dynamic layouts
- **CSS `subgrid`** — for aligning content *inside* grid items across tracks
- **Accessibility** — making sure card components are properly structured for screen readers
- **CSS animations** — adding subtle hover states to cards

---

## Author

- Frontend Mentor - [@Ismaellerakotoson](https://www.frontendmentor.io/profile/Ismaellerakotoson)