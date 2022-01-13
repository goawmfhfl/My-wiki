# 💡transform: translateY(-50%);

> Why Use transform: translateY(-50%);

Button태그에는 position: relative를 주었고 자식에 위치한 가상요소에 position: absolute를 줌으로써 부모 element에 의존하여 위치값을 정할 수 있게 되었다. left와 top값을 주어서 위치값을 정해주었다. 이때 translateY(-50%)의 역할이 궁금했다.

```jsx
const Button = styled.div`
  position: relative;
  margin-bottom: 10px;
  width: 322px;
  height: 44px;
  border-radius: 44px;
  background-color: #fff;
  text-align: center;
  line-height: 44px;

  &::before {
    position: absolute;
    left: 14px;
    top: 50%;
    display: block;
    content: "";
    width: 24px;
    height: 24px;
    transform: translateY(-50%);
    background: url(${png}) no-repeat center / 24px 24px;
  }
`;
```

<br/>

- top:0

```jsx
--------Top of Page--------
{element}

------Middle of  Page------

------Bottom of  Page------
```

element의 본 요소가 중앙에 위치해 있지 않은 것을 알 수 있다. 왼쪽 상단이라고 할 수 있는 모서리 부분이 기준점이 되어서 위치가 잡혀있다.

<br/>

- top:50%

```jsx
--------Top of Page--------

------Middle of  Page------
{element}

------Bottom of  Page------
```

역시나 element의 기준점이 element 중앙을 가리키고 있지않다.

<br/>

- transform: translateY(-50%);

```jsx
--------Top of Page--------

{element}-Middle of Page---

------Bottom of  Page------
```

요소 자체 높이의 절반 위로 다시 이동하여 전체 페이지의 중앙에 배치할 수 있다.

<br/>

나의 경우 translate를 설정하지 않고 top요소를 25%만 전해줘도 요소가 중앙배치가 되어진다. 하지만 별로 좋은 방법은 아닌 것 같다 박스요소의 크기에 따라서 위치가 변할 수 있다.

<br/>

> 결론

top: 50%와 transform: translateY(-50%)를 적절히 사용하자.

# 🔗 Reference

- [https://stackoverflow.com/questions/40530101/why-is-translatey-50-needed-to-center-an-element-which-is-at-top-50/40530483](https://stackoverflow.com/questions/40530101/why-is-translatey-50-needed-to-center-an-element-which-is-at-top-50/40530483)
