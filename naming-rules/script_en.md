[KO](./script_ko.md) | [EN](./script_en.md)

# Script Naming Rules

<br>

In scripts, we group many values and write them to be visually easy to identify.

<br>

## Basic Rules

<br>

Use camelCase.

<br>

### Variables

<br>

-   When using internal functions and composables, follow their existing naming conventions.
-   For state values, use `is` as a prefix.
-   Variables that assign elements or components must use `$` as a prefix.

<br>

ex)

```ts
const props = defineProps();
const isActive = ref<boolean>(false);
const $header = ref<HTMLDivElement>();
```

### Functions

<br>

For event functions triggered by user interaction, you must use `event` as a suffix.

- `loginEvent`
- `dragStartEvent`
