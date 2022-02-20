# 💡일급객체란 무엇인가?

> 일급객체

일급객체를 자바스크립트의 관점에서 보자면 함수를 값으로 취급하는 것을 말합니다. 이런 일급 객체의 조건을 만족시키기 위해서는 함수를 변수나 자료구조에 저장, 매개변수에 전달, 함수의 반환값으로 전달할 수 있어야 합니다.

<br/>

> 일급객체의 조건

<br/>

- 변수나 자료구조에 저장할 수 있다.

```jsx
let fruits = function () {
  return "apple";
};

console.log(fruits);
```

<br/>

- 함수의 매개변수에 전달할 수 있다

```jsx
let fruits = function () {
  let apple = 10;
  return apple;
};

let box = function (value) {
  console.log(value);
};

box(fruits());
```

<br/>

- 함수의 반환값으로 전달할 수 있다.

```jsx
function outer() {
  return function () {
    console.log("apple");
  };
}

let start = outer();
start();
```

<br/>

> 자바스크립트가 일급 객체이기 때문에 할 수 있는것은 무엇인가

- 고차 함수를 사용할 수 있다. (forEach, Filter, Map, Sort...등등)
- 클로저를 사용할 수 있다.
- 콜백 패턴을 사용할 수 있다.

# 🔗 Reference

- [https://heeyeonjeong.tistory.com/108](https://heeyeonjeong.tistory.com/108)
- [https://velog.io/@reveloper-1311/일급-객체First-Class-Object란](https://velog.io/@reveloper-1311/%EC%9D%BC%EA%B8%89-%EA%B0%9D%EC%B2%B4First-Class-Object%EB%9E%80)
