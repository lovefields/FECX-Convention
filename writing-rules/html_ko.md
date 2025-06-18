[KO](./html_ko.md) | [EN](./html_en.md)

# HTML 작성 규칙

HTML은 브라우저에 데이터를 직접적으로 표기하는 뼈대같은 존재입니다.

기본적으로 HTML5의 규칙을 따르며, 빌드 이후에 어떻게 랜더링 되는지를 고려합니다.

## 태그

기본적으로 전부 소문자를 사용합니다.

단, 컴포넌트의 경우 **PascalCase**를 사용합니다.

### 기본 태그

```html
<div></div>
```

### 단일 태그

```html
<br />
```

단일 태그의 슬래시는 XHTML 문법이지만 빌드 이후에 삭제됩니다.

일반 태그와의 구분과 단일 컴포넌트와의 통일성을 위해 사용합니다.

### 컴포넌트

```html
<MyComponent></MyComponet>
```

### 단일 컴포넌트

```html
<MyComponent />
```

## 개행 및 줄 비우기

### 자식이 있는 형제 태그 사이

-   형제 요소 중 하나라도 자식 요소가 있다면, 형제 요소들 사이에 한 줄을 비워 구분합니다.
-   마지막 형제는 제외합니다.

```html
<div>
    <div>
        <p>내용</p>
    </div>

    <div></div>

    <div></div>
</div>
```

### `<br />` 태그 사용시

`<br />`태그를 사용하는 경우 다음처럼 줄을 명확히 구분합니다.

```html
<p>
    이 문장은<br />
    두 줄로
</p>
```

### 속성이 너무 길거나 많은 경우

속성이 많거나 길어져 가독성이 떨어질 경우, 각 속성을 한 줄씩 작성합니다.

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

## 속성 작성 순서 (Vue 포함)

> 일관된 순서를 통해 가독성과 코드 관리를 높입니다.

| 순서 |   항목    | 설명                                               |
| :--: | :-------: | :------------------------------------------------- |
|  1   |   `v-*`   | Vue 에서 사용하는 시스템 지시자                    |
|  2   |  `class`  | 정적인 클래스명                                    |
|  3   | `:class`  | 동적인 Vue 클래스 바인딩                           |
|  4   | 기본 속성 | type, disabled, id 등 HTML 태그가 가지는 고유 속성 |
|  5   |   `ref`   | DOM 엘리먼트 접근용 Vue ref 변수                   |
|  6   |   `@*`    | Vue 이벤트 바인딩 (@click 등)                      |

예시)

```html
<div v-if="show" class="btn-item" :class="{ '--active': isActive === true }" type="button" ref="$button" @click="onClickEvent">버튼</div>
```
