---
author: Aditya Tomar
pubDatetime: 2022-09-26T12:13:24Z
modDatetime: 2024-01-04T09:09:06Z
title: Predefined color schemes
slug: predefined-color-schemes
featured: false
draft: false
tags:
  - color-schemes
description:
  Some of the well-crafted, predefined color schemes for DivineInsights blog
  theme.
---

I've crafted some predefined color schemes for this DivineInsights blog theme. You can replace these color schemes with the original ones.

If you don't know how you can configure color schemes, check [this blog post](https://divineinsights.vercel.app/posts/customizing-DivineInsights-theme-color-schemes/).

## Table of contents

## Light color schemes

Light color scheme has to be defined using the css selector `:root` and `html[data-theme="light"]`.

### Lobster

```css
:root,
html[data-theme="light"] {
  --color-fill: 246, 238, 225;
  --color-text-base: 1, 44, 86;
  --color-accent: 225, 74, 57;
  --color-card: 217, 209, 195;
  --color-card-muted: 239, 216, 176;
  --color-border: 220, 152, 145;
}
```

### Leaf Blue

```css
:root,
html[data-theme="light"] {
  --color-fill: 242, 245, 236;
  --color-text-base: 53, 53, 56;
  --color-accent: 17, 88, 209;
  --color-card: 206, 213, 180;
  --color-card-muted: 187, 199, 137;
  --color-border: 124, 173, 255;
}
```

### Pinky light

```css
:root,
html[data-theme="light"] {
  --color-fill: 250, 252, 252;
  --color-text-base: 34, 46, 54;
  --color-accent: 211, 0, 106;
  --color-card: 234, 206, 219;
  --color-card-muted: 241, 186, 212;
  --color-border: 227, 169, 198;
}
```

## Dark color schemes

Dark color scheme has to be defined as `html[data-theme="dark"]`.

### DivineInsights 1 original Dark Theme

```css
html[data-theme="dark"] {
  --color-fill: 47, 55, 65;
  --color-text-base: 230, 230, 230;
  --color-accent: 26, 217, 217;
  --color-card: 63, 75, 90;
  --color-card-muted: 89, 107, 129;
  --color-border: 59, 70, 85;
}
```

### Deep Oyster

```css
html[data-theme="dark"] {
  --color-fill: 33, 35, 61;
  --color-text-base: 244, 247, 245;
  --color-accent: 255, 82, 86;
  --color-card: 57, 60, 102;
  --color-card-muted: 74, 78, 134;
  --color-border: 177, 47, 50;
}
```

### Pikky dark

```css
html[data-theme="dark"] {
  --color-fill: 53, 54, 64;
  --color-text-base: 233, 237, 241;
  --color-accent: 255, 120, 200;
  --color-card: 75, 76, 89;
  --color-card-muted: 113, 85, 102;
  --color-border: 134, 67, 107;
}
```

### Astro dark (High Contrast)

```css
html[data-theme="dark"] {
  --color-fill: 16, 23, 42; /* higher contrast bgColor */
  --color-fill: 33, 39, 55;
  --color-text-base: 234, 237, 243;
  --color-accent: 255, 107, 1;
  --color-card: 27, 39, 70;
  --color-card-muted: 138, 51, 2;
  --color-border: 171, 75, 8;
}
```

### Astro dark (New default dark theme in DivineInsights 2)

```css
html[data-theme="dark"] {
  --color-fill: 33, 39, 55; /* lower contrast bgColor */
  --color-text-base: 234, 237, 243;
  --color-accent: 255, 107, 1;
  --color-card: 52, 63, 96;
  --color-card-muted: 138, 51, 2;
  --color-border: 171, 75, 8;
}
```

### Astro Deep Purple (New dark theme in DivineInsights 3)

```css
html[data-theme="dark"] {
  --color-fill: 33, 39, 55;
  --color-text-base: 234, 237, 243;
  --color-accent: 235, 63, 211;
  --color-card: 52, 63, 96;
  --color-card-muted: 125, 79, 124;
  --color-border: 100, 36, 81;
}
```

### DivineInsights v4 Special (New dark theme in DivineInsights 4)

```css
html[data-theme="dark"] {
  --color-fill: 0, 1, 35;
  --color-accent: 97, 123, 255;
  --color-text-base: 234, 237, 243;
  --color-card: 33, 34, 83;
  --color-card-muted: 12, 14, 79;
  --color-border: 48, 63, 138;
}
```
