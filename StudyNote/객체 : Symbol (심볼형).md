# <div align="center">📍 객체 : Symbol (심볼형)</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - symbol](https://ko.javascript.info/symbol)

<br>

자바스크립트는 객체 프로퍼티 키로 오직 문자형과 심볼형만 허용합니다.

<br>

## 심볼

유일한 식별자를 만들고 싶을 때 사용합니다.

Symbol() 를 사용해서 심볼값을 만들 수 있습니다.

```jsx
let id = Symbol(); // id는 새로운 심볼이 됩니다.
let id = Symbol("id"); // id심볼에 "id"라는 설명이 붙습니다.
```

설명이 같은 심볼을 두개 만들어서 비교해도 false 로 반영됩니다.

```jsx
let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 == id2); // false
```
