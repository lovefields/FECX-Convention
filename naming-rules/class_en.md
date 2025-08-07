[KO](./class_ko.md) | [EN](./class_en.md)

# Class Naming Rules

Our system is divided into a layout system and an independent component system. These two systems each have their own roles and are combined to form a consistent and predictable UI.

<br>

## Basic Rules

<br>

When naming classes, kebab-case is used.

<br>

## Class Types and Prefixes

<br>

| Category     | Prefix                                                      | Description                                                                                        |
| :------- | :---------------------------------------------------------- | :------------------------------------------------------------------------------------------ |
| Context | `ctx-*`                                                     | Specifies the unique context of a domain/screen. (**Only usable with `page-*` or `com-*` classes**) |
| Structure     | `page-*`,`area-*`,`box-*`, `group-*`,`row`,`col`,`layout-*` | Defines wide-frame level structures like pages, areas, or groups.                               |
| Component | `com-*`                                                     | This is the base class for reusable, independent UI units. (e.g., `com-button`)                     |
| JS Hook  | `js-*`                                                      | This is a dedicated class for JavaScript to access the DOM, and **it is not used for styling**.        |
| 옵션     | `--*`                                                       | Expresses options for a component or element. (e.g., `--active`)                                    |

<br>

### Context

<br>

Context classes have a strong domain concept. By default, they can only be used with `page-*` and `com-*` classes.

<br>

ex)

```scss
.ctx-student.page-profile {
}

.ctx-teacher.page-profile {
}
```

<br>

### Structure

<br>

Structure classes are used to clarify the HTML structure.

They have the following hierarchy:

`page` > `area` > `box` > `group` > `row`, `col`

`layout` structure classes can be used independently and have a self-contained structure used throughout the application.

<br>

### Component

<br>

Component structure classes should be declared at the top level of the component.

<br>

### JS Hook

<br>

JS Hook classes are for JavaScript to access the DOM.

<p style="color:red;font-weight:bold">They should not be used as CSS selectors.</p>

<br>

### Option

<br>

Option classes are primarily used to indicate a state or additional features.

<br>

ex)

```html
<p class="text --red"></p>

<button class="btn-close --active"></button>
```

### Example

```html
<header class="com-header">
    <div class="area-logo">
        <a href="" class="logo">
            <svg class="icon"></svg>
        </a>
    </div>

    <nav class="list-menu">
        <a href="" class="link"></a>
        <a href="" class="link"></a>
        <a href="" class="link"></a>
    </nav>
</header>

<main class="page-main">
    <section class="area-section01">
        <h2 class="title"></h2>
        <p class="caption"></p>
    </section>

    <section class="area-section02">
        <div class="box-text">
            <h2 class="title"></h2>
            <p class="caption"></p>
        </div>

        <div class="list-card">
            <div class="card">
                <div class="group-image">
                    <img class="img" src="" alt="" />
                </div>

                <div class="group-text">
                    <p class="name"></p>
                    <p class="description"></p>
                </div>
            </div>

            <div class="card">
                <div class="group-image">
                    <img class="img" src="" alt="" />
                </div>

                <div class="group-text">
                    <p class="name"></p>
                    <p class="description"></p>
                </div>
            </div>
        </div>
    </section>
</main>

<footer class="com-footer">
    <div class="area-top">
        <nav class="list-menu">
            <a href="" class="link"></a>
            <a href="" class="link"></a>
            <a href="" class="link"></a>
        </nav>

        <div class="box-infomation">
            <p class="name"></p>
            <p class="address"></p>
        </div>
    </div>

    <div class="area-bottom">
        <p class="copy"></p>
    </div>
</footer>
```
