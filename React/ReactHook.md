# 💡Reack Hook

> Side Effect

외부 상태를 변경하는 부수효과를 의미한다. 함수형 프로그래밍에서 부수효과가 있다는 말은 함수가 호출하는 값으로 인하여 외부의 상태가 변경되어 영향을 미치게 되는것을 말합니다.

- [함수형 프로그래밍](https://github.com/goawmfhfl/My-wiki/blob/31d5cc066ec8918353f5bc95f8ba9da363a21d33/JavaScript/Functional%20Programming.md)

<br/>

> Sied Effect in React

React 컴포넌트가 화면에 1차로 렌더링된 이후에 비동기로 처리되어야 하는 부수적인 효과들을 Side Effect라고 한다. 예를들면 데이터를 가져오려고 외부 API를 호출할 때, 일단 화면에 렌더링 할 수 있는 것들은 1차로 렌더링하고 실제 데이터는 비동기로 가져오는 것이 권장이 된다. 1차 렌더링과 Side Effect를 통해서 실제 데이터를 2차 렌더링 하는 이유는 연동된 API가 응답이 늦거나 없을 경우 1차 렌더링 화면을 사용자에게 보여줌으로써 화면이 보이지 않는 답답한 문제를 해결하여 사용자 경험을 개선시킬 수 있기 때문이다.

<br/>

> React Hook이란?

함수형 컴포넌트에서도 상태 관리를 할 수 있는 useState, 그리고 렌더링 직후 작업을 설정하는 useEffect 등의 기능등을 제공하여 기존의 함수형 컴포넌트에서 할 수 없었던 다양한 작업을 할 수 있게 해준다.

# 🔗 Reference

- [https://devbirdfeet.tistory.com/52](https://devbirdfeet.tistory.com/52)
- [https://velog.io/@velopert/react-hooks](https://velog.io/@velopert/react-hooks)
