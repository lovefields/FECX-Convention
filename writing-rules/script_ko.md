[KO](./script_ko.md) | [EN](./script_en.md)

# Script 작성 규칙

기본적으로 함수형 프로그래밍을 지향합니다. 코드의 가독성과 일관성을 최우선으로 하며, 모든 규칙을 코드를 읽는 사람이 의도를 명확하게 파악할 수 있도록 돕는 것을 목표로 합니다.

<br>

## 작성 순서

파일 내 혹은 `.vue` 파일 내 `<Script>` 부분을 포함해서 코드의 순서를 통일합니다.

코드는 언제나 같은 위치에서 찾을 수 있도록 하며, 아래의 순서를 반드시 따릅니다.

<br>

1. 모듈 및 파일 `import`
2. 변수 및 상수 선언
    1. Nuxt 내장 Composables (`useRoute` 등)
    2. 모듈 / 플러그인 Composables (`useDayjs` 등)
    3. 상태 (State) (`ref`, `useState` 등)
    4. DOM 엘리먼트 잠조 (Element Refs)
    5. 일반 상수
    6. 일반 변수
3. 함수 선언
4. Vue 및 Nuxt 생명주기 및 페이지 관련 Composables (`onMounted`, `useHead` 등)

<br>

ex)

```ts
// 1. 모듈 및 파일
import { ref } from "vue";
import type { VNode } from "vue";

// 2. 변수 및 상수 선언
const route = useRoute();
const dayjs = useDayjs();
const userName = ref<string>("Mr.User");
const $mainContianer = ref<HTMLDivElement>();
const maxLength = 100;
let timerId = null;

// 3. 함수 선언
function updateUser(): void {
    // ...
}

// 4. Vue 및 Nuxt 생명주기 및 페이지 관련
onMounted(() => {
    // ...
});

useHead({
    title: "page title",
});
```

## 타입 선언

타입 선언은 가능한 외부 파일로 분리합니다. (`type.d.ts`)

<br>

1. `type`은 `interface`보다 위에 있어야 합니다.

<br>

ex)

```ts
type UserType = "guast" | "member";

interface UserData {
    type: UserType;
}
```

## 함수

<br>

-   함수 선언식을 사용합니다.
-   반환 타입을 반드시 명시해야합니다.
-   함수 내에서만 사용하는 보조 함수는 주된 로직 실행 이후에 작성합니다. (`return` 이후)

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

## if 문

<br>

-   항상 엄격한 비교 연산자(`===`,`!==`)를 사용합니다.
-   `boolean` 타입 비교시 `=== true` 또는 `=== false`로 명시합니다.
-   `if`문은 한줄이더라도 반드시 중괄호(`{}`)를 사용합니다.

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

## 주석

주석은 누구든지 이해할 수 있는 수준으로 작성하도록 합니다.

### 변수

변수의 경우 변수 선언문의 우측에 작성하도록 합니다.

<br>

ex)

```ts
const userName = ref<string>(""); // 유저 이름
let counter:NodeJS.Timer; // 시간 제한 카운트 변수
```

### 함수

함수의 경우 함수 선언문의 상단에 작성하도록 합니다.

<br>

ex)

```ts
// 미디어 파일 삭제 이벤트
function medaiFileDeleteEvent():void {
    ...
}
```
