# ๐กtransform: translateY(-50%);

> Why Use transform: translateY(-50%);

Buttonํ๊ทธ์๋ position: relative๋ฅผ ์ฃผ์๊ณ  ์์์ ์์นํ ๊ฐ์์์์ position: absolute๋ฅผ ์ค์ผ๋ก์จ ๋ถ๋ชจ element์ ์์กดํ์ฌ ์์น๊ฐ์ ์ ํ  ์ ์๊ฒ ๋์๋ค. left์ top๊ฐ์ ์ฃผ์ด์ ์์น๊ฐ์ ์ ํด์ฃผ์๋ค. ์ด๋ translateY(-50%)์ ์ญํ ์ด ๊ถ๊ธํ๋ค.

```jsx
const Button = styled.div`
  position: relative;
  margin-bottom: 10px;
  width: 322px;
  height: 44px;
  border-radius: 44px;
  background-color: #fff;
  text-align: center;
  line-height: 44px;

  &::before {
    position: absolute;
    left: 14px;
    top: 50%;
    display: block;
    content: "";
    width: 24px;
    height: 24px;
    transform: translateY(-50%);
    background: url(${png}) no-repeat center / 24px 24px;
  }
`;
```

<br/>

- top:0

```jsx
--------Top of Page--------
{element}

------Middle of  Page------

------Bottom of  Page------
```

element์ ๋ณธ ์์๊ฐ ์ค์์ ์์นํด ์์ง ์์ ๊ฒ์ ์ ์ ์๋ค. ์ผ์ชฝ ์๋จ์ด๋ผ๊ณ  ํ  ์ ์๋ ๋ชจ์๋ฆฌ ๋ถ๋ถ์ด ๊ธฐ์ค์ ์ด ๋์ด์ ์์น๊ฐ ์กํ์๋ค.

<br/>

- top:50%

```jsx
--------Top of Page--------

------Middle of  Page------
{element}

------Bottom of  Page------
```

์ญ์๋ element์ ๊ธฐ์ค์ ์ด element ์ค์์ ๊ฐ๋ฆฌํค๊ณ  ์์ง์๋ค.

<br/>

- transform: translateY(-50%);

```jsx
--------Top of Page--------

{element}-Middle of Page---

------Bottom of  Page------
```

์์ ์์ฒด ๋์ด์ ์ ๋ฐ ์๋ก ๋ค์ ์ด๋ํ์ฌ ์ ์ฒด ํ์ด์ง์ ์ค์์ ๋ฐฐ์นํ  ์ ์๋ค.

<br/>

๋์ ๊ฒฝ์ฐ translate๋ฅผ ์ค์ ํ์ง ์๊ณ  top์์๋ฅผ 25%๋ง ์ ํด์ค๋ ์์๊ฐ ์ค์๋ฐฐ์น๊ฐ ๋์ด์ง๋ค. ํ์ง๋ง ๋ณ๋ก ์ข์ ๋ฐฉ๋ฒ์ ์๋ ๊ฒ ๊ฐ๋ค ๋ฐ์ค์์์ ํฌ๊ธฐ์ ๋ฐ๋ผ์ ์์น๊ฐ ๋ณํ  ์ ์๋ค.

<br/>

> ๊ฒฐ๋ก 

top: 50%์ transform: translateY(-50%)๋ฅผ ์ ์ ํ ์ฌ์ฉํ์.

# ๐ย Reference

- [https://stackoverflow.com/questions/40530101/why-is-translatey-50-needed-to-center-an-element-which-is-at-top-50/40530483](https://stackoverflow.com/questions/40530101/why-is-translatey-50-needed-to-center-an-element-which-is-at-top-50/40530483)
