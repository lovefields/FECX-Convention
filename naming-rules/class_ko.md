[KO](./class_ko.md) | [EN](./class_en.md)

# class 네이밍 규칙

레이아웃 시스템과 독립적인 컴포넌트 시스템으로 나뉩니다. 두 시스템은 각자의 역할을 가지며, 조합하여 일관되고 예측 가능한 UI를 구성하도록 합니다.

<br>

## 기본 규칙

<br>

class를 명할때는 케밥케이스를 사용합니다.

<br>

## 클래스 종류 및 접두사

<br>

| 구분     | 접두사                                                      | 설명                                                                                        |
| :------- | :---------------------------------------------------------- | :------------------------------------------------------------------------------------------ |
| 컨텍스트 | `ctx-*`                                                     | 도메인/화면의 고유 맥락을 명시합니다. (**`page-*` 또는 `com-*` 클래스와만 함께 사용 가능**) |
| 구조     | `page-*`,`area-*`,`box-*`, `group-*`,`row`,`col`,`layout-*` | 페이지, 영역, 그룹 등 와이드 프레임 수준의 구조를 정의합니다.                               |
| 컴포넌트 | `com-*`                                                     | 재사용이 가능한 독립적 UI 단위의 기본 클레스 입니다. (예: `com-button`)                     |
| JS Hook  | `js-*`                                                      | JavaScript가 DOM에 접근하기 위한 전용 클래스 이며, **스타일링에 사용하지 않습니다.**        |
| 옵션     | `--*`                                                       | 컴포넌트 또는 요소의 옵션을 표현합니다. (예: `--active`)                                    |

<br>

### 컨텍스트

<br>

컨텍스트 클래스는 도메인 개념이 강합니다. 기본적으로 `page-*` 와 `com-*` 클레스만 같이 사용할 수 있습니다.

<br>

ex)

```scss
.ctx-student.page-profile {
}

.ctx-teacher.page-profile {
}
```

<br>

### 구조

<br>

구조 클래스는 HTML구조를 명확하게 하기 위해서 사용합니다.

다음과 같은 위계를 가지고 있습니다.

`page` > `area` > `box` > `group` > `row`, `col`

`layout` 구조 클레스는 독자적으로 사용이 가능하며, 어플리케이션 전반에 걸쳐서 사용되는 독자적인 구조를 가집니다.

<br>

### 컴포넌트

<br>

컴포넌트 구조 클래스는 컴포넌트 최상위에 선언되어야 합니다.

<br>

### JS Hook

<br>

JS Hook 클래스는 JavaScript에서 DOM에 접근하기 위한 클래스입니다.

<p style="color:red;font-weight:bold">CSS 선택자로 사용되어선 안됩니다.</p>

<br>

### 옵션

<br>

옵션 클래스는 주로 상태, 혹은 추가적인 사항이 있을때 사용합니다.

<br>

ex)

```html
<p class="text --red"></p>

<button class="btn-close --active"></button>
```

### 예시

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
