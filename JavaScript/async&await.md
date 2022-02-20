# 💡 async&await

Promise를 더욱 쉽게 사용할 수 있도록 ES8에서 추가된 문법이다.
async await을 사용할 경우에는 비동기 요청의 흐름을 동기적인 흐름으로 개발자가 제어할 수 있습니다.
사용 방법은 함수의 앞부분에 async 키워드를 추가하고, 함수 내부의 Promise의 앞부분에 await키워드를 사용합니다.

<br/>

# 🚀 Example

```jsx
register: async (요청, 응답) => {
  const { 유저이름, 비밀번호 } = 요청.body;
  const 존재 = await User.findOne({ 유저이름: 유저이름 });
  if (존재) {
    응답.status(504).send("유저가 존재합니다");
    return;
  }
  const 유저 = new User({
    유저이름: 유저이름,
  });
  const 해쉬화된비밀번호 = await bcrypt.hash(비밀번호, 10);
  유저.비밀번호 = 해쉬화된비밀번호;
  await 유저.save();
  응답.redirect("/");
};
```

이전에 회원가입 기능을 구현할 때 사용해본 경험이 있다. 사용환경은 node.js였다.
요청한 사용자의 정보를 얻어온 후에 얻어온 사용자의 정보에 해쉬화된 비밀번호를 설정해 주었다. 그때 await async를 통하여 비동기 요청이 동기적으로 동작할 수 있게 흐름을 제어한 경험이 있다.

<br/>

# 🔗 Reference

<br/>
