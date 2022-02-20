# 💡 클로저란?

자신이 생성될 때의 환경을 기억하는 함수를 클로저라고 하는데, 좀 더 자세히 말씀드리자면 외부함수에서 반환된 내부함수가 자신이 선언 되었을 때의 환경을 기억하는 것을 말합니다. 내부함수가 외부함수의 환경을 기억하고 있기 때문에 내부함수가 외부함수 밖에서 호출되어도 외부함수에 접근할 수 있게 됩니다.

<br/>

> 클로저를 사용하는 이유는 무엇인가?

- 클로저를 사용하게 될 경우 클로저 함수가 아닌 이상 외부함수에 선언된 변수의 값에 접근을 할 수 없다. 이런 특징을 사용하면 외부 함수에 전역 변수처럼 사용할 변수를 선언함으로써 전역 변수의 사용을 억제할 수 있다. 정리하자면 클로저를 사용하면 전역 변수를 사용했을 때와 같이 의도되지 않는 변경을 걱정할 필요가 없기 때문에 안정적인 프로그래밍이 가능합니다.

<br/>

- 변수의 값은 누군가에 의해 언제든지 변경될 수 있어 오류 발생의 근본적 원인이 될 수 있다. 상태 변경이나 가변(mutable) 데이터를 피하고 불변성(Immutability)을 지향하는 함수형 프로그래밍에서 부수 효과(Side effect)를 최대한 억제하여 오류를 피하고 프로그램의 안정성을 높이기 위해 클로저는 적극적으로 사용된다. -[자바스크립트 딥 다이브]

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
- [https://poiemaweb.com/js-closure](https://poiemaweb.com/js-closure)
