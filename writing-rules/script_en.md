[KO](./script_ko.md) | [EN](./script_en.md)

# Script Writing Rules

We generally aim for functional programming, prioritizing code readability and consistency. The goal of all rules is to help readers clearly understand the code's intent.

<br>

## Writing Order

Standardize the order of code within files, including the `<Script>` section in `.vue` files.

Code should always be found in the same location and must follow the order below:

<br>

1. Module and file `import`s
2. Variable and constant declarations
    1. Nuxt built-in Composables (`useRoute`, etc.)
    2. Module / Plugin Composables (`useDayjs`, etc.)
    3. State (`ref`, `useState`, etc.)
    4. DOM Element References (Element Refs)
    5. General constants
    6. General variables
3. Function declarations
4. Vue and Nuxt Lifecycle and Page-related Composables (`onMounted`, `useHead`, etc.)

<br>

ex)

```ts
// 1. Modules and Files
import { ref } from "vue";
import type { VNode } from "vue";

// 2. Variable and Constant Declarations
const route = useRoute();
const dayjs = useDayjs();
const userName = ref<string>("Mr.User");
const $mainContianer = ref<HTMLDivElement>();
const maxLength = 100;
let timerId = null;

// 3. Function Declarations
function updateUser(): void {
    // ...
}

// 4. Vue and Nuxt Lifecycle and Page-related
onMounted(() => {
    // ...
});

useHead({
    title: "page title",
});
```

## Type Declarations

Separate the type declaration into possible external files (`type.d.ts`).

<br>

1. `type` must be placed above `interface`.

<br>

ex)

```ts
type UserType = "guast" | "member";

interface UserData {
    type: UserType;
}
```

## Functions

<br>

-   Use function declarations.
-   The return type must always be explicitly stated.
-   Auxiliary functions used only within a main function should be written after the main logic's execution (`return` statement).

<br>

ex)

```ts
function myFunction(): void {
    // ...
}

function myFunction01(): string {
    return "void";

    function mySubFunction01(): void {
        // ...
    }
}
```

## If Statements

<br>

-   Always use strict comparison operators (`===`, `!==`).
-   When comparing `boolean` types, explicitly state `=== true` or `=== false`.
-   Always use curly braces (`{}`) for `if` statements, even for a single line.

<br>

ex)

```ts
if (myValue === "value") {
    // ...
}

if (myBoolean === true) {
    // ...
}
```

## Comments

Comments should be written at a level that anyone can understand.

### Variables

For variables, write the comment to the right of the variable declaration.

<br>

ex)

```ts
const userName = ref<string>(""); // User name
let counter:NodeJS.Timer; // Time limit counter variable
```

### Functions

For functions, write the comment above the function declaration.

<br>

ex)

```ts
// Media file delete event
function medaiFileDeleteEvent():void {
    ...
}
```
