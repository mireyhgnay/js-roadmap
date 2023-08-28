# 'null' 값 & 'undefined' 값

## **`null`**

null 값은 지금까지 소개한 자료형 중 어느 자료형에도 속하지 않는 값입니다.

**null 값은 오로지 null 값만 포함하는 별도의 자료형**을 만듭니다.

```jsx
let age = null;
```

자바스크립트에선 null을 ‘존재하지 않는(nothing)’ 값, ‘비어 있는(empty)’ 값, ‘알 수 없는(unknown)’ 값을 나타내는 데 사용합니다.

> 예를 들어, 어떠한 변수의 반환 값이 없는게 아니라 이 변수의 값은 없도록 설정하는 것! 이라고 생각하니 쉬웠다.

<br>
<br>

## **`undefined`**

undefined 값도 null 값처럼 자신만의 자료형을 형성합니다.

**undefined는 '값이 할당되지 않은 상태’**를 나타낼 때 사용합니다.

변수는 선언했지만, **값을 할당하지 않았다면** 해당 변수에 undefined가 자동으로 할당됩니다.

```jsx
let age;

alert(age); // 'undefined'가 출력됩니다.
```

개발자가 변수에 undefined를 명시적으로 할당하는 것도 가능하긴 하지만,

undefined 을 직접 할당하는 걸 권장하진 않습니다.

변수가 ‘비어있거나’ ‘알 수 없는’ 상태라는 걸 나타내려면 null을 위에 null로 설정하면 됩니다.

```jsx
let age = 100;

// 값을 undefined로 바꿉니다.
age = undefined;

alert(age); // "undefined"
```
