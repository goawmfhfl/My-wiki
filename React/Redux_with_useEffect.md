# ๐กRedux with useEffect

# ๐ย Code

<br/>

> useEffect๋ฅผ ํตํ ๋ณด์ผ๋ฌ ํ๋ ์ดํธ ๋์๋ฐฉ์ ์ดํดํ๊ธฐ.

```jsx
const HomeScreen = () => {
  console.log("start");
  const dispatch = useDispatch();
  const productList = useSelector(state => state.productList);
  console.log(productList);
  const { loading, error, products } = productList;

  useEffect(() => {
    console.log(dispatch);
    console.log("useEffect");
    dispatch(listProducts());
  }, [dispatch]);

  console.log("end");
  return (
	 .......
  );
};
```

- ํด๋น ์ฝ๋๋ฅผ ์ฐ์์ ๋ ๋์ค๋ console.log

<img width="500" alt="result" src="../src/result.png">

์ฒ์ฒํ ๋ถ์ํด๋ณด์.

๋๋ ์ด ๊ณผ์ ์ ์์ค์ฝ๋ ํ๊ฐ ๊ณผ์  ๊ทธ๋ฆฌ๊ณ  ์ค์  ๋ฐํ์ ํ๊ฒฝ์ธ ์์ค์ฝ๋ ์คํ ๊ณผ์ ์ผ๋ก ๊ตฌ๋ถ์ง์ด ์ดํดํด ๋ณด๋ ค๊ณ ํ๋ค.

<br/>

- `์์ค์ฝ๋ ํ๊ฐ๊ณผ์ ` ๐

```jsx
const HomeScreen = () => {
  console.log("start"); // ๐ ํจ์ ํธ์ด์คํ
  const dispatch = useDispatch(); // ๐ undefined
  const productList = useSelector(state => state.productList); // ๐ undefined
  console.log(productList); // ๐ ํจ์ ํธ์ด์คํ
  const { loading, error, products } = productList; // ๐ undefined

  useEffect(() => {
    console.log(dispatch);
    console.log("useEffect");
    dispatch(listProducts());
  }, [dispatch]);

// ๐ ํจ์ ํธ์ด์คํ

  console.log("end"); // ๐ ํจ์ ํธ์ด์คํ
  return (
	 .......
  );
};
```

<br/>

- `์์ค์ฝ๋ ์คํ๊ณผ์ ` ๐ฆย  ์ด๊ธฐํ ๋ฐ ํจ์ ํธ์ถ

```jsx
const HomeScreen = () => {
  console.log("start"); // ๐ฆ "start" ์ถ๋ ฅ
  const dispatch = useDispatch(); //๐ฆ useDispatch return๊ฐ์ผ๋ก ์ด๊ธฐํ
  const productList = useSelector(state => state.productList);
//๐ฆ useSelector return๊ฐ์ผ๋ก ์ด๊ธฐํ
  console.log(productList); // ๐ฆ "productList" ์ถ๋ ฅ
  const { loading, error, products } = productList; // ๊ตฌ์กฐ ๋ถํด ์ด๊ธฐํ

  useEffect(() => {
    console.log(dispatch);
    console.log("useEffect");
    dispatch(listProducts());
  }, [dispatch]); // ๋ณํ๊ฐ ์์ผ๋ฏ๋ก ์๋ฌด๋ฐ ์ถ๋ ฅ์ ํ์ง ์๋๋ค.

  console.log("end"); //  ๐ฆ "productList" ์ถ๋ ฅ
  return (
	 .......
  );
};
```

<br/>

> Action

๋ฉ์๋๋ ์ฝ๋ฐฑ์ ๋๋ฒ์งธ ์ธ์๋ก ๋๊ฒจ์ค ๋ฐฐ์ด์ ๊ฐ์ ๋ณํ๊ฐ ์์ ๊ฒฝ์ฐ์ ํจ์๋ฅผ ํธ์ถํ๋ค. listProducts ํจ์๋ฅผ ํธ์ถํ๋ค dispatch๋ฅผ ํตํด์ ์ก์์ ๊ธฐ๋ฅ์ ์ํํ๋ lisrProducts ์ปดํฌ๋ํธ๋ก ์ด๋ํ๋ค

```jsx
export const listProducts = () => async dispatch => {
  try {
    dispatch({ type: PRODUCT_LIST_REQUEST });

    const { data } = await axios.get("/api/products");

    dispatch({
      type: PRODUCT_LIST_SUCCESS,
      payload: data,
    });
  } catch (error) {
    dispatch({
      type: PRODUCT_LIST_FAIL,
      payload:
        error.response && error.response.data.message
          ? error.response.data.message
          : error.message,
    });
  }
};
```

์ด๋ listProducts ๋ด๋ถ์ ๋ก์ง์ ๋ณด๋ฉด dispatch๋ฅผ ํตํด์ ๋๋ฒ์ ๋น๋๊ธฐ ํจ์๋ฅผ ํธ์ถํ๋ค. ๊ทธ์ ๋ฐ๋ผ์ reducer์ ์๋ PRODUCT_LIST_REQUEST, PRODUCT_LIST_SUCCESS, PRODUCT_LIST_FAIL ์ฆ, ์์ฒญ, ์ฑ๊ณต, ์คํจ์ ๊ดํ type์ ๋ช์ํด์ ๋ณด๋ธ๋ค.

<br/>

> Reducer

```jsx
export const productListReducer = (state = { products: [] }, action) => {
  switch (action.type) {
    case PRODUCT_LIST_REQUEST:
      return { loading: true, products: [] };
    case PRODUCT_LIST_SUCCESS:
      return { loading: false, products: action.payload };
    case PRODUCT_LIST_FAIL:
      return { loading: false, error: action.payload };
    default:
      return state;
  }
};
```

Action์ ํตํด์ ๋ฐ์์จ action.type์ ๊ฐ์ switch case๋ฌธ์ ์ํด์ ์คํ๋๋ค. ์ด๋ ์ํฉ์ ๋ง๊ฒ return์ด ๋๋ ๊ฐ์ด ๋ณ๊ฒฝ์ด ๋๋ค. ์ฌ๊ธฐ์ ๊ฐ์ฅ ์ค์ํ ๋ถ๋ถ์ ๋ฐ๋ก return์ ๊ฐ์ด๋ค. ์์  action์ ๋น๋๊ธฐ ์์ฒญ์ผ๋ก ์ธํด์ reducer์์๋ ์์ฒญ๊ณผ ์ฑ๊ณต ํน์ ์์ฒญ๊ณผ ์คํจ์ ๋ํ ๊ฐ์ ๋ฐํํ๋ค. ๋ฐ๋ก ์ด ๊ฐ์ ๋ฐํํ  ๋ useEffect์ ์๋ productList์ loading ๊ฐ๊ณผ products์ ํ ๋น๋ state๊ฐ ๋ณํ๊ฒ ๋๋ฉด์ useEffect ํจ์๊ฐ ํธ์ถ์ด ๋๋ค.

<br/>

๋ฐ๋ผ์ ๊ฐ์ ๋ณํ๋ฅผ ์ธ์งํ useEffect๊ฐ ํธ์ถ์ด ๋๋ฉด์ ๊ฐ๋ค์ด ์ถ๋ ฅ์ด๋๊ณ  ๋ค์ ๋ณํ๊ฐ ์๋์ง ์๋์ง ํ์ธํ๋ค. ์์ ๋ณธ๊ฒ๊ณผ ๊ฐ์ด action์ ํตํด์ 2๋ฒ์ dispatch๊ฐ ํธ์ถ์ด ๋์๊ณ  reducer๋ 2๋ฒ์ ๋ณํ๋ฅผ ์ฃผ์๋ค. ๊ทธ์ ๋ฐ๋ผ์ useEffect๋ฅผ ํตํด์ 2๋ฒ์ ํธ์ถ์ด ์ผ์ด๋ฌ๊ณ  ๊ทธ ๊ฒฐ๊ณผ๋ก ๋ฐํ์ ๊ณผ์ ์ด 2๋ฒ ๋ ์ผ์ด๋๊ฒ ๋์๋ค.

<img width="500" alt="result" src="../src/result.png">
