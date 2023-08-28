# <div align="center">📍 DataType(자료형)</div>

<br>

### Reference

- https://ko.javascript.info/types
- https://roadmap.sh/javascript

<br>

## DataType

### Primitive Types

<img width="443" alt="Primitive Types" src="https://github.com/mireyhgnay/js-roadmap/assets/111990266/17cb5531-47c3-4640-887f-afec24cf94b5">

<br>

### Object & typeof operator

<img width="410" alt="Object   typeof operator" src="https://github.com/mireyhgnay/js-roadmap/assets/111990266/5ad92952-6a1e-438d-bf5d-b4953bea4c25">

<br>
<br>

## 자료형 (DataType)

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

## typeof 연산자로 데이터 타입 알아보기

typeof 연산자는 인수의 자료형을 반환합니다.

자료형에 따라 처리 방식을 다르게 하고 싶거나 변수의 자료형을 빠르게 알아내고자 할 때 유용합니다.

<br>

typeof 연산자는 두 가지 형태의 문법을 지원합니다.

괄호가 있든 없든 결과가 동일합니다.

- 연산자: typeof x
  - typeof x를 호출하면 인수의 자료형을 나타내는 문자열을 반환합니다.
- 함수: typeof(x)

```jsx
typeof undefined; // "undefined"

typeof 0; // "number"

typeof 10n; // "bigint"

typeof true; // "boolean"

typeof "foo"; // "string"

typeof Symbol("id"); // "symbol"

const text = "안녕";
console.log(typeof text); // string
```

<br>

#### [숫자형 보러가기 👉](https://github.com/mireyhgnay/js-roadmap/blob/main/StudyNote/DataType/Number.md)

#### [문자형 보러가기 👉](https://github.com/mireyhgnay/js-roadmap/blob/main/StudyNote/DataType/String.md)

#### [불린형 보러가기 👉](https://github.com/mireyhgnay/js-roadmap/blob/main/StudyNote/DataType/Boolean.md)

#### ['null' 값 & 'undefined' 값 보러가기👉](https://github.com/mireyhgnay/js-roadmap/blob/main/StudyNote/DataType/null%20%26%20undefined.md)

#### [Object(객체) 와 Symbol(심볼) 보러가기 👉](https://github.com/mireyhgnay/js-roadmap/blob/main/StudyNote/DataType/Object%20%26%20Symbol.md)
