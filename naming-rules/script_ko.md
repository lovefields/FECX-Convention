[KO](./script_ko.md) | [EN](./script_en.md)

# Script 네이밍 규칙

<br>

Script에서 사용하는 많은 값을 그룹화 하고 가시적으로 확인하기 쉽게 작성하도록 합니다.

<br>

## 기본 규칙

<br>

카멜 케이스를 사용합니다.

<br>

### 변수

<br>

-   내부 함수 및 내부 컴포저블을 사용할 때는 해당 함수나 컴포저블의 명명을 따라갑니다.
-   상태값은 접두사로 `is`를 사용합니다.
-   엘리먼트, 컴포넌트를 할당하는 변수는 반드시 접두사로 `$`를 사용합니다.

<br>

ex)

```ts
const props = defineProps();
const isActive = ref<boolean>(false);
const $header = ref<HTMLDivElement>();
```

### 함수

<br>

유저 인터렉션에 의해 실행되는 이벤트 함수의 경우 접미사로 `event` 를 사용해야 합니다.

- `loginEvent`
- `dragStartEvent`

### 인자
