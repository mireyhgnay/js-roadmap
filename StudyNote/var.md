# <div align="center">📍 var</div>

<br>

### Reference

- [MDN - 변수 var](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/var)
- [모던 JavaScript 튜토리얼 - variabels](https://ko.javascript.info/variables)

<br>
<br>

전역, 함수 스코프를 가집니다. 블록 스코프를 가지지 않습니다.

호이스팅으로 값이 undefined로 초기화 됩니다.

> 호이스팅은 코드가 실행하기 전 변수선언/함수선언이 해당 스코프의 최상단으로 끌어 올려진 것 같은 현상을 말한다.

따라서 선언 전 변수에 접근할 수 있습니다.

값을 다시 할당하거나 변수를 다시 선언할 수 있습니다.

<br>

## 블록 스코프를 가지지 않음

```jsx
var x = 1;

if (x === 1) {
  var x = 2;
  console.log(x); // 2
}
console.log(x); // 2
```

if문 블록 안에서 x를 다시 선언, 값을 할당 했지만, 블록 스코프를 가지지 않아 블록을 벗어나도 2가 찍힙니다.

<br>

```jsx
function foo() {
  var x = 1;

  function bar() {
    var y = 2;
    console.log(x); // 1
    console.log(y); // 2
  }

  bar();

  console.log(x); // 1
  console.log(y); // ReferenceError: y is not defined
}

foo();
```

- 함수 bar에서 x에 접근이 가능합니다. 자신의 외부 변수를 기억, 접근할 수 있는 클로저 특성 때문이죠.
- bar 외부에서 y에 접근하면 에러가 발생합니다. y는 bar 스코프에 속하기 때문에, foo 스코프에서는 y를 알지 못합니다.

<br>

## 호이스팅

```jsx
console.log(x); // undefined (not ReferenceError)

var x = 1;
console.log(x); // 1
```

var 변수는 코드 실행 전에 만들어집니다.  
전역 객체의 non-configurable 속성으로 추가되며, 초기 값은 undefined 입니다.

<br>

**non-configurable 특징**

- delete로 지울 수 없음
- 플래그(writable, enumerable, configurable)를 수정할 수 없음

**호이스팅**

변수 선언이 스코프 최 상단으로 옮겨지는 것 같은 현상

**왜 호이스팅이 있는걸까?**

자바스크립트는 변수를 자신의 스코프 최 상단에 선언할 것을 권장. 함수 스코프 변수와 체이닝 확인이 명확해지기 때문.

<br>

### 예제1 - 전역 스코프

```jsx
console.log(bla); // undefined
bla = 2; // 2
var bla; // 2
```

위 코드는 다음과 같이 해석됩니다.

<br>

```jsx
var bla;
console.log(bla); // undefined
bla = 2; // 2
```

<br>

### 예제2 - 함수 스코프

```jsx
function do_something() {
  console.log(bar); // undefined
  var bar = 111;
  console.log(bar); // 111
}
```

위 코드는 다음과 같이 해석됩니다.

<br>

```jsx
function do_something() {
  var bar;
  console.log(bar); // undefined
  var bar = 111;
  console.log(bar); // 111
}
```

<br>

### 예제3 - 전역, 함수 스코프

```jsx
var x = 0;
function f() {
  var x = (y = 1);
}
f();

console.log(x, y); // 0, 1
```

- 변수 y는 함수 f의 스코프에 속할 것 같지만, 선언이 없어 전역 스코프에서 만들어집니다.
- 함수 f에서 선언한 x는 전역 변수 x와 이름은 같지만 다릅니다. 스코프가 서로 다르기 때문이죠.
- strict 모드에서는 y가 정의되지 않아 ReferenceError가 발생합니다.
