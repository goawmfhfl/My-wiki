# ๐กReact Router v5 โ v6

<br/>

- `use Routes Wrapper`

```jsx
<Routes>
  <Route path="/" element={<HomeScreen />} exact />
</Routes>
```

๊ธฐ์กด v5์์๋ ๋ผ์ฐํฐ๋ฅผ ๊ตฌํํ๊ธฐ ์ํด์๋ Routes๋ผ๋ Wrapper๊ฐ ํ์ํ์ง์์

Routes ๋ผ๋ Wrapper๊ฐ ์๊น๊ณผ ๋์์ ๋ช๊ฐ์ง ๋ณํ๊ฐ ์๊น

1. component โ element๋ก ๋ณ๊ฒฝ
2. element ๋ด๋ถ์๋ jsx๋ฌธ๋ฒ ์ฌ์ฉ ๊ฐ๋ฅ

- `useNavigate`

v5: ๋ฆฌ๋ค์ด๋ ์ ๊ตฌํ

```jsx
if (error) {
  // ์์ฒญ์ ๋ํ ์๋ต๊ฐ์ผ๋ก ์๋ฌ๊ฐ ๋์ฌ ๊ฒฝ์ฐ / ๊ฒฝ๋ก๋ก ์ด๋
  return <Redirect to="/" />;
}
```

v6: ๋ฆฌ๋ค์ด๋ ์ ๊ตฌํ

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

v6: ๋ค๋ก๊ฐ๊ธฐ ํ์ด์ง ๊ตฌํ

```jsx
import { BrowserRouter as Router, Route, Routes, useNavigate, goBack} from "react-router-dom";

const navigate = useNavigate()

<Button onclick ={()=>{
  navigate(-1)
}} text='go Back'><button>
```

- `useLocation`

pํ๊ทธ์ ํ์ฌ ํ์ด์ง์ ๊ฒฝ๋ก ํ์

```jsx
import { BrowserRouter as Router, Route, Routes,useLocation} from "react-router-dom";
const { pathname }= useLocation()

<p>{pathname}</p>
```

<br/>

# ๐ย Reference

- [https://www.youtube.com/watch?v=k2Zk5cbiZhg&t=1s](https://www.youtube.com/watch?v=k2Zk5cbiZhg&t=1s)
