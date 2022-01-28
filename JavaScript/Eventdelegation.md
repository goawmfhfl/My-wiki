# 💡 이벤트 위임과 이벤트 핸들러

<br/>

# 기존 이벤트 핸들러에 매개변수를 넘기는 방법 1

```jsx
<body>
  <ul class="부모박스" style="background-color: brown">
    <button class="자식버튼1">자식 버튼1</button>
    <button class="자식버튼2">자식 버튼2</button>
    <button class="자식버튼3">자식 버튼3</button>
  </ul>
</body>;
// <script>
const 자식버튼1 = document.querySelector(".자식버튼1");

const 숫자 = 12345;

function handleClick(매개변수) {
  console.log(매개변수);
}
자식버튼1.addEventListener("click", () => {
  handleClick(숫자);
});
// </script>
```

<br/>

- 모든 버튼에 이벤트 추가하기

```jsx
<body>
  <ul class="부모박스" style="background-color: brown">
    <button class="자식버튼1">자식 버튼1</button>
    <button class="자식버튼2">자식 버튼2</button>
    <button class="자식버튼3">자식 버튼3</button>
  </ul>
</body>;

// <script>
const 자식버튼1 = document.querySelector(".자식버튼1");
const 자식버튼2 = document.querySelector(".자식버튼2");
const 자식버튼3 = document.querySelector(".자식버튼3");

const 숫자 = 12345;
const 텍스트 = "텍스트";
const 불리언 = false;

function handleClick(매개변수) {
  console.log(매개변수);
}
자식버튼1.addEventListener("click", () => {
  handleClick(숫자);
});
자식버튼2.addEventListener("click", () => {
  handleClick(텍스트);
});
자식버튼3.addEventListener("click", () => {
  handleClick(불리언);
});

// </script>
```

- 중복되는 코드가 발생한다.
- 코드의 가독성을 해치는 문제가 발생한다
- 많은 메모리 공간을 차지하게 된다.

<br/>

## 🔗  이벤트 위임이란?

- 이벤트를 자식요소에 하나하나 정해주는것이 아닌 상위 부모 요소에 이벤트를 한번 등록 함으로써 부모 요소에서 등록한 이벤트가 자식요소에 전파되는 것을 말합니다.

```jsx
<body>
    <ul class="부모박스" style="background-color: brown">
      <button class="자식버튼1">자식 버튼1</button>
      <button class="자식버튼2">자식 버튼2</button>
      <button class="자식버튼3">자식 버튼3</button>
    </ul>
  </body>

  <script>
    const 부모박스 = document.querySelector(".부모박스");

    function handleClick() {
      console.log(" 당신의 클릭에 handleClick 함수가 호출되었습니다.");
    }

    부모박스.addEventListener("click", () => {
      // handleClick();
      // console.dir(이벤트객체);
      // console.log(이벤트객체.currentTarget);
      // console.log(이벤트객체.target);
      // handleClick(이벤트객체.target);
    });
  </script>
```

<br/>

> 이벤트 객체란?

- 이벤트 객체에는 해당 클릭 이벤트가 발생한 요소에 대한 정보와 그리고 click 이벤트로 브라우저에서 알아낼 수 있는 정보들이 담겨있습니다.

<br/>

> 이벤트 위임의 장점

- 많은 이벤트 핸들러를 할당하지 않아도 되기 때문에 초기화가 단순해지고 메모리가 절약됩니다.
- 요소를 추가하거나 제거할 때 해당 요소에 할당된 핸들러를 추가하거나 제거할 필요가 없기 때문에 코드가 짧아집니다.

<br/>

> 그래서 이벤트 위임을 안하면 인터넷 속도가 저하되는거야?

- 부모박스에 할당된 핸들러가 응답할 필요가 있는 이벤트이든 아니든 상관없이 모든 자식버튼 에서 발생하는 이벤트에 응답해야 하므로 CPU 작업 부하가 늘어날 수 있습니다. 그런데 `이런 부하는 무시할만한 수준이므로 실제로는 잘 고려하지 않습니다.`

<br/>

# 기존 이벤트 핸들러에 매개변수를 넘기는 방법 2

- `onClick`

```jsx
<body>
    <ul class="부모박스" style="background-color: brown">
      <button class="자식버튼1" onclick="handleClick(숫자)">자식 버튼1</button>
      <button class="자식버튼2" onclick="handleClick(텍스트)">자식 버튼2</button>
      <button class="자식버튼3" onclick="handleClick(불리언)">자식 버튼3</button>
    </ul>
  </body>

  <script>

	const 숫자 = 12345
	const 텍스트 = "텍스트"
	const 불리언 = false

    function handleClick(매개변수) {
      console.log(매개변수);
    }
  </script>
```

- HTML 문서의 역할 ?
- CSS 문서의 역할 ?
- JavaScript 문서의 역할 ?

<br/>

# 리액트에서의 이벤트 핸들러는 어떻게 매개변수를 넘기는가?

```jsx
function App() {
  const 숫자 = 12345;
  const 텍스트 = "텍스트";
  const 불리언 = false;

  const handleClick = (매개변수) => {
    console.log(매개변수);
  };

  return (
    <>
      <div className="부모노드">
        <button onClick={() => handleClick(숫자)}>자식버튼1</button>
        <button onClick={() => handleClick(텍스트)}>자식버튼2</button>
        <button onClick={() => handleClick(불리언)}>자식버튼3</button>
      </div>
    </>
  );
}
```

<br/>

# 주의할 점

```jsx
import React from "react";

function App() {
  const 숫자 = 12345;
  const 텍스트 = "텍스트";
  const 불리언 = false;

  const handleClick = (매개변수) => {
    console.log(매개변수);
  };

  return (
    <>
      <div className="부모노드">
        <button onClick={handleClick(숫자)}>자식버튼1</button>
        <button onClick={handleClick(텍스트)}>자식버튼2</button>
        <button onClick={handleClick(불리언)}>자식버튼3</button>
      </div>
    </>
  );
}
export default App;
```

<br/>

# 🔗 Reference

- [https://ko.javascript.info/event-delegation](https://ko.javascript.info/event-delegation)
