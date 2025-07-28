[KO](./css_ko.md) | [EN](./css_en.md)

# css 작성 규칙

기본적으로 CSS3의 규칙을 따르며, 빌드 이후에 어떻게 랜더링 되는지를 고려합니다.

<br>

## 기본

CSS작성시에는 전부 소문자만을 사용합니다. 이는 파일 명도 예외가 아니며, 외부 파일이나 외부 모듈의 경우만 예외로 둡니다.

<br>

## 선택자

| 선택자 | 사용가능 여부 | 예외 여부 |                  설명                  |
| :----: | :-----------: | :-------: | :------------------------------------: |
| class  |       O       |     X     |              기본 선택자               |
|   id   |       X       |     O     |   root의 경우 id 선택자를 허용합니다   |
|  tag   |       X       |     O     |     reset css의 경우만 허용합니다      |
| global |       X       |     O     | 직계 자식을 선택하는 경우만 허용됩니다 |

<br>

## 뎁스

-   선택자를 사용할때 최대 6뎁스의 제한이 존재합니다.
-   1뎁스에는 주로 `page`, `com` 등이 사용 가능합니다.
-   2뎁스에는 주로 `area`, `group`, `box` 등이 사용됩니다.

<br>

```scss
// ✅ 가능
.ctx-user.com-modal .area-content .group-list .box-item .btn-delete .icon {
}

// ❌ 불가능
.ctx-user.com-modal .area-content .group-list .box-item .btn-delete .icon .path {
}
```

<br>

## 프로퍼티

FECX에서는 가독성과 유지보수를 높이기 위해 CSS속성을 다음과 같은순으로 작성합니다.

<br>

```
// include
@include myMixin;

// 레이아웃 관련
display
content
grid-*
column-*
flex-*
justify-*
align-*
gap
position
top
left
right
bottom
width
height
padding
margin
// 색상 관련
background
color
border
box-sizing
// 텍스트 관련
font-*
text-*
line-height
letter-spacing
line-break
break-*
word-*
white-space
writing-mode
// 효과 관련
vertical-align
cursor
opacity
visibility
user-select
outline
transform
transition
animation-*
// 기타
box-*
resize
overflow
z-index
```

<br>

## 작성 순서

css, scss 그리고 vue 파일 내의 `<style>` 에서도 동일하게 적용됩니다.

<br>

| 순서 | 설명                         |
| :--- | :--------------------------- |
| 1    | `@use`, `@forward` 등 호출문 |
| 2    | `$` 변수 선언                |
| 3    | `@mixin` 정의                |
| 4    | 선택자 기반 스타일 정의      |

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

초기화는 다음 Reset CSS 사용을 권장합니다.

[🔗 https://github.com/lovefields/reset-css](https://github.com/lovefields/reset-css)
