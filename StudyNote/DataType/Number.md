# 숫자형 (Number)

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
