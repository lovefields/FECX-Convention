[KO](./html_ko.md) | [EN](./html_en.md)

# HTML Writing Rules

Basically, follow HTML5 rules, considering how it will be rendered after building.

<br>

## Tags

All tags generally use lowercase letters. \
However, for components, PascalCase is used.

<br>

### Basic Tag

```html
<div></div>
```

<br>

### Self-Closing Tag

The slash in a self-closing tag is XHTML syntax but will be removed after building.\
It is used to distinguish it from regular tags and maintain consistency with single components.

```html
<br />
```

<br>

### Component

```html
<MyComponent></MyComponent>
```

<br>

### Self-Closing Component

```html
<MyComponent />
```

<br>

## Line Breaks and Empty Lines

<br>

### Between Sibling Tags with Children

-   If at least one of the sibling elements has a child element, leave one empty line between the sibling elements to separate them.
-   Exclude the last sibling.

<br>

```html
<div>
    <div>
        <p>Content</p>
    </div>

    <div></div>

    <div></div>
</div>
```

<br>

### When Using `<br />` Tag

When using the `<br />` tag, clearly separate lines as follows:

<br>

```html
<p>
    This sentence is<br />
    two lines
</p>
```

<br>

### When Attributes Are Too Long or Numerous

If attributes are numerous or too long, reducing readability, write each attribute on a separate line.

<br>

```html
<p
    v-if="hasText === true"
    class="text-notice"
    data-value1="example1"
    data-value2="example2"
    data-value3="example3"
    data-value4="example4"
    data-value5="example5"
    data-value6="example6"
    data-value7="example7"
    data-value8="example8"
    data-value9="example9"
    data-value10="example10"
    data-value11="example11"
    data-value12="example12"
    data-value13="example13"
    data-value14="example14"
    data-value15="example15"
></p>
```

<br>

## Attribute Order (Including Vue)

> Consistent order enhances readability and code maintainability.

<br>

| Order |       Item       | Description                                              |
| :---: | :--------------: | :------------------------------------------------------- |
|   1   |      `v-*`       | System directives used in Vue                            |
|   2   |     `class`      | Static class names                                       |
|   3   |     `:class`     | Dynamic Vue class binding                                |
|   4   | Basic Attributes | type, disabled, id, etc., unique attributes of HTML tags |
|   5   |      `ref`       | Vue ref variable for accessing DOM elements              |
|   6   |       `@*`       | Vue event binding (@click, etc.)                         |

<br>

Example)

```html
<div v-if="show" class="btn-item" :class="{ '--active': isActive === true }" type="button" ref="$button" @click="onClickEvent">Button</div>
```
