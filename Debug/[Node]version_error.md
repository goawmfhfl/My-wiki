> 문제발생

팀원의 레파지토리를 클론 후에 npm install을 진행한 후에 live server에서 확인해 볼려고 했으나 에러가 발생했다.

- 에러메시지

```jsx
error:0308010C:digital envelope routines::unsupported
```

> 문제해결

검색해보니 node의 버전이 일치하지 않을 경우에 발생하는 에러라고한다.
프로젝트를 할 때는 모두가 같은 node버전에서 작업을 해야할 것 같다.
컨벤션처럼 따로 정해둠으로써 위와같은 문제가 발생하지 않도록 해야할 것 같다

# 🔗 Reference

- [https://han-py.tistory.com/407](https://han-py.tistory.com/407)
