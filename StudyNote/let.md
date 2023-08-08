# <div align="center">📍 let</div>

<br>

### Reference

- [MDN - 변수 let](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/let)
- [모던 JavaScript 튜토리얼 - variabels](https://ko.javascript.info/variables)

<br>
<br>

let은 블록 스코프를 가집니다.

**TDZ**를 가지므로 선언 전에는 접근할 수 없습니다.

전역 스코프에서 선언한 경우 전역 객체 속성을 만들지 않습니다.

같은 스코프에서 다시 선언할 수 없습니다.

<br>

## 블록 스코프

```jsx
function varTest() {
  var x = 1;
  {
    var x = 2; // var는 블록 스코프를 가지지 않으므로 같은 변수
    console.log(x); // 2
  }
  console.log(x); // 2
}

function letTest() {
  let x = 1;
  {
    let x = 2; // let은 블록 스코프를 가지므로 이름은 같지만 다른 변수
    console.log(x); // 2
  }
  console.log(x); // 1
}
```

<br>

## TDZ

var와 다르게 let은 선언 전 값을 초기화 하지 않습니다.

즉 초기화하는 선언 전 var처럼 undefined 로 출력되는게 아닌 것!

```jsx
console.log(x); // Uncaught ReferenceError: x is not defined
let x;
```

<br>

실제 선언 코드를 만나야 접근이 가능합니다.

```jsx
let x;
console.log(x); // undefined
```

<br>

## 재선언 불가!

같은 스코프 안에서 재 선언을 시도하면 에러가 발생합니다.

```jsx
{
  let foo;
  let foo; // SyntaxError: Identifier 'a' has already been declared
}
```

<br>

**에러 → 함수, try catch 인자와 같은 이름의 변수**

```jsx
function foo(a) {
  let a = 1; // SyntaxError: Identifier 'a' has already been declared
}
try {
} catch (e) {
  let e; // SyntaxError: Identifier 'e' has already been declared
}
```

**에러 → switch case**

case 마다 블록 스코프를 가지지 않는 경우, 같은 이름의 변수를 선언할 수 없습니다.

```jsx
let x = 1;

switch (x) {
  case 0:
    let foo;
    break;
  case 1:
    let foo; // SyntaxError: Identifier 'a' has already been declared
    break;
}
```

case 마다 블록 스코프를 가지도록 수정할 수 있습니다.

```jsx
let x = 1;

switch (x) {
  case 0: {
    let foo;
    break;
  }
  case 1: {
    let foo;
    break;
  }
}
```

<br>

## 전역 객체 속성을 만들지 않음

전역 스코프에서 var 변수를 선언하면 전역 객체의 속성이 생깁니다. let은 다릅니다.

```jsx
var x = "global";
let y = "global";

console.log(this.x); // "global"
console.log(this.y); // undefined
```

<br>

## lexical scope와 결합된 TDZ

다음 코드는 왜 에러가 발생할까요?

```jsx
function test() {
  var foo = 33;

  if (foo) {
    let foo = foo + 55; // ReferenceError
  }
}

test();
```

- foo는 함수 스코프 변수입니다.
- if문 조건식의 foo는 함수 스코프 변수입니다. 값이 33이므로 true입니다.
- if문 안에 선언한 foo는 블록 스코프 변수입니다. TDZ가 만들어집니다. 선언 전까지 접근할 수 없습니다.
- foo + 55에서 ReferenceError가 발생합니다. 블록 스코프 변수 foo를 선언 전에 접근했기 때문이죠.
