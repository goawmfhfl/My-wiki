# 💡 Callback & Promise

<br/>

> Callback?

자바스크립트는 싱글스레드 방식으로 동작한다.
이런 싱글 스레드 방식에서 비동기 처리를 위해 사용하는 패턴이 바로 콜백이다.
이러한 콜백은 함수의 처리 순서를 보장하기 위해서 사용하는 경우가 있습니다.
함수를 중첩하게 사용되는 경우에는 콜백헬이라는 것이 발생합니다.
이런 콜백헬이 발생하게 되면 코드의 흐름을 예측하기 힘들고 가독성이 좋지 않아 유지보수가 힘듭니다.
또한 일반적인 callback 함수에서는 try,catch 문이 동작하지 않아 에러처리가 힘들다는 단점이 있습니다.
이러한 프로미스의 단점을 해결하기 위해서 사용하는 것이 바로 Promise입니다.

> Promise

콜백의 단점을 해결하기 위해서 나타난 Promise이다.
ES6부터 정식으로 사용되었다.
Promise는 생성자 함수를 통해 인스턴스화 시킵니다.
비동기 처리가 성공하면 `resolve`메서드를 호출해서 비동기 처리 결과를 후속처리 메서드로 전환한다.
비동기 처리를 실패하면 `reject`메서드를 호출해서 에러 메시지를 후속 처리 메서드로 전달한다.

```jsx
// Promise 객체의 생성
const promise = new Promise((resolve, reject) => {
  // 비동기 작업을 수행한다.

  if (/* 비동기 작업 수행 성공 */) {
    resolve('result');
  }
  else { /* 비동기 작업 수행 실패 */
    reject('failure reason');
  }
});
```

> 후속처리 메서드

- Promise.prototype.then
  then 메서드는 두 개의 콜백 함수를 인수로 전달받는다.

```jsx
// fullfilled
new Promise(resolve => resolve("fulfilled")).then(
  v => console.log(v),
  e => console.log(e),
); // fulfilled

// rejected
new Promise((_, rejected) => rejected(new Error("rejected"))).then(
  v => console.log(v),
  e => console.log(e),
); // Error: rejected
```

  <br/>

첫 번째 콜백 함수는 프로미스가 fulfilled상태(resolve 함수가 호출된 상태)가 되면 호출된다. 이때 콜백 함수는 프로미스의 비동기 처리 결과를 인수로 전달받는다.

  <br/>

두 번째 콜백 함수는 프로미스가 rejected 상태(resolve 함수가 호출된 상태)가 되면 호출된다. 이때 콜백 함수는 프로미스의 에러를 인수로 전달받는다.

<br/>

- Promise.prototype.catch

catch 메서드는 한 개의 콜백 함수를 인수로 전달받는다. catch 메서드의 콜백 함수는 프로미스가 rejected 상태인 경우만 호출된다.

```jsx
new Promise((_, reject) => reject(new Error("reject"))).catch(e =>
  console.log(e),
); // Error: reject
```

<br/>

- Promise.prototype.finally

finally 메서드는 한 개의 콜백 함수를 인수로 전달받는다. finally 메서드의 콜백 함수는 프로미스의 성공(fulfilled) 또는 실패(rejected)와 상관없이 무조건 한 번 호출된다. fianlly 메서드는 프로미스의 상태와 상관없이 공통적으로 수행해야 할 처리 내용이 있을 때 유용하다. finally 메서드도 then/catch 메서드와 마찬가지로 언제나 프로미스를 반환한다.

```jsx
new Promise(() => {}).finally(() => console.log("finally")); // finally
```

<br/>

# 🚀

> 콜백에 try...catch...문을 적용시킬 수 없는 이유

<br/>

# 🔗 Reference

- https://poiemaweb.com/
