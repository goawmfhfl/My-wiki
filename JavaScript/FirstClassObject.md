# ๐ก์ผ๊ธ๊ฐ์ฒด๋ ๋ฌด์์ธ๊ฐ?

> ์ผ๊ธ๊ฐ์ฒด

์ผ๊ธ๊ฐ์ฒด๋ฅผ ์๋ฐ์คํฌ๋ฆฝํธ์ ๊ด์ ์์ ๋ณด์๋ฉด ํจ์๋ฅผ ๊ฐ์ผ๋ก ์ทจ๊ธํ๋ ๊ฒ์ ๋งํฉ๋๋ค. ์ด๋ฐ ์ผ๊ธ ๊ฐ์ฒด์ ์กฐ๊ฑด์ ๋ง์กฑ์ํค๊ธฐ ์ํด์๋ ํจ์๋ฅผ ๋ณ์๋ ์๋ฃ๊ตฌ์กฐ์ ์ ์ฅ, ๋งค๊ฐ๋ณ์์ ์ ๋ฌ, ํจ์์ ๋ฐํ๊ฐ์ผ๋ก ์ ๋ฌํ  ์ ์์ด์ผ ํฉ๋๋ค.

<br/>

> ์ผ๊ธ๊ฐ์ฒด์ ์กฐ๊ฑด

<br/>

- ๋ณ์๋ ์๋ฃ๊ตฌ์กฐ์ ์ ์ฅํ  ์ ์๋ค.

```jsx
let fruits = function () {
  return "apple";
};

console.log(fruits);
```

<br/>

- ํจ์์ ๋งค๊ฐ๋ณ์์ ์ ๋ฌํ  ์ ์๋ค

```jsx
let fruits = function () {
  let apple = 10;
  return apple;
};

let box = function (value) {
  console.log(value);
};

box(fruits());
```

<br/>

- ํจ์์ ๋ฐํ๊ฐ์ผ๋ก ์ ๋ฌํ  ์ ์๋ค.

```jsx
function outer() {
  return function () {
    console.log("apple");
  };
}

let start = outer();
start();
```

<br/>

> ์๋ฐ์คํฌ๋ฆฝํธ๊ฐ ์ผ๊ธ ๊ฐ์ฒด์ด๊ธฐ ๋๋ฌธ์ ํ  ์ ์๋๊ฒ์ ๋ฌด์์ธ๊ฐ

- ๊ณ ์ฐจ ํจ์๋ฅผ ์ฌ์ฉํ  ์ ์๋ค. (forEach, Filter, Map, Sort...๋ฑ๋ฑ)
- ํด๋ก์ ๋ฅผ ์ฌ์ฉํ  ์ ์๋ค.
- ์ฝ๋ฐฑ ํจํด์ ์ฌ์ฉํ  ์ ์๋ค.

# ๐ย Reference

- [https://heeyeonjeong.tistory.com/108](https://heeyeonjeong.tistory.com/108)
- [https://velog.io/@reveloper-1311/์ผ๊ธ-๊ฐ์ฒดFirst-Class-Object๋](https://velog.io/@reveloper-1311/%EC%9D%BC%EA%B8%89-%EA%B0%9D%EC%B2%B4First-Class-Object%EB%9E%80)
