# 💡max & min

> 언제 쓰이는 속성인가?

반응형 웹에서 크기를 조절할 때 사용된다. 디바이스 화면에 따라 크기가 다르기 때문에 사용하는 속성으로 화면이 너무 커지거나 작아질 때를 대비하여 최대, 최솟값을 정해주는 것이다.

# 🚀 예제

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

- `max-width, min-width 속성을 둘다 지정하지 않았을 때`

https://user-images.githubusercontent.com/79143800/146844274-e06c509f-e82e-4f37-b233-dce1a3f878ab.mov

container안에 있던 item요소는 container의 크기가 줄어듦에 따라서 item에 담긴 이미지 요소가 줄어드는 것을 볼 수 있다.

- `max-width`

https://user-images.githubusercontent.com/79143800/146844415-cc269684-f4fe-4a99-8df7-4059b5d1daad.mov

container안에 있던 item요소는 container의 크기가 아무리 커지더라도 지정해둔 max-width값 이상만큼은 커지지 않는다. 난 최대한 이만큼만 넓어질거야! 라고 정해주는 것과 같다

- `min-width`

https://user-images.githubusercontent.com/79143800/146844427-6be3e258-e00d-48ac-b750-b818d0537c89.mov

container안에 있던 item요소는 container의 크기가 아무리 작아지더라도 지정해둔 min-width값 이하만큼은 작아지지 않는다. 난 적어도 크기는 유지할거야 ! 라고 설정하는 것과 같다.


# 🔗 Reference

[https://m.blog.naver.com/govlrhaehfdl/221243111912](https://m.blog.naver.com/govlrhaehfdl/221243111912)
