# <div align="center">📍 객체 : new 연산자와 생성자 함수</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - constructor_new](https://ko.javascript.info/constructor-new)

<br>

## 유사한 객체 여러개 만들 때 유용합니다.

객체 리터럴 `{...}` 을 사용하면 객체를 쉽게 만들 수 있습니다.

enw 연산자와 생성자 함수를 사용하면 유사한 객체 여러개를 쉽게 만들 수 있습니다.

<br>

## 생성자 함수 (constructor function)

일반함수와 동일하지만, 차이를 두기 위해서 아래와 같은 규칙을 지켜주어야 합니다.

1. 함수의 첫 글자는 대문자로 시작한다.
2. 반드시 new 연산자를 붙여 실행합니다.

```jsx
function User(name) {
  this.name = name;
}

let user = new User("보라");

alert(user.name); // 보라
```

<br>

## new User(…) 실행된 후 로직

```jsx
function User(name) {
  // this = {};  (빈 객체가 암시적으로 만들어짐)

  // 새로운 프로퍼티를 this에 추가함
  this.name = name;
  this.isAdmin = false;

  // return this;  (this가 암시적으로 반환됨)
}
```

```jsx
new User("보라");
new User("하늘");
```

이렇게 다양하게 객체를 만들 수 있는 것!
