# ๐กย DOM & CSSOM & BOM & Virtual DOM

> DOM์ด๋ ๋ฌด์์ธ๊ฐ?

- DOM์ HTML ๋ฌธ์๋ฅผ ๋ธ๋ผ์ฐ์ ์์ ์ ๋์ํ  ์ ์๋๋ก ์ค๊ณ๋ ๊ฐ์ฒด์๋๋ค.
- ๋ง์ฝ ๋ธ๋ผ์ฐ์ ๊ฐ ๊ณต์ฅ์ด๋ผ๊ณ  ๊ฐ์ ํ๋ฉด ์ด๋ ์ฃผ๋ฌธ์๋ ๋ฐ๋ก DOM์ด๋ค. ๋ธ๋ผ์ฐ์ ๋ DOM์ ์๋ ๋ธ๋๋ค์ ์ค์  ์ ํ์ผ๋ก ๋ง๋ค์ด์ฃผ๋ ์ญํ ์ ํ๋ ๊ฒ์๋๋ค.
- MDN์์๋ DOM์ HTML๋ฌธ์๋ฅผ ๋ํ๋ด๋ API๋ผ๊ณ  ๋งํ๋ค

<br/>

> DOM์ ๊ด์ ์์ API๋ ๋ฌด์์ธ๊ฐ

- API๋ ํ๋ก๊ทธ๋จ๋ค์ด ์๋ก ์ํธ์์ฉํ๋ ๊ฒ์ ๋์์ฃผ๋ ๋งค๊ฐ์ฒด๋ฅผ ์๋ฏธํ๋ค.
- DOM์ ๊ด์ ์์ ๋ฐ๋ผ ๋ณธ API๋ HTML๋ฌธ์์ ๋ธ๋ผ์ฐ์ ๊ฐ ์๋ก ์ํธ์์ฉ ํ๋ ๊ฒ์ ๋์์ฃผ๋ ๋งค๊ฐ์ฒด๋ผ๊ณ  ๋ณผ ์ ์๋ค.

<br/>

> ๋ธ๋๋ ๋ฌด์์ธ๊ฐ?

- DOM์ ๊ด์ ์์ ๋ธ๋๋ HTML๋ด๋ถ์ ํ๋ํ๋์ ์ ๋ณด๋ค์ ์๋ฏธํ๋ค.
- Node๋ค์ ๋ถ๋ชจ ์์ ์์๊ด๊ณ๋ฅผ ๊ฐ์ง๊ณ  ์์ด ๋ถ๋ชจ ๋ธ๋์ ์์ฑ์ ์์ ๋ธ๋์์ ์์ ๋ฐ์ ์ฌ์ฉํ  ์ ์๋ค.

<br/>

> BOM์ด๋ ๋ฌด์์ธ๊ฐ?

- BOM์ ๋ธ๋ผ์ฐ์  ์ค๋ธ์ ํธ ๋ชจ๋ธ์ ์๋ฏธํ๋ค.
- ์๋ฅผ๋ค๋ฉด alert, navigation, history, documnet ๋ฑ๋ฑ์ด ์๋ค.
- ์ ํํ๋ ์๋ฐ์คํฌ๋ฆฝํธ๊ฐ ์๋ ์น ๋ธ๋ผ์ฐ์ ๊ฐ ์ ๊ณตํ๋ ๊ธฐ๋ฅ์ด๋ค.
- ์๋ฐ์คํฌ๋ฆฝํธ๋ฅผ ํตํด์ ๋ธ๋ผ์ฐ์ ์ ๊ธฐ๋ฅ์ ์ธ ์์๋ค์ ์ง์  ์ ์ดํ  ์ ์๋ค.

<br/>

> ์๋์ฐ ๊ฐ์ฒด๋ ๋ฌด์์ธ๊ฐ?

- ๋ชจ๋  ๊ฐ์ฒด๊ฐ ์์๋ ๊ฐ์ฒด์ด๋ค. ์ ์ญ ๊ฐ์ฒด์ด๋ฉด์, ์ฐฝ์ด๋ ํ๋ ์์ ์๋ฏธํ๋ค. ๊ทธ๋ ๊ธฐ์ ๋ธ๋ผ์ฐ์ ์ ์ฐฝ ํฌ๊ธฐ ์กฐ์ , ์ ์ฐฝ ์ด๊ธฐ ๋ฑ๋ฑ ๋ธ๋ผ์ฐ์  ์ฐฝ์ ์ธ๋ถ์ ์ธ ์ต์๋ค์ ์ผ์ผ์ด ์ค์  ํ  ์ ์๋ค.
- ์๋ฐ์คํฌ๋ฆฝํธ์ ๋ชจ๋  ๊ฐ์ฒด, ์ ์ญ ํจ์, ์ ์ญ ๋ณ์๋ค์ ์๋์ผ๋ก window ๊ฐ์ฒด์ ํ๋กํผํฐ๊ฐ ๋๋ค.
- DOM์ ์์๋ค๋ ๋ชจ๋ window ๊ฐ์ฒด์ ํ๋กํผํฐ์ด๋ค.
- let,const ํค์๋๋ฅผ ์์ฑํ ๋ณ์๋ window์ ํ๋กํผํฐ๊ฐ ๋์ง ์๋๋ค.
- var ํค์๋๋ฅผ ํตํด ์์ฑํ ๋ณ์๋ window์ ํ๋กํผํฐ๊ฐ ๋๋ค.

<br/>

> CSSOM์ด๋ ๋ฌด์์ธ๊ฐ

- CSSOM์ ์คํ์ผ๊ณผ ๊ด๋ จ๋ ๋ธ๋๋ค์ด ๋ชจ์ฌ์ ํ์ฑ๋ ๊ฐ์ฒด ํํ์ด๋ค.
- CSSOM์ ๋ธ๋ผ์ฐ์  ๋ ๋๋ง ๊ณผ์ ์์ ์คํ์ผ๊ณผ ๊ด๋ จ๋ linkํ๊ทธ๋ฅผ ๋ง๋ ์์ฑ๋๊ธฐ ์์ํ๋ค
- DOM์ด ์์ฑ์ด ๋ ์ดํ CSSOM์ด ๊ฒฐํฉ๋์ด ํ๋ฉด์ ๋ณด์ฌ์ง ์์๋ค๋ง ๊ฑธ๋ฌ์ง ํ์ Render Tree๋ก ๊ทธ๋ ค์ง๋ค.

<br/>

> ๊ฐ์ DOM์ ์ ์๊ฒผ๋๊ฐ?

์์ ์ Single Page Application์ ๋์ ๋ฐฉ์์์๋ ํ์ด์ง์ ๋ณ๊ฒฝ์ฌํญ์ด ์ผ์ด๋  ๊ฒฝ์ฐ์ Ajax ๋น๋๊ธฐ ์์ฒญ์ ํ์ฌ ๋ณ๊ฒฝ์ฌํญ์ ํ๋ํ๋ ์์ธกํ์ฌ ์์ ํด์คฌ๋ค. ์ด๋ ๊ฒ ์ฝ๋๋ฅผ ์์ ํ๋ ์ผ์ ๋ง์ ์์์๊ฐ์ ์์ํ๋ ์ผ์ด๋ค. ๋ํ ํ์ด์ง์ ๋ํ ์ฆ์ ๋ณ๊ฒฝ์ผ๋ก ์ธํ์ฌ ๋ณ๊ฒฝ๋ ๋ถ๋ถ์ ๋ํ ๋ ์ด์์ ์ฌ์์ฑ ๊ณผ์ ์ธ reflow reapint๊ฐ ์์ฃผ ๋ฐ์ํ๊ฒ ๋์๋ค. ๋ฆฌ์กํธ๋ ์ด๋ฌํ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด์ ๊ฐ์ DOM์ด๋ผ๋ ๊ฐ๋์ ๋ง๋ค์๋ค. ๊ฐ์ DOM์ ์ค์  ๋์ ๋ณต์ฌ๋ณธ์ ๋ง๋ค์ด ๋ณ๊ฒฝ๋ ๋ถ๋ถ๋ง ํจ์จ์ ์ผ๋ก ๋ณ๊ฒฝ์ด ๊ฐ๋ฅํ  ์ ์๊ฒ ์ค๊ณํ๋ค. ์ด๋ก์ธํด reflow, repaint๋ ๋จ ํ๋ฒ๋ง ์ด๋ฃจ์ด ์ง๊ฒ๋์์ผ๋ฉฐ, ๋ณ๊ฒฝ ์ฌํญ์ ๋ํ ์ฝ๋๋ฅผ ์์ธกํ์ฌ ์ผ์ผ์ด ์์ฑํ  ํ์๋ ์์ด์ก๋ค.

<br/>

> ๊ฐ์ DOM์ ๋ฌด์์ธ๊ฐ?

์ค์  ๋๊ณผ ๋ค๋ฅธ ๊ฐ์์ ๋์ผ๋ก ์ค์  ๋์ ๋ณต์ฌ๋ณธ์ด๋ผ๊ณ  ์ดํดํ๋ฉด ์ข๋ค. ๊ฐ์๋์ ๋ฉ๋ชจ๋ฆฌ์์๋ง ์กด์ฌํ๋ฉฐ ์ค์  ํ๋ฉด์๋ ๋ํ๋์ง ์๋ ๋ณต์ฌ๋ณธ๊ณผ ๊ฐ๋ค. ๊ฐ์๋์ ์ค์  ๋์์ ๋ณ๊ฒฝ์ด ์ผ์ด๋  ๊ฒฝ์ฐ ๋ณ๊ฒฝ์ฌํญ์ Diffing ์๊ณ ๋ฆฌ์ฆ์ ํตํ์ฌ ๋ถ์ํ๋ค. ๋ณ๊ฒฝ๋ ๋ถ๋ถ์ ํ์ํ๋ฉด ๋ณ๊ฒฝ๋ ๋ถ๋ถ์ ๋ํ ์๋ฐ์ดํธ๋ฅผ ์งํํ๋ค

<br/>

> ๊ฐ์ ๋์ ๋์ ์๋ฆฌ์ ๋ํด์ ์ค๋ชํด๋ฌ๋ผ

๊ธฐ์กด ๋ธ๋ผ์ฐ์  ๋ ๋๋ง์ ์์์ ๋ฐ๋ฅด๋ฉด ์๋ฐ์คํฌ๋ฆฝํธ๋ก DOM์ ์์๊ฐ ๋ณ๊ฒฝ์ด ๋  ๋๋ง๋ค ๋งค๋ฒ ๋ฆฌํ๋ก์ฐ ๋ฆฌํ์ธํธ๊ฐ ๋ฐ์ํ์ฌ ์ฑ๋ฅ ์ ํ์ ์ฃผ๋ ์์ธ์ด ๋์๋ค. ๋ฆฌ์กํธ์ ๋ฒ์ถ์ด ๋์ ํน์  ๋ถ๋ถ์ด ๋ฆฌ๋ ๋๋ง ๋์ด์ผ ํ  ๋ ๊ทธ ๋ถ๋ถ์ ํด๋นํ๋ virtual DOM ํธ๋ฆฌ๋ฅผ ๋ฉ๋ชจ๋ฆฌ์ ์๋ก ์์ฑํ๊ณ  diffing ์๊ณ ๋ฆฌ์ฆ์ผ๋ก ๋น๊ตํ์ฌ ์ฐจ์ด์ ์ ํ์ํ๋ค ๊ทธ๋ฆฌ๊ณ  ๊ทธ ์ฐจ์ด์ ๋ค์ ํ๋๋ก ๋ชจ์์ virtual DOM์ ํ๋๋ก ๋ชจ์์ ์ค์  DOM์๊ฒ ์ ๋ฌํด์ค๋ค. ์ด๋ก ์ธํด์ ์ค์  DOM์ ๋ฆฌ๋ ๋๋ง ์ฐ์ฐ์ ๋จ ํ๋ฒ๋ง ์ผ์ด๋๊ฒ ๋์ด ํฐ ์ฑ๋ฅ์ ์ด๋์ ์ป๊ฒ ๋๋ค.

<br/>

> ๊ฐ์ ๋์ด ์ฐ์ด๋ ์ง์ง ์ด์ 

DOM ์กฐ์์ ์ค์  ๋ฌธ์ ๋ ๊ฐ ์กฐ์์ด ๋ ์ด์์ ๋ณํ, ํธ๋ฆฌ ๋ณํ์ ๋ ๋๋ง์ ์ผ์ผํจ๋ค๋๊ฒ๋๋ค. ๊ทธ๋์, ์๋ฅผ ๋ค์ด ์ฌ๋ฌ๋ถ์ด 30๊ฐ์ ๋ธ๋๋ฅผ ํ๋ ํ๋ ์์ ํ๋ฉด, ๊ทธ ๋ป์ 30๋ฒ์ (์ ์ฌ์ ์ธ) ๋ ์ด์์ ์ฌ๊ณ์ฐ๊ณผ 30๋ฒ์ (์ ์ฌ์ ์ธ) ๋ฆฌ๋ ๋๋ง์ ์ด๋ํ๋ค๋ ๊ฒ์ด์ฃ . Virtual DOM ์ ๊ทธ๋ฅ ๋ญ ์์ฒญ ์๋ก์ด๊ฒ๋ ์๋๊ณ , ๊ทธ๋ฅ DOM ์ฐจ์์์์ ๋๋ธ ๋ฒํผ๋ง์ด๋ ๋ค๋ฆ์ด ์๋๊ฑฐ์์. ๋ณํ๊ฐ ์ผ์ด๋๋ฉด ๊ทธ๊ฑธ ์คํ๋ผ์ธ DOM ํธ๋ฆฌ์ ์ ์ฉ์ํค์ฃ . ์ด DOM ํธ๋ฆฌ๋ ๋ ๋๋ง๋ ๋์ง ์๊ธฐ๋๋ฌธ์ ์ฐ์ฐ ๋น์ฉ์ด ์ ์ด์. ์ฐ์ฐ์ด ๋๋๊ณ ๋๋ฉด ๊ทธ ์ต์ข์ ์ธ ๋ณํ๋ฅผ ์ค์  DOM ์ ๋์ ธ์ฃผ๋๊ฑฐ์์. ๋ฑ ํ๋ฒ๋ง ํ๋๊ฑฐ์์.

๋ชจ๋  ๋ณํ๋ฅผ ํ๋๋ก ๋ฌถ์ด์. ๊ทธ๋ฌ๋ฉด, ๋ ์ด์์ ๊ณ์ฐ๊ณผ ๋ฆฌ๋ ๋๋ง์ ๊ท๋ชจ๋ ์ปค์ง๊ฒ ์ง๋ง, ๋ค์ ํ๋ฒ ๊ฐ์กฐํ์๋ฉด ๋ฑ ํ๋ฒ๋ง ํ๋๊ฑฐ์์. ๋ฐ๋ก ์ด๋ ๊ฒ, ํ๋๋ก ๋ฌถ์ด์ ์ ์ฉ์ํค๋๊ฒ์ด, ์ฐ์ฐ์ ํ์๋ฅผ ์ค์ด๋๊ฑฐ๊ตฌ์.

์ฌ์ค, ์ด ๊ณผ์ ์ Virtual DOM ์ด ์์ด๋ ์ด๋ค์ง์ ์์ด์. ๊ทธ๋ฅ, ๋ณํ๊ฐ ์์ ๋, ๊ทธ ๋ณํ๋ฅผ ๋ฌถ์ด์ DOM fragment ์ ์ ์ฉํ ๋ค์์ ๊ธฐ์กด DOM ์ ๋์ ธ์ฃผ๋ฉด ๋ผ์.

๊ทธ๋ฌ๋ฉด, Virtual DOM ์ด ํด๊ฒฐ ํ๋ ค๊ณ  ํ๋๊ฑด ๋ฌด์์ด๋? `DOM fragment๋ฅผ ๊ด๋ฆฌํ๋ ๊ณผ์ ์ ์๋์ผ๋ก ํ๋ํ๋ ์์ ํ  ํ์ ์์ด, ์๋ํํ๊ณ  ์ถ์ํํ๋๊ฑฐ์์.` ๊ทธ ๋ฟ๋ง ์๋๋ผ, ๋ง์ฝ์ ์ด ์์์ ์ฌ๋ฌ๋ถ๋ค์ด ์ง์  ํ๋ค๋ฉด, ๊ธฐ์กด ๊ฐ ์ค ์ด๋ค๊ฒ ๋ฐ๋์๊ณ  ์ด๋ค๊ฒ ๋ฐ๋์ง ์์๋์ง ๊ณ์ ํ์ํ๊ณ  ์์ด์ผํ๋๋ฐ (๊ทธ๋ ์ง ์์ผ๋ฉด ์์  ํ  ํ์๊ฐ ์๋ DOM ํธ๋ฆฌ๋ ์๋ฐ์ดํธ๋ฅผ ํ๊ฒ ๋  ์๋ ์์ผ๋๊น์), ์ด๊ฒ๋ Virtual DOM ์ด ์ด๊ฑธ ์๋์ผ๋ก ํด์ฃผ๋๊ฑฐ์์. ์ด๋ค๊ฒ ๋ฐ๋์๋์ง , ์ด๋ค๊ฒ ๋ฐ๋์ง ์์๋์ง ์์๋ด์ฃผ์ฃ .

๋ง์ง๋ง์ผ๋ก, DOM ๊ด๋ฆฌ๋ฅผ Virtual DOM ์ด ํ๋๋ก ํจ์ผ๋ก์จ, ์ปดํฌ๋ํธ๊ฐ DOM ์กฐ์ ์์ฒญ์ ํ  ๋ ๋ค๋ฅธ ์ปดํฌ๋ํธ๋ค๊ณผ ์ํธ์์ฉ์ ํ์ง ์์๋ ๋๊ณ , ํน์  DOM ์ ์กฐ์ํ  ๊ฒ ์ด๋ผ๋์ง, ์ด๋ฏธ ์กฐ์ํ๋ค๋์ง์ ๋ํ ์ ๋ณด๋ฅผ ๊ณต์  ํ  ํ์๊ฐ ์์ต๋๋ค. ์ฆ, ๊ฐ ๋ณํ๋ค์ ๋๊ธฐํ ์์์ ๊ฑฐ์น์ง ์์ผ๋ฉด์๋ ๋ชจ๋  ์์์ ํ๋๋ก ๋ฌถ์ด์ค ์ ์๋ค๋๊ฑฐ์ฃ .

# ๐ย Reference

- [https://it-eldorado.tistory.com/87](https://it-eldorado.tistory.com/87)
- [https://www.youtube.com/watch?v=1ojA5mLWts8](https://www.youtube.com/watch?v=1ojA5mLWts8)
- [https://velopert.com/3236](https://velopert.com/3236)
- [https://wickies.tistory.com/26](https://wickies.tistory.com/26)
- [http://www.tcpschool.com/javascript/js_bom_window](http://www.tcpschool.com/javascript/js_bom_window)
- [https://basemenks.tistory.com/24](https://basemenks.tistory.com/24)
