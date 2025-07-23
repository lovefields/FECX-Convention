[KO](./utiles&composables_ko.md) | [EN](./utiles&composables_en.md)

# utils & composables 네이밍 규칙

<br>

어플리케이션에서 공통으로 사용하게되는 utils와 composables은 page에서 사용하는 네이밍과 구분되도록 하는 것이 관점입니다.

<br>

## 기본 규칙

<br>

-   파일 명명은 케밥케이스를 따릅니다.
-   함수 선언식으로 작성합니다.
-   함수 명은 접두사로 `_`를 사용합니다.

<br>

### utils 규칙

<br>

기본적으로 연산을 하거나 값을 반환하는 함수를 작성합니다.

수식어 예시

<br>

-   get
-   convert
-   encode
-   decode

<br>

ex) `getRandomCode.ts`

```ts
export _getRandomCode():string {
    ...
}
```

<br>

### composables 규칙

<br>

기본적으로 무언가를 실행하거나 동작하는 경우의 함수를 작성합니다.

수식어 예시

<br>

-   run
-   set

ex) `runLogout.ts`

```ts
export _runLogout():void {}
```
