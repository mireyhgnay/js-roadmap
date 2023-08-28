# 문자형 (String)

자바스크립트에선 문자열(string)을 따옴표로 묶습니다.

```jsx
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
따옴표는 세 종류가 있습니다.
```

- 큰따옴표: "Hello"
- 작은따옴표: 'Hello'
- 역 따옴표(백틱, backtick): `Hello`

<br>

큰따옴표와 작은따옴표는 ‘기본적인’ 따옴표로, 자바스크립트에서는 이 둘에 차이를 두지 않습니다.

역 따옴표로 변수나 표현식을 감싼 후 ${…}안에 넣어주면, 아래와 같이 원하는 변수나 표현식을 문자열 중간에 손쉽게 넣을 수 있습니다.

<br>

```jsx
let name = "HONG";

// 변수를 문자열 중간에 삽입
alert(`Hello, ${name}!`); // Hello, HONG!

// 표현식을 문자열 중간에 삽입
alert(`the result is ${1 + 2}`); // the result is 3
```

`${}` 안에 단순 계산 말고도 다양하게 자바스크립트 코드를 넣을 수 있습니다.

<br>
<br>
