[KO](./setting_ko.md) | [EN](./setting_en.md)

# 설정 방법

Use Extension List

-   ESLint
-   Prettier - Code formatter
-   Stylelint

## ESLint

Create `.eslintrc.json` file to Root Directory.

```json
{
    "extends": ["plugin:vue/vue3-essential", "eslint:recommended"],
    "rules": {
        "eqeqeq": ["error", "always"],
        "curly": "error"
    }
}
```

## Prettier - Code formatter

Create `.prettierrc.json` file to Root Directory.

```json
{
    "printWidth": 500,
    "tabWidth": 4,
    "useTabs": false,
    "semi": true,
    "singleQuote": false,
    "quoteProps": "as-needed",
    "trailingComma": "es5",
    "vueIndentScriptAndStyle": false,
    "arrowParens": "avoid",
    "htmlWhitespaceSensitivity": "ignore"
}
```

## Stylelint

Install Node Module

-   `postcss-html`
-   `stylelint-order`

Create `.stylelintrc.json` file to Root Directory.

```json
{
    "plugins": ["stylelint-order"],
    "rules": {
        "selector-max-id": 1,
        "selector-max-compound-selectors": 6,
        "selector-class-pattern": [
            "^.*$",
            {
                "message": "-"
            }
        ],
        "order/properties-order": [
            "display",
            "content",
            "grid",
            "grid-area",
            "grid-template",
            "grid-template-areas",
            "grid-template-rows",
            "grid-template-columns",
            "grid-row",
            "grid-row-start",
            "grid-row-end",
            "grid-column",
            "grid-column-start",
            "grid-column-end",
            "grid-auto-rows",
            "grid-auto-columns",
            "grid-auto-flow",
            "grid-gap",
            "gap",
            "flex",
            "flex-flow",
            "flex-grow",
            "flex-shrink",
            "flex-basis",
            "flex-direction",
            "flex-wrap",
            "justify-content",
            "align-items",
            "align-content",
            "align-self",
            "position",
            "top",
            "left",
            "right",
            "bottom",
            "width",
            "min-width",
            "max-width",
            "height",
            "min-height",
            "max-height",
            "margin",
            "margin-top",
            "margin-right",
            "margin-bottom",
            "margin-left",
            "padding",
            "padding-top",
            "padding-right",
            "padding-bottom",
            "padding-left",
            "background",
            "background-color",
            "background-image",
            "background-repeat",
            "background-attachment",
            "background-position",
            "background-position-x",
            "background-position-y",
            "background-clip",
            "background-origin",
            "background-size",
            "color",
            "border",
            "border-width",
            "border-style",
            "border-color",
            "border-top",
            "border-top-color",
            "border-top-width",
            "border-top-style",
            "border-right",
            "border-right-color",
            "border-right-width",
            "border-right-style",
            "border-bottom",
            "border-bottom-color",
            "border-bottom-width",
            "border-bottom-style",
            "border-left",
            "border-left-color",
            "border-left-width",
            "border-left-style",
            "border-radius",
            "font",
            "font-family",
            "font-size",
            "font-weight",
            "font-style",
            "text-align",
            "text-decoration",
            "text-transform",
            "text-shadow",
            "line-height",
            "letter-spacing",
            "line-break",
            "word-break",
            "word-wrap",
            "white-space",
            "writing-mode",
            "vertical-align",
            "cursor",
            "opacity",
            "visibility",
            "user-select",
            "outline",
            "transform",
            "transition",
            "animation",
            "animation-name",
            "animation-duration",
            "animation-timing-function",
            "animation-delay",
            "animation-iteration-count",
            "animation-direction",
            "animation-fill-mode",
            "animation-play-state",
            "box-sizing",
            "resize",
            "overflow",
            "overflow-x",
            "overflow-y",
            "z-index"
        ]
    },
    "overrides": [
        {
            "files": ["**/*.vue"],
            "customSyntax": "postcss-html"
        }
    ]
}
```
