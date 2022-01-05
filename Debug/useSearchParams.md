# 💡문제발생

productScreen 컴포넌트의 button을 클릭할 경우 addToCardHandler 함수를 호출

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

react-router V6의 navigate에 따라서 해당 경로로 이동하게된다.

```jsx
const addToCartHandler = () => {
  navigate(`/cart/${id}?qty=${qty}`);
};
```

아래는 click버튼으로 인하여 이동하게 된 url

```jsx
http://localhost:3000/cart/61d438813fa484901b2c9aa2?qty=2
```

<br/>

> 문제발생

만약 다른 CartScreen이라는 컴포넌트에서 해당 id값과 qty값을 조회하려면 어떻게 해야할까?

현재 app.js에서는 id값만 parameter로 보내줄 뿐이지 qty값은 불러오지 않는다.

```jsx
<Route path="/cart/:id" element={<CartScreen />} />
```

id값은 useParams을 통해서 불러올 수 있지만 qty를 불러오기 위해서는 어떻게 해야할까?

<br/>

> 문제해결

qty값을 조회하기 위해서 사용하는것이 바로

`useSearchParams` 이다

```jsx
const [searchParams] = useSearchParams();
const qty = Number(searchParams.get("qty"));
```

Getting Query Strings 을 통하여 qty의 문자열을 불러왔고 Number를 통해서 숫자만 반환되게 하여 qty값을 구했다.

<br/>

# 🔗  Reference

- [https://stackoverflow.com/questions/70456937/no-routes-matched-location-cart-in-router-router-dom-v-6/70457128](https://stackoverflow.com/questions/70456937/no-routes-matched-location-cart-in-router-router-dom-v-6/70457128)
- [https://ultimatecourses.com/blog/query-strings-search-params-react-router](https://ultimatecourses.com/blog/query-strings-search-params-react-router)
