# 👁 eyes.css

> *A pair of eyes that follow your cursor — built entirely in CSS.*

No JavaScript. No canvas. No libraries. Just the cascade doing something it probably shouldn't.

---

## Demo

Move your mouse around the box. The eyes follow.

Hover the dead centre — they go red.

---

## How it works

A 5×5 invisible grid of `.hitbox` divs covers the container. Each cell corresponds to a specific `rotate() translate()` transform on the pupils. When your cursor enters a zone, the CSS sibling combinator (`~`) propagates the style change to the eyes.

```
┌─────────────────────────┐
│  a1  a2  a3  a4  a5     │
│  b1  b2  b3  b4  b5     │
│  c1  c2 [c3] c4  c5     │  ← hover #c-3 for a surprise
│  d1  d2  d3  d4  d5     │
│  e1  e2  e3  e4  e5     │
└─────────────────────────┘
```

It's a lookup table disguised as CSS — no logic, just rules. The browser does the math.

The eyelids blink autonomously on a `@keyframes` loop. On hover they furrow. No state, no events, no script.

---

## Usage

```html
<link rel="stylesheet" href="style.css">

<div class="hit-area">
  <!-- 25 hitbox divs (a-1 through e-5) -->
  <div class="eye"><div class="pupil"></div></div>
  <div class="eye"><div class="pupil"></div></div>
  <div class="eyelid"></div>
  <div class="eyelid"></div>
</div>
```

Drop it into any HTML page. No build step. No dependencies.

---

## At a glance

| | |
|---|---|
| **Technique** | CSS `~` sibling combinator + `transform` |
| **Grid** | 5 × 5 hitboxes |
| **JavaScript** | 0 bytes |
| **Dependencies** | none |
| **Easter egg** | hover `#c-3` |

---

## Why

Because someone had to find out if it was possible.

---
