# 💡 클로저란?

자신이 생성될 때의 환경을 기억하는 함수를 클로저라고 한다.
외부함수에서 반환된 내부함수가 자신이 선언되었을 떄의 환경인 스코프를 기억하여
자신이 선언되었을 때의 환경 밖에서 호출되어도 그 환경에 접근할 수 있는 함수이다.

이런 특징을 이용한다면 비공개 데이터를 가진 객체를 만들어 볼 수 있다.

<br/>

> 클로저를 사용하는 이유는 무엇인가?

1. 현재 상태를 기억하고 변경된 최신 상태를 유지하기 위해서 사용한다.
2. 전역 변수의 사용을 억제하기 위해서 사용한다.
3. 정보를 은닉하기 위해서 사용한다.

<br/>

# 🚀 예시코드

- 폐쇄된 공간에 대한 접근 권한을 가진 함수

```jsx
var outer = function () {
  var a = 1;
  var inner = function () {
    var b = 2;
    var c = 3;

    a = a + b + c;
    console.log(a);
  };
  return inner;
};

var newInner = outer();

newInner();
```

- outer 함수는 inner 함수를 반환한 후에 함수의 생명주기가 파괴된다.
- newInner 함수를 통해 생명주기가 끝난 outer 함수의 내부함수 inner 함수를 실행시킨다.
- 이때 inner는 outer가 이미 반환된 후에도 outer의 변수에 대한 접근 권한을 갖는다.

- 폐쇄된 공간에 접근해보자.

```jsx
var outer = (function () {
  var a = 5;
  return {
    inner1: function () {
      console.log(a);
      return a;
    },

    inner2: function (item) {
      a = item;
      console.log(a);
    },
  };
})();

console.log(outer.a); // undefined
```

- 함수 a에 접근을 하기 위해서 outer함수의 변수 a를 호출
- 접근을 할 수 없기에 undefined 반환

- 변수 a에 접근을 하기위해서는 외부함수에서 반환한 내부함수를 통해서 접근 가능

```jsx
var outer = (function () {
  var a = 5;
  return {
    inner1: function () {
      console.log(a);
      return a;
    },
  };
})();

outer.inner1(); // 5
```

- 이런 특징을 이용하면 비공개 데이터를 가진 객체를 만들 수 있다.

<br/>

# 🔗 Reference

- [https://sunnykim91.tistory.com/121](https://sunnykim91.tistory.com/121)
