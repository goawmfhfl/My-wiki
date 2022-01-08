> 에러발생

```jsx
choejaeyeong@choejaeyeong-ui-MacBookAir redux % npx create-react-app redux
Need to install the following packages:
  create-react-app
Ok to proceed? (y) Y

You are running `create-react-app` 4.0.3, which is behind the latest release (5.0.0).

We no longer support global installation of Create React App.

Please remove any global installs with one of the following commands:
- npm uninstall -g create-react-app
- yarn global remove create-react-app

The latest instructions for creating a new app can be found here:
https://create-react-app.dev/docs/getting-started/
```

creat-react-app을 하려고 했으니 설치가 제대로 안됨... 무슨 문제인지 몰라서 일단은 가이드라인에 따라서 `- npm uninstall -g create-react-app` 명령어 입력후에 다시 `npx create-react-app redux` 그래도 설치가 안됨, 무슨 문제인 지 모르겠음

<br/>

> 문제해결

검색해보니 문제 해결방법을 알려주는 친절한 블로그 발견

```jsx
npm uninstall -g create-react-app
npm add create-react-app
npx create-react-app redux
```

위의 순서그대로 진행했더니 다시 react 파일을 다운받게되었다.

<br/>

# 🔗 Reference

- [https://velog.io/@milkyway/React-오류-해결-You-are-running-create-react-app-4.0.2-which-is-behind-the-latest-release-4.0.3](https://velog.io/@milkyway/React-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0-You-are-running-create-react-app-4.0.2-which-is-behind-the-latest-release-4.0.3)
