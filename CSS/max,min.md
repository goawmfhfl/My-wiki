# ๐กmax & min

> ์ธ์  ์ฐ์ด๋ ์์ฑ์ธ๊ฐ?

๋ฐ์ํ ์น์์ ํฌ๊ธฐ๋ฅผ ์กฐ์ ํ  ๋ ์ฌ์ฉ๋๋ค. ๋๋ฐ์ด์ค ํ๋ฉด์ ๋ฐ๋ผ ํฌ๊ธฐ๊ฐ ๋ค๋ฅด๊ธฐ ๋๋ฌธ์ ์ฌ์ฉํ๋ ์์ฑ์ผ๋ก ํ๋ฉด์ด ๋๋ฌด ์ปค์ง๊ฑฐ๋ ์์์ง ๋๋ฅผ ๋๋นํ์ฌ ์ต๋, ์ต์๊ฐ์ ์ ํด์ฃผ๋ ๊ฒ์ด๋ค.

# ๐ย ์์ 

```css
<style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .container {
      box-sizing: border-box;
      padding: 1rem;
      background-color: black;
      width: 80%;
      height: 500px;
    }
    .item {
      box-sizing: border-box;
      background-color: white;
      width: 50%;
     /* max-width: 400px; */
     /* min-width: 400px; */
      height: 50%;
    }
    .item:nth-child(1) {
      background-color: wheat;
      background-image: url(https://cdn.pixabay.com/photo/2019/07/25/06/51/thuja-4361821_1280.jpg);
      background-size: cover;
      background-repeat: no-repeat;
    }
    .item:nth-child(2) {
      background-color: wheat;
      background-image: url(https://cdn.pixabay.com/photo/2021/11/23/11/14/town-6818441_1280.jpg);
      background-size: cover;
      background-repeat: no-repeat;
    }
  </style>
  <body>
    <div class="container">
      <div class="item"></div>
      <div class="item"></div>
    </div>
  </body>
```

- `max-width, min-width ์์ฑ์ ๋๋ค ์ง์ ํ์ง ์์์ ๋`

https://user-images.githubusercontent.com/79143800/146844274-e06c509f-e82e-4f37-b233-dce1a3f878ab.mov

container์์ ์๋ item์์๋ container์ ํฌ๊ธฐ๊ฐ ์ค์ด๋ฆ์ ๋ฐ๋ผ์ item์ ๋ด๊ธด ์ด๋ฏธ์ง ์์๊ฐ ์ค์ด๋๋ ๊ฒ์ ๋ณผ ์ ์๋ค.

- `max-width`

https://user-images.githubusercontent.com/79143800/146844415-cc269684-f4fe-4a99-8df7-4059b5d1daad.mov

container์์ ์๋ item์์๋ container์ ํฌ๊ธฐ๊ฐ ์๋ฌด๋ฆฌ ์ปค์ง๋๋ผ๋ ์ง์ ํด๋ max-width๊ฐ ์ด์๋งํผ์ ์ปค์ง์ง ์๋๋ค. ๋ ์ต๋ํ ์ด๋งํผ๋ง ๋์ด์ง๊ฑฐ์ผ! ๋ผ๊ณ  ์ ํด์ฃผ๋ ๊ฒ๊ณผ ๊ฐ๋ค

- `min-width`

https://user-images.githubusercontent.com/79143800/146844427-6be3e258-e00d-48ac-b750-b818d0537c89.mov

container์์ ์๋ item์์๋ container์ ํฌ๊ธฐ๊ฐ ์๋ฌด๋ฆฌ ์์์ง๋๋ผ๋ ์ง์ ํด๋ min-width๊ฐ ์ดํ๋งํผ์ ์์์ง์ง ์๋๋ค. ๋ ์ ์ด๋ ํฌ๊ธฐ๋ ์ ์งํ ๊ฑฐ์ผ ! ๋ผ๊ณ  ์ค์ ํ๋ ๊ฒ๊ณผ ๊ฐ๋ค.


# ๐ย Reference

[https://m.blog.naver.com/govlrhaehfdl/221243111912](https://m.blog.naver.com/govlrhaehfdl/221243111912)
