# ๐ก์ค์์ ๋ ฌ

<img width="500" alt="em" src="../src/์ค์์ ๋ ฌ.png">

- HTML

```css
<div class="pg-container">
	<div class="pg-wrapper">
	  <div class="pg-item">padding</div>
	  <div class="pg-item">margin</div>
	</div>
</div>
```

- CSS

```css
.pg-container {
  width: 300px;
  height: 300px;
  background-color: #fff;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
.pg-wrapper {
  width: 100px;
  height: 100px;
  background-color: bisque;
}
.pg-item:nth-child(1) {
  background-color: black;
  opacity: 0.3;
  text-align: center;
  height: 30px;
  line-height: 30px;
}
.pg-item:nth-child(2) {
  background-color: pink;
  opacity: 0.3;
  text-align: center;
  height: 30px;
  line-height: 30px;
}
```

> Element Node ์ค์ ์ ๋ ฌ

- `display`

```css
display: flex
justify-content:center
align-item:center
```

๋ถ๋ชจ Element์ flex ์์ฑ์ ์ฃผ๊ณ  ์ค์ ์ ๋ ฌ

- `margin`

```css
margin: 0 auto;
```

์ค์ ์ ๋ ฌํ ๋ ค๋ Element์ margin 0 auto ์์ฑ ์ ์ฉ

> Content Node ์ค์ ์ ๋ ฌ

```css
text-align: center; /* ์ํ์ ๋ ฌ */
height: 30px; /* ์์ง์ ๋ ฌ */
line-height: 30px; /* ์์ง์ ๋ ฌ */
```

Content๋ธ๋์ ling-height๊ฐ ์ผ์น์ํค๊ธฐ
