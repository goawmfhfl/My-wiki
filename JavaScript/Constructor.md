# 💡생성자 함수

> 생성자 함수란?

- 생성자란 앞에 new 키워드가 붙은 함수를 의미한다.
- 생성자 함수의 new 연산자는 인스턴스를 참조한다.

> 왜 사용하는가?

- 동일한 프로퍼티와 메소드를 가진 객체를 쉽게 대량 생산 하기 위해서 사용된다.

# 🚀 예시

> 생성자 함수란?

- 자바스크립트 Array를 통한 객체 생성

```jsx
var myArray = new Array(1, 2, 3);
console.log(myArray); // [1,2,3]
```

- 직접 객체 생성

```jsx
function MyOwn() {}
var myObj = new MyOwn();
```

이때 생성자 함수 명의 첫 문자는 대문자로 시작해야한다.
일종의 약속이다.

> 왜 생성자 함수를 사용하는가?

```jsx
function Realtionship(person) {
  this.person = person;
  this.who = function () {
    console.log("이 분은 저의 " + this.person + " 입니다.");
  };
}

var famaily = new Realtionship("가족");
var firend = new Realtionship("친구");
var girlFriend = new Realtionship("여자친구");

famaily.who(); // 이 분은 저의 가족 입니다.
firend.who(); // 이 분은 저의 친구 입니다.
girlFriend.who(); // 이 분은 저의 여자친구 입니다.
```

생성자 함수의 this는 일반 함수의 this와 다르게 동작한다.
생성자 함수의 this는 생성자 함수 본인을 가리킨다.

new연산자가 자동으로 인스턴스를 반환하기 때문에 함수안에 `return`을 사용할 필요도 없다.

> 생성자함수 vs 일반함수 내부의 this 참조

```jsx
function Person() {
  console.log(this);
}

var me = new Person(); // Person()
var you = Person(); // window
```

- new연산자를 사용하여 생성자 함수를 호출할 경우 this는 생성할 인스턴스를 가리킨다. 여기서 생성할 인스턴스란 무엇일까? 바로 me를 의미한다. me는 생성자 함수를 통해서 생성된 인스턴스이다.
- new연산자를 사용하지 않고 함수를 호출할 경우 this는 window를 가리킨다.
