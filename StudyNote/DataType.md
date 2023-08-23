# <div align="center">📍 DataType(자료형)</div>

<br>

### Reference

- https://ko.javascript.info/types
- https://roadmap.sh/javascript

<br>
<br>

## DataType

### Primitive Types

<img width="443" alt="Primitive Types" src="https://github.com/mireyhgnay/js-roadmap/assets/111990266/17cb5531-47c3-4640-887f-afec24cf94b5">

<br>

### Object & typeof operator

<img width="410" alt="Object   typeof operator" src="https://github.com/mireyhgnay/js-roadmap/assets/111990266/5ad92952-6a1e-438d-bf5d-b4953bea4c25">

<br>
<br>

## 자료형

자바스크립트에서 값은 항상 문자열이나 숫자형 같은 특정한 자료형에 속합니다.

자바스크립트에는 **여덟 가지** 기본 자료형이 있습니다.

변수는 어떤 순간에 문자열일 수 있고 다른 순간엔 숫자가 될 수도 있습니다.

<br>

```jsx
let message = "hello";
message = 123456;
```

위 같이 해도 에러가 나지 않습니다.

이처럼 자료의 타입은 있지만 변수에 저장되는 값의 타입은 언제든지 바꿀 수 있는 언어를 **‘동적 타입(dynamically typed)’ 언어**라고 부릅니다.

<br>

## 숫자형

```jsx
let n = 123;
n = 12.345;
```

숫자형(number type) 은 정수 및 부동소수점 숫자(floating point number)를 나타냅니다.

숫자형과 관련된 연산은 곱셈 \*, 나눗셈 /, 덧셈 +, 뺄셈 - 등이 대표적입니다.

<br>

숫자형엔 일반적인 숫자 외에 Infinity, -Infinity, NaN같은 '특수 숫자 값(special numeric value)'이 포함됩니다.

- Infinity

  ```jsx
  alert(1 / 0); // 무한대
  ```

- NaN
  ```jsx
  alert("숫자가 아님" / 2); // NaN, 문자열을 숫자로 나누면 오류가 발생합니다.
  ```
  - 연산 과정 어디에선가 NaN이 반환되었다면, 이는 모든 결과에 영향을 미칩니다.

<br>

[숫자형 더 공부하기👉]()
