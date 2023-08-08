# <div align="center">📍 const</div>

<br>

### Reference

- [MDN - 변수 const](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/const)
- [모던 JavaScript 튜토리얼 - variabels](https://ko.javascript.info/variables)

<br>

const는 블록 스코프를 가집니다.

TDZ를 가지므로 선언 전에는 접근할 수 없습니다.

전역 스코프에서 선언한 경우 전역 객체 속성을 만들지 않습니다.

같은 스코프에서 다시 선언할 수 없습니다.

선언만 할 수 없습니다. 초기화도 같이 해주세요.

const 변수의 값은 바꿀 수 없습니다.(정확히는 값이 아닌 주소입니다.)

**단! 타입이 객체인 경우 속성은 바꿀 수 있습니다.**

상수는 보통 대문자를 씁니다.(특히 원시 타입 변수)

<br>

## 블록 스코프

```jsx
const MY_FAV = 7;

if (MY_FAV === 7) {
  const MY_FAV = 20;
  console.log(MY_FAV); // 20

  var MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
}

console.log(MY_FAV); // 7
```

- 이미 const 로 MY_FAV가 선언되었기 떄문에 똑같은 변수명을 var,let,const 모두 사용해도 선언할 수 없다.

<br>

## 재 할당, 재 선언 불가

```jsx
const MY_FAV = 7;

console.log("my favorite number is: " + MY_FAV);

MY_FAV = 20; // TypeError: Assignment to constant variable

const MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
var MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
let MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
```

<br>

## 객체 속성(또는 원소) 변경 가능

**Object**

```jsx
const MY_OBJECT = { key: "value" };
MY_OBJECT.key = "otherValue"; // key값 변경 OK!

// MY_OBJECT 객체 내용을 바꾸는건 No!
MY_OBJECT = { OTHER_KEY: "value" }; // TypeError: Assignment to constant variable.
```

<br>

**Array**

```jsx
const MY_ARRAY = [];
MY_ARRAY.push("A"); // 배열 원소 추가는 OK!

// 배열을 아예 바꾸는건 No!
MY_ARRAY = ["B"]; // TypeError: Assignment to constant variable.
```
