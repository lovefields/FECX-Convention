[KO](./css_ko.md) | [EN](./css_en.md)

# CSS Writing Rules

Basically, follow CSS3 rules, considering how it will be rendered after building.

<br>

## General

When writing CSS, only lowercase letters are used. This rule also applies to file names, with exceptions only for external files or external modules.

<br>

## Selectors

| Selector | Usable | Exception |                  Description                  |
| :----: | :-----------: | :-------: | :------------------------------------: |
| class  |       O       |     X     |              Basic selector               |
|   id   |       X       |     O     |   id selectors are allowed for root elements   |
|  tag   |       X       |     O     |     Only allowed for reset CSS      |
| global |       X       |     O     | Only allowed when selecting direct children |

<br>

## Depth

-   When using selectors, there is a maximum limit of 6 depths.
-   1st depth mainly allows `page`, `com`, etc.
-   2nd depth mainly uses `area`, `group`, `box`, etc.

<br>

```scss
// ✅ Possible
.ctx-user.com-modal .area-content .group-list .box-item .btn-delete .icon {
}

// ❌ Not Possible
.ctx-user.com-modal .area-content .group-list .box-item .btn-delete .icon .path {
}
```

<br>

## Properties

At FECX, to enhance readability and maintainability, CSS properties are written in the following order:

<br>

```
// include
@include myMixin;

// Layout related
display
content
position
top
left
right
bottom
box-*
grid-*
column-*
flex-*
justify-*
align-*
gap
width
height
margin
padding
// Color related
background
color
border
box-sizing
// Text related
font-*
text-*
line-height
letter-spacing
line-break
break-*
word-*
white-space
writing-mode
// Effect related
vertical-align
cursor
opacity
visibility
user-select
outline
transform
transition
animation-*
// Others
resize
overflow
z-index
```

<br>

## Writing Order

This applies uniformly to CSS, SCSS, and `<style>` blocks within Vue files.

<br>

| Order | Description                         |
| :--- | :--------------------------- |
| 1    | `@use`, `@forward` and other call statements |
| 2    | `$` variable declarations                |
| 3    | `@mixin` definitions                |
| 4    | Selector-based style definitions      |

<br>

```scss
@use "./reset";

$myValue: 32px;

@mixin myMixin {
    width: $myValue;
}

.selector {
}
```

<br>

## Reset CSS

For initialization, we recommend using the following Reset CSS.

[🔗 https://github.com/lovefields/reset-css](https://github.com/lovefields/reset-css)
