# 💡CSS Box model

> `CSS 박스 모델의 특징은 무엇인가?`

1. CSS박스 모델은 CSSOM의 요소들에 대하여 생성한다.
2. CSS박스 모델은 content 영역, padding, border, margin 영역이 주어진다
3. CSS 박스 모델의 크기는 width, height, padding, border, margin에 의해 계산된다.

<br/>

> `width, height`

```css
body {
  font-size: 20px;
  line-height: 20px;
  color: rgb(51, 51, 51);
}

.pg-wrapper {
  width: 100px;
  height: 100px;
  background-color: bisque;
}
.pg-item:nth-child(1) {
  background-color: black;
  /*박스의 배경화면 색상을 biesque로 가득 채운다 */
  padding-bottom: 80px;
  /* ✅ 1번 3번 */
  /*if padding-bottom: 90px; */
  /* 첫 번째 아이템 요소의 높이가 부모의 높이보다 10px이 많아져 넘치게된다. */
}
.pg-item:nth-child(2) {
  background-color: pink;
}
```

1. `height` 가 지정되어있지 않으면, 블럭 요소는 포함하고있는 내용만큼의 높이를 가질 것이고, `padding`을 더한다
2. 요소의 `height`는 내용의 `height`에 의해 계산된다.

```css
.pg-item:nth-child(1) {
  background-color: black;
  padding-left: 70px;
}
/*
✅ 1번 2번
width가 지정되어 있지 않기 때문에 부모 요소의 width값을 가진다.
( 즉 width:100% 가 Defalut값인 것처럼 동작한다는 것 )
요소에 padding-left값을 주었을 경우
부모의 너비보다 넘치게 될 경우 content는 다음줄로 넘어간다.
*/
```

1. 요소의 `width`는 내용의 `width`에 의해 계산된다.
2. `width` 가 지정되지있지 않으면, float가 아닌 블록 요소는 [부모의 너비-`padding`]에 맞게 확장된다
3. 기본적으로, `padding`과 `border`는 요소의 `width`와 `height`의 일부가 아니다.

<br/>

> Content box vs Border box

- box-sizing content-box가 적용되면 width와 height, border, margin, padding 의 값이 따로 계산되어 요소의 크기에 영향을 준다
- border - box가 적용되면 요소의 width와 height 값을 계산할 때 border와 padding도 계산에 포함된다.
- padding과 border를 박스 모델의 일부분이라고 생각하면 요소의 크기를 계산하기 쉽다.

<br/>

> block, inline, inline-block의 차이점

- block : width, height, margin, padding 모든 값 지정 가능 한 줄에 여러요소 존재 불가
- inline : width, height, matgin top, bottom 적용 불가 한 줄에 여러요소 존재 가능
- inline - block : block처럼 요소의 모든 값 지정 가능 inline 처럼 한 줄에 여러요소 존재 가능

<br/>

> flex, grid 스펙

- flexbox는 1차원 레이아웃을 대상으로 하고 Grid는 2차원 레이아웃을 대상으로한다
- flex와 grid사용하면 inline-block이나 float를 사용하는 것 보다 요소들을 쉽게 정렬 할 수 있다.
- flex와 grid는 최신의 레이아웃 기술이다, 반응형 웹 사이트 작업에 적합하다.
- 딱 하나를 정해서 쓰는것보다 flex와 grid를 상황에 맞게 적재적소에 사용하면 좋다.

<br/>

# 🔗 Reference

- [프론트엔드 면접질문 모음](https://velog.io/@chris/front-end-interview-handbook-css-3)
