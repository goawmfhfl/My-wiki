# ๐กย em rem

> **_em rem์ ์ ์ฌ์ฉํ๋๊ฐ?_**

em๊ณผ rem ๋จ์๋ฅผ ์ฐ๋ฉด ๋์์ธ์ด ์ ์ฐํด์ง๋ฉด์, ๊ณ ์ ๋ ํฌ๊ธฐ์๋ง ๋จธ๋ฌด๋ ๊ฒ ์๋๋ผ ๊ตฌ์ฑ ์์์ ํฌ๊ธฐ๋ฅผ ๋๋ฆฌ๊ณ  ์ค์ด๋ ๊ฒ ๊ฐ๋ฅํด์ง๋๋ค. ๊ทธ๋์ ์ด๋ฐ ์ ์ฐ์ฑ์ ๋์์ธ์ ์ ์ฉํ๋ฉด ๊ฐ๋ฐ ๊ธฐ๊ฐ์ ๋ง๋๋ ์ฌ๋ฌ ์ํฉ์ ๋ํ ๋์ฒ๊ฐ ํจ์ฌ ์ฌ์์ง๊ณ , ๋ ๋ธ๋ผ์ฐ์  ์ฌ์ฉ์๋ ์ ์ฒด ์ฌ์ดํธ์ ํฌ๊ธฐ๋ฅผ ์กฐ์ ํด ๊ฐ๋ฉด์ ์ฝ๊ธฐ์ ๊ฐ์ฅ ์ ํฉํ ํ๊ฒฝ์ ์์ ๊ตฌ์ฑํ  ์๋ ์๋ค

> **_em rem ์ ์ธ์  ์ฌ์ฉํ๋๊ฐ?_**

`rem ๋จ์`๋ฅผ ์ฐ๋ฉด, ๋ณํ๋ ํฝ์ ํฌ๊ธฐ๋ ํ์ด์ง ์ต์์(root) ์์, ๊ทธ๋ฌ๋๊น html ์์์ ํฐํธ ํฌ๊ธฐ๊ฐ ๊ธฐ์ค์ด ๋๋ค.

`em ๋จ์`๋ฅผ ์ฐ๋ฉด ๋ณํ๋๋ ํฝ์๊ฐ์ ์คํ์ผ์ ์ง์ ํ ์์์ ํฐํธ ํฌ๊ธฐ๋ฅผ ๊ณฑํ ๊ฐ์ด ๋ฉ๋๋ค.

- ๋ถ๋ชจ์์์ ํฌ๊ธฐ์ ๋ฐ๋ผ์ ์ฌ์ด์ฆ๊ฐ ๋ณ๊ฒฝ๋์ด์ผ ํ๋ค๋ฉด em์ ์ฌ์ฉํ๋ค.
- ๋ธ๋ผ์ฐ์  ์ฌ์ด์ฆ์ ๋ฐ๋ผ์ ๋ฐ์ํด์ผ ํ๋ค๋ฉด rem์ ์ฌ์ฉํ๋ค
- ํฐํธ์ฌ์ด์ฆ์ ๋ฐ๋ผ์ ํฌ๊ธฐ๊ฐ ๋ณ๊ฒฝ๋์ด์ผ ํ๋ค๋ฉด em rem์ ์ฌ์ฉํ๋ค

<br/>

# ๐ย ์ฝ๋์์

## em

<img width="200" alt="em" src="https://user-images.githubusercontent.com/79143800/145941407-a2380e11-4af0-43d6-8882-0a6a45e1878b.png">

```css
.step1 {
  font-size: 2em;
}
.step2 {
  font-size: 2em;
}
.step3 {
  font-size: 2em;
}
.step4 {
  font-size: 2em;
}
```

ํ์ฌ HTML์ ํ๊ทธ๋ค์ div.step1>div.step2>div.step3>div.step4๋ก ์ค์ฒฉ์ด ๋์ด ์๋ ์ํ์ด๋ค. ์ด๋ ํฌ๊ธฐ๋ฅผ ๊ฒฐ์ ํ๋ ๊ธฐ์ค์ ๋ถ๋ชจ์์๊ฐ ๋๋ค. (root font size: 16px > 32px > 64px > 128px > 256px)

<br/>

## rem

<img width="200" alt="em" src="../img/rem.png">

```css
.step1 {
  font-size: 2rem;
}
.step2 {
  font-size: 2rem;
}
.step3 {
  font-size: 2rem;
}
.step4 {
  font-size: 2rem;
}
```

em๊ณผ ๋ค๋ฅด๊ฒ ํฌ๊ธฐ๋ฅผ ๊ฒฐ์ ํ๋ ๊ธฐ์ค์ root์ font-size์ด๋ค. ์ด์๋ฐ๋ผ ์ค์ฒฉ์ด ๋์ด์์์๋ ๋ถ๊ตฌํ๊ณ  ๋ชจ๋์ ๊ธฐ์ค์ ์ ๊ฐ๋ค. (root font size: 16px > 32px > 32px > 32px > 32px)

> font size = rem , padding = em์ ์ฃผ์์ ๊ฒฝ์ฐ

padding์ em์ผ๋ก ์ฃผ๊ฒ ๋๋ฉด ์์(ํฐํธ)์ ํฌ๊ธฐ์ ๋น๋กํ ํฌ๊ธฐ๊ฐ ๊ฒฐ์ ๋๋ค. ์ด๋ฅผ ํ์ฉํ๋ฉด ์๋์ ๊ฐ์ด ํฐํธ์ฌ์ด์ฆ๊ฐ ๋ณ๊ฒฝ ๋  ๊ฒฝ์ฐ padding๊ฐ์ด ์ค์ด๋ค์ด ์ ์ฐ์ฑ์๊ฒ ๋์์ธ์ด ๊ฐ๋ฅํ๋ค.

https://user-images.githubusercontent.com/79143800/145941478-0763e24b-7454-432b-987d-981282568c3e.mov

# ๐ย Reference

- [https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984](https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984)
- [https://www.youtube.com/watch?v=xWMKz9NCD0k](https://www.youtube.com/watch?v=xWMKz9NCD0k)
