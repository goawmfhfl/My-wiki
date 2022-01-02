# 💡React Router v5 → v6

<br/>

- `use Routes Wrapper`

```jsx
<Routes>
  <Route path="/" element={<HomeScreen />} exact />
</Routes>
```

기존 v5에서는 라우터를 구현하기 위해서는 Routes라는 Wrapper가 필요하지않음

Routes 라는 Wrapper가 생김과 동시에 몇가지 변화가 생김

1. component → element로 변경
2. element 내부에는 jsx문법 사용 가능

- `useNavigate`

v5: 리다이렉션 구현

```jsx
if (error) {
  // 요청에 대한 응답값으로 에러가 나올 경우 / 경로로 이동
  return <Redirect to="/" />;
}
```

v6: 리다이렉션 구현

```jsx
import {
  BrowserRouter as Router,
  Route,
  Routes,
  useNavigate,
} from "react-router-dom";

const navigate = useNavigate();

if (error) {
  return navigate("/");
}
```

- `useNavigate with goBack`

v6: 뒤로가기 페이지 구현

```jsx
import { BrowserRouter as Router, Route, Routes, useNavigate, goBack} from "react-router-dom";

const navigate = useNavigate()

<Button onclick ={()=>{
  navigate(-1)
}} text='go Back'><button>
```

- `useLocation`

p태그에 현재 페이지의 경로 표시

```jsx
import { BrowserRouter as Router, Route, Routes,useLocation} from "react-router-dom";
const { pathname }= useLocation()

<p>{pathname}</p>
```

<br/>

# 🔗 Reference

- [https://www.youtube.com/watch?v=k2Zk5cbiZhg&t=1s](https://www.youtube.com/watch?v=k2Zk5cbiZhg&t=1s)
