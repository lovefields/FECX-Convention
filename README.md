[KO](./README_ko.md) | [EN](./README.md)

# FECX(Front-end Contextual Experience) Convention

CROCSS(Component-Role-Option-Condition Style System) is a structure-first, clear and intuitive CSS naming methodology designed for scalable UI development.

## 📐 Naming Convention

```
[com-]role[-option] [--state] [ctx-*]
```

| Element | Description                                                  |
| ------- | ------------------------------------------------------------ |
| `com-`  | Independent components (e.g., modal, selector, pagination)   |
| Role    | Required structural name (e.g., `modal`, `field`, `btn`)     |
| Option  | Functional sub-units (e.g., `-icon`, `-clear`)               |
| State   | Prefixed with `--`, separated by a space (e.g., `--active`)  |
| Context | Prefixed with `ctx-*` to indicate usage context (`ctx-auth`) |

## 📏 Structural Prefix Rules

| Prefix    | Meaning                                    | Example                                             |
| --------- | ------------------------------------------ | --------------------------------------------------- |
| `page-`   | Page-level structure                       | `page-login`                                        |
| `area-`   | Visual sections                            | `area-header`                                       |
| `box-`    | Functional blocks                          | `box-form`                                          |
| `group-`  | Group of elements with a shared purpose    | `group-btn`                                         |
| `layout-` | **Used only for global layout components** | `layout-main` (❌ do not use for general structure) |

Structural Hierarchy

-   `page` > `area` > `box` > `group`
-   `layout` : standalone and only for global layout

## 🧭 State Class Rules

-   Prefixed with `--` and separated by space from other classes
-   Cannot be used as a standalone selector

```html
<button class="btn-item --active">Click me</button>
```

## 🌐 Context Class Rules

-   `ctx-*` must always be used **with** another structure class
-   **Cannot** be used alone

```scss
/* ✅ Allowed */
.ctx-auth.com-modal { ... }
.ctx-auth.com-modal .area-container { ... }

/* ❌ Not allowed */
.ctx-class-room { ... }
```

## 🧱 Selector Depth Rule

-   Maximum allowed depth is **5**

```scss
/* ✅ */
.ctx-class-room.com-modal .area-container .group-btn .btn-item {
}

/* ❌ */
.ctx-class-room.com-modal .area-container .group-btn .btn-item .icon {
}
```
