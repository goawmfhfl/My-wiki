# ๐ก๋ฌธ์ ๋ฐ์

productScreen ์ปดํฌ๋ํธ์ button์ ํด๋ฆญํ  ๊ฒฝ์ฐ addToCardHandler ํจ์๋ฅผ ํธ์ถ

```jsx
<Button
  onClick={addToCartHandler}
  className="btn-block"
  type="button"
  disabled={products.countInStock === 0}
>
  Add To Cart
</Button>
```

react-router V6์ navigate์ ๋ฐ๋ผ์ ํด๋น ๊ฒฝ๋ก๋ก ์ด๋ํ๊ฒ๋๋ค.

```jsx
const addToCartHandler = () => {
  navigate(`/cart/${id}?qty=${qty}`);
};
```

์๋๋ click๋ฒํผ์ผ๋ก ์ธํ์ฌ ์ด๋ํ๊ฒ ๋ url

```jsx
http://localhost:3000/cart/61d438813fa484901b2c9aa2?qty=2
```

<br/>

> ๋ฌธ์ ๋ฐ์

๋ง์ฝ ๋ค๋ฅธ CartScreen์ด๋ผ๋ ์ปดํฌ๋ํธ์์ ํด๋น id๊ฐ๊ณผ qty๊ฐ์ ์กฐํํ๋ ค๋ฉด ์ด๋ป๊ฒ ํด์ผํ ๊น?

ํ์ฌ app.js์์๋ id๊ฐ๋ง parameter๋ก ๋ณด๋ด์ค ๋ฟ์ด์ง qty๊ฐ์ ๋ถ๋ฌ์ค์ง ์๋๋ค.

```jsx
<Route path="/cart/:id" element={<CartScreen />} />
```

id๊ฐ์ useParams์ ํตํด์ ๋ถ๋ฌ์ฌ ์ ์์ง๋ง qty๋ฅผ ๋ถ๋ฌ์ค๊ธฐ ์ํด์๋ ์ด๋ป๊ฒ ํด์ผํ ๊น?

<br/>

> ๋ฌธ์ ํด๊ฒฐ

qty๊ฐ์ ์กฐํํ๊ธฐ ์ํด์ ์ฌ์ฉํ๋๊ฒ์ด ๋ฐ๋ก

`useSearchParams` ์ด๋ค

```jsx
const [searchParams] = useSearchParams();
const qty = Number(searchParams.get("qty"));
```

Getting Query Strings ์ ํตํ์ฌ qty์ ๋ฌธ์์ด์ ๋ถ๋ฌ์๊ณ  Number๋ฅผ ํตํด์ ์ซ์๋ง ๋ฐํ๋๊ฒ ํ์ฌ qty๊ฐ์ ๊ตฌํ๋ค.

<br/>

# ๐ย  Reference

- [https://stackoverflow.com/questions/70456937/no-routes-matched-location-cart-in-router-router-dom-v-6/70457128](https://stackoverflow.com/questions/70456937/no-routes-matched-location-cart-in-router-router-dom-v-6/70457128)
- [https://ultimatecourses.com/blog/query-strings-search-params-react-router](https://ultimatecourses.com/blog/query-strings-search-params-react-router)
