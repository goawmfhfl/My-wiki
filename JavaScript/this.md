```jsx
function NotArrow() {
  this.name = "i am this.name";
  return {
    name: "i am object name",
    callMyName: function () {
      console.log(this.name);
    },
  };
}

// 일반 함수는 자신이 종속된 객체를 this로 가리킨다

const test1 = new NotArrow();
test1.name; // i am object name
test1.callMyName(); // i am object name

function Arrowfunction() {
  this.name = "i am this.name";
  return {
    name: "i am object name",
    callMyName: () => {
      console.log(this.name);
    },
  };
}

// 화살표 함수는 자신이 종속된 인스턴스를 가리킵니다.

const test2 = new Arrowfunction();
test2.name; // i am object name
test2.callMyName(); // i am this.name
```
