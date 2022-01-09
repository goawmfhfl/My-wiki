# 💡useState & useEffect

## `useState란 ?`

```jsx
import React, { useState } from "react";

const [value, setValue] = useState(0);
```

리액트의 가장 기본적인 Hook으로써 함수형 컴포넌트에서 가변적인 상태를 지니고 있을 수 있게 도와주는 함수입니다. useState를 호출하면 기본적으로 배열을 반환합니다. 비구조화 할당 문법을 통해서 첫번째 값에 상태 값을 할당하고, 두번째 값은 상태를 설정하는 함수를 할당합니다. 이 두번째 상태를 설정하는 함수에 파라미터를 넣어서 호출하게 되면 전달받은 파라미터로 값이 바뀌게 되고 컴포넌트는 정상적으로 리렌더링 됩니다.

<br/>

## `useEffect란?`

```jsx
import React, { useEffect } from 'react';

useEffect(() => {
 console.log("rendering");
    });
  },[value]);
```

useEffect 는 리액트 컴포넌트가 렌더링 될 때마다 특정 작업을 수행하도록 설정 할 수 있는 Hook 입니다. useEffect 라는 Hook 을 사용하면 컴포넌트가 마운트 됐을 때 (처음 나타났을 때), 언마운트 됐을 때 (사라질 때), 그리고 업데이트 될 때 특정 작업을 처리할 수 있게 됩니다.

> 마운트는 어느 상황에서 쓰이는가?

- `props`로 받은 값을 컴포넌트의 로컬 상태로 설정할 때
- 외부 API 요청 (REST API 등)
- setInterval 을 통한 반복작업 혹은 setTimeout 을 통한 작업 예약

> 언마운트는 어느 상황에서 쓰이는가?

- setInterval, setTimeout 을 사용하여 등록한 작업들 clear 하기 (clearInterval, clearTimeout)

# 🔗 Reference

- [https://velog.io/@velopert/react-hooks](https://velog.io/@velopert/react-hooks)
- [https://react.vlpt.us/basic/16-useEffect.html](https://react.vlpt.us/basic/16-useEffect.html)
