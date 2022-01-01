# 💡 async&await

Promise를 더욱 쉽게 사용할 수 있도록 ES8에서 추가된 문법이다
함수의 앞부분에 async 키워드를 추가하고, 함수 내부의 Promise의 앞부분에 await키워드를 사용한다.
async await을 사용할 경우 코드가 간결해져 유지보수가 편하며 동기적인 흐름으로 개발이 가능하다는 장점이 있습니다.

<br/>

# 🚀 Example

```jsx
register: async (req, res) => {
  const { 유저이름, 비밀번호 } = req.body;
  const 존재 = await User.findOne({ 유저이름: 유저이름 });
  if (존재) {
    res.status(504).send("유저가 존재합니다");
    return;
  }
  const 유저 = new User({
    유저이름: 유저이름,
  });
  const 해쉬화된비밀번호 = await bcrypt.hash(비밀번호, 10);
  유저.비밀번호 = 해쉬화된비밀번호;
  await user.save();
  res.redirect("/");
};
```

이전에 회원가입 기능을 구현할 때 node.js를 통해서 사용해본 경험이 있다. 유저에 대한 정보를 조회하고 조회한 데이터를 토대로 순서에 맞게
로직을 작성하기 위해서 사용했다.

<br/>

# 🔗 Reference

<br/>
