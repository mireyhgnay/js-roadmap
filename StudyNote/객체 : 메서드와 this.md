# <div align="center">📍 객체 : 메서드와 this</div>

<br>

### Reference

[🔗 JAVASCRIPT.INFO - object_methods](https://ko.javascript.info/object-methods)

<br>

## 메서드 만들기

자바스크립트에서는 객체의 프로퍼티에 함수를 할당해 객체에게 행동할 수 있는 능력을 부여해줍니다.

```jsx
// 방법1
let user = {
  name: "John",
  age: 30,
};

user.sayHi = function () {
  alert("안녕하세요!");
};

user.sayHi(); // 안녕하세요!

// 방법2
let user = {
  name: "John",
  age: 30,
};

function sayHi() {
  alert("안녕하세요!");
}

let hi = sayHi; // sayHi함수를 hi의 메서드로 등록

user.hi(); // 안녕하세요!
```

방법1은 객체 프로퍼티 user.sayHi 에 함수를 할당해준 것이고,

방법2는 함수를 먼저 선언해주고 변수로 함수를 할당해 호출할 수 있습니다.

이렇게 객체 프로퍼티에 할당된 함수를 메서드(method)라고 합니다.

sayHi() 형태로 등록하게되면 함수의 결과값이 등록되서 호출됩니다.  
sayHi 로 함수 형식으로 등록을 해주고, 이후 객체 프로퍼티를 사용해서 호출해주면 됩니다.

<br>

## 객체 안에 메서드 간단하게 등록하기

```jsx
user = {
  sayHi() {
    // "sayHi: function()"과 동일합니다.
    alert("Hello");
  },
};
```

<br>

## 메서드 & this

메서드 내부에서 this 키워드를 사용하면 객체에 접근할 수 있습니다.

```jsx
let user = {
  name: "John",
  age: 30,

  sayHi() {
    // 'this'는 '현재 객체'를 나타냅니다.
    alert(this.name);
    // 외부 변수를 참조해서 객체 접근(비추천)
    alert(user.name);
  },
};

user.sayHi(); // John
```

- this는 user(현재 객체)를 가르킵니다.

- this 키워드를 사용하지 않고 외부 변수를 참조해서 객체에 접근할 수 있지만, 그치 추천하지 않는 방식입니다.
- 이후에 user가 null로 변경될 시 에러가 남

<br>

## 자바스크립트에선 모든 함수에 `this`를 사용할 수 있ㅅ브니다.

this 값은 런타임에 결정됩니다.

메서드가 어디서 정의되었는지에 상관없이 this는 ‘점 앞의’ 객체가 무엇인가에 따라 ‘자유롭게’ 결정됩니다.

<br>

## 정리하자면

- 객체 프로퍼티에 저장된 함수를 메서드라고 부릅니다.
- object.FunctionName(); 은 객체를 행동할 수 있게 해줍니다.
- 메서드는 this로 객체를 참조합니다.

- this는 런타임에 결정됩니다.
- 함수가 호출되기 전까지는 this엔 값이 할당되지 않습ㄴ디ㅏ.

- 화살표 함수는 자신만의 this를 갖지 않습니다. 화살표 함수 안에서 this 사용 시 외부에서 this 값을 가져옵니다.
