# ๐กuseState & useEffect

## `useState๋ ?`

```jsx
import React, { useState } from "react";

const [value, setValue] = useState(0);
```

๋ฆฌ์กํธ์ ๊ฐ์ฅ ๊ธฐ๋ณธ์ ์ธ Hook์ผ๋ก์จ ํจ์ํ ์ปดํฌ๋ํธ์์ ๊ฐ๋ณ์ ์ธ ์ํ๋ฅผ ์ง๋๊ณ  ์์ ์ ์๊ฒ ๋์์ฃผ๋ ํจ์์๋๋ค. useState๋ฅผ ํธ์ถํ๋ฉด ๊ธฐ๋ณธ์ ์ผ๋ก ๋ฐฐ์ด์ ๋ฐํํฉ๋๋ค. ๋น๊ตฌ์กฐํ ํ ๋น ๋ฌธ๋ฒ์ ํตํด์ ์ฒซ๋ฒ์งธ ๊ฐ์ ์ํ ๊ฐ์ ํ ๋นํ๊ณ , ๋๋ฒ์งธ ๊ฐ์ ์ํ๋ฅผ ์ค์ ํ๋ ํจ์๋ฅผ ํ ๋นํฉ๋๋ค. ์ด ๋๋ฒ์งธ ์ํ๋ฅผ ์ค์ ํ๋ ํจ์์ ํ๋ผ๋ฏธํฐ๋ฅผ ๋ฃ์ด์ ํธ์ถํ๊ฒ ๋๋ฉด ์ ๋ฌ๋ฐ์ ํ๋ผ๋ฏธํฐ๋ก ๊ฐ์ด ๋ฐ๋๊ฒ ๋๊ณ  ์ปดํฌ๋ํธ๋ ์ ์์ ์ผ๋ก ๋ฆฌ๋ ๋๋ง ๋ฉ๋๋ค.

<br/>

> ๋์ useState ํ์ฉ๊ธฐ

```jsx
const JoinMembershipScreen = () => {
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");
	...
	return(
		<div>
        <input
          name="email"
          type="email"
          placeholder="์ด๋ฉ์ผ"
          value={email}
          onChange={(e) => setEmail(e.currentTarget.value)}
        />
		</div>
		<div>
        <input
          name="password"
          type="password"
          placeholder="๋น๋ฐ๋ฒํธ"
          value={password}
          onChange={(e) => setPassword(e.currentTarget.value)}
        />
		</div>
    <div>
        <button type="button" onClick={loginHandler}>
          ๋ค์
        </button>
        <button type="button" onClick={logoutHandler}>
          ๋ก๊ทธ์์
        </button>
		</div>
)
```

๋ก๊ทธ์ธ์ ๊ตฌํํ ๋ ์ฌ์ฉ์๊ฐ ์๋ ฅํ ๊ฐ์ ๋ฐ์์ค๊ธฐ ์ํด์ ์ฌ์ฉํ์๋ค. input์ฐฝ์ ์๋ ฅ๋ ๊ฐ์ ์ํ๋ณ๊ฒฝํจ์๋ฅผ ํตํด์ ์ ๋ฌํจ์ผ๋ก์จ ๋ณ๊ฒฝ๋ ๊ฐ์ด ๋ฆฌ๋ ๋๋ง ๋  ์ ์๊ฒ ํด์ฃผ์๋ค.

<br/>

## `useEffect๋?`

```jsx
import React, { useEffect } from 'react';

useEffect(() => {
 console.log("rendering");
    });
  },[value]);
```

useEffect ๋ ๋ฆฌ์กํธ ์ปดํฌ๋ํธ๊ฐ ๋ ๋๋ง ๋  ๋๋ง๋ค ํน์  ์์์ ์ํํ๋๋ก ์ค์  ํ  ์ ์๋ Hook ์๋๋ค. useEffect ๋ผ๋ Hook ์ ์ฌ์ฉํ๋ฉด ์ปดํฌ๋ํธ๊ฐ ๋ง์ดํธ ๋์ ๋ (์ฒ์ ๋ํ๋ฌ์ ๋), ์ธ๋ง์ดํธ ๋์ ๋ (์ฌ๋ผ์ง ๋), ๊ทธ๋ฆฌ๊ณ  ์๋ฐ์ดํธ ๋  ๋ ํน์  ์์์ ์ฒ๋ฆฌํ  ์ ์๊ฒ ๋ฉ๋๋ค.

<br/>

> ๋ง์ดํธ๋ ์ด๋ ์ํฉ์์ ์ฐ์ด๋๊ฐ?

- `props`๋ก ๋ฐ์ ๊ฐ์ ์ปดํฌ๋ํธ์ ๋ก์ปฌ ์ํ๋ก ์ค์ ํ  ๋
- ์ธ๋ถ API ์์ฒญ (REST API ๋ฑ)
- setInterval ์ ํตํ ๋ฐ๋ณต์์ ํน์ setTimeout ์ ํตํ ์์ ์์ฝ

<br/>

> ์ธ๋ง์ดํธ๋ ์ด๋ ์ํฉ์์ ์ฐ์ด๋๊ฐ?

- setInterval, setTimeout ์ ์ฌ์ฉํ์ฌ ๋ฑ๋กํ ์์๋ค clear ํ๊ธฐ (clearInterval, clearTimeout)

# ๐ย Reference

- [https://velog.io/@velopert/react-hooks](https://velog.io/@velopert/react-hooks)
- [https://react.vlpt.us/basic/16-useEffect.html](https://react.vlpt.us/basic/16-useEffect.html)
