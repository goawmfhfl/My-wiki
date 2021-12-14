# 💡 em rem

> **_em rem은 왜 사용하는가?_**

em과 rem 단위를 쓰면 디자인이 유연해지면서, 고정된 크기에만 머무는 게 아니라 구성 요소의 크기를 늘리고 줄이는 게 가능해집니다. 그래서 이런 유연성을 디자인에 적용하면 개발 기간에 만나는 여러 상황에 대한 대처가 훨씬 쉬워지고, 또 브라우저 사용자는 전체 사이트의 크기를 조절해 가면서 읽기에 가장 적합한 환경을 손수 구성할 수도 있다

> **_em rem 은 언제 사용하는가?_**

`rem 단위`를 쓰면, 변환된 픽셀 크기는 페이지 최상위(root) 요소, 그러니까 html 요소의 폰트 크기가 기준이 된다.

`em 단위`를 쓰면 변환되는 픽셀값은 스타일을 지정한 요소의 폰트 크기를 곱한 값이 됩니다.

- 부모요소에 크기에 따라서 사이즈가 변경되어야 한다면 em을 사용한다.
- 브라우저 사이즈에 따라서 반응해야 한다면 rem을 사용한다
- 폰트사이즈에 따라서 크기가 변경되어야 한다면 em rem을 사용한다

<br/>

# 🚀 코드예시

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

현재 HTML의 태그들은 div.step1>div.step2>div.step3>div.step4로 중첩이 되어 있는 상태이다. 이때 크기를 결정하는 기준은 부모요소가 된다. (root font size: 16px > 32px > 64px > 128px > 256px)

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

em과 다르게 크기를 결정하는 기준은 root의 font-size이다. 이에따라 중첩이 되어있음에도 불구하고 모두의 기준점은 같다. (root font size: 16px > 32px > 32px > 32px > 32px)

> font size = rem , padding = em을 주었을 경우

padding을 em으로 주게 되면 요소(폰트)의 크기에 비례한 크기가 결정된다. 이를 활용하면 아래와 같이 폰트사이즈가 변경 될 경우 padding값이 줄어들어 유연성있게 디자인이 가능하다.

https://user-images.githubusercontent.com/79143800/145941478-0763e24b-7454-432b-987d-981282568c3e.mov

# 🔗 Reference

- [https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984](https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984)
- [https://www.youtube.com/watch?v=xWMKz9NCD0k](https://www.youtube.com/watch?v=xWMKz9NCD0k)
