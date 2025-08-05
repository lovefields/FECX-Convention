[KO](./utiles&composables_ko.md) | [EN](./utiles&composables_en.md)

# utils & composables Naming Rules

<br>

The main point for utils and composables, which are commonly used across the application, is to distinguish their naming from what's used in pages.

<br>

## Basic Rules

<br>

-   File naming follows kebab-case.
-   Write functions using function declarations.
-   Function names use `_` as a prefix.

<br>

### utils Rules

<br>

Generally, write functions that perform calculations or return values.

Examples of modifiers:

<br>

-   get
-   convert
-   encode
-   decode

<br>

ex) `getRandomCode.ts`

```ts
export function _getRandomCode():string {
    ...
}
```

<br>

### composables Rules

<br>

Generally, write functions that execute or perform some action.

Examples of modifiers:

<br>

-   run
-   set

ex) `runLogout.ts`

```ts
export function _runLogout():void {}
```
