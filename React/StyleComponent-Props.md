# 💡Props

```jsx
import React from "react";
import styled from "styled-components"; // ✅ 1. 스타일 컴포넌트를 불러와야합니다.
import { InnerBox, OutBox } from "../components/layout"; // 무시하셔도됩니다

// ✅ 2. 현재 페이지를 보기 위해서는 마지막 경로에 /step1이라고 입력하시면 됩니다.

// ✅ 3. 일반적인 컴포넌트입니다. 스타일된 컴포넌트를 활용하는 View의 역할을 하는 컴포넌트입니다.
const Step1 = () => {
  return (
    <OutBox>
      <InnerBox>
        {/* 
      ✅ 3. 스타일컴포넌트를 사용하면 이런식으로 태그옆에 속성값을 넣어줌으로써 요소를 컨트롤 할 수 있습니다.
      백퍼센트 이해안하셔도 됩니다 그냥 이런식으로 쓰이는구나 이해하시면 됩니다. 한번 width를 조절하면서 값입 변경되는것을 확인하시면 됩니다.
       */}
        <StyledButton width={"300px"} hahaha={"300px"}>
          안녕 나는 스타일이 적용된 버튼이야.
        </StyledButton>
      </InnerBox>
    </OutBox>
  );
};

// ✅ 4. 아래 부분은 전형적인 스타일 컴포넌트의 예시입니다.
// 4-1 반드시 CamelCase 규칙에 따라 변수명을 작성해 주셔야합니다.
// 4-2 styled 뒤에는 저희가 평소에 사용하는 html 태그 명을 붙입니다.

const StyledButton = styled.button`
  /* 공통 스타일 */
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  outline: none;
  border: none;
  color: white;
  font-weight: bold;

  // ✅ 5. 저희가 View 컴포넌트에 width값을 넘겨주었을 때 값이 변경되었던 이유입니다.
  // 저희는 태그에 width라는 이름으로 속성값을 일로 전해주었기 때문에 스타일이 변경된 것입니다.
  // 논리연산자 || 는 필수로 알고계셔야 합니다 아래 링크에서 학습하시면 좋습니다.
  // https://ko.javascript.info/logical-operators

  // 300px 넣어준것은 디폴트 값을 설정해 주기 위함입니다.
  width: ${props => props.width || "300px"};
  // 네미잉은 자유롭게 하셔도 됩니다. 하지만 의미를 명확히 표시하는게 좋겠죠?
  height: ${props => props.hahaha || "300px"};

  // 무시하셔도됩니다
  background-color: #123;
  & + & {
    margin-left: 30px;
  }
`;

// ✅ 6 여기 보면 뭔 이상한 컴포넌트가 하나 더 있습니다.
// 이제부터 함수니 뭐니 그냥 무슨 역할을 하는것은 컴포넌트라고 부르겠습니다ㅋㅋㅋ
// 설정을 위한 컴포넌트라고 보시면 됩니다.
// 저희가 이 컴포넌트를 통해서 방금전에 props로 전달받은 값들을 다시 View 컴포넌트에 내뱉습니다.
// 이해가 안가셔도 괜찮습니다. 대신 구조는 익히시면 좋습니다.

function Button({ children, width, ...rest }) {
  return (
    <StyledButton width={width} {...rest}>
      {children}
    </StyledButton>
  );
}

// ✅ 7 여기 보면 뭔 이상한 컴포넌트가 하나 더 있습니다.
// 이건 button 태그에서 사용하는 기본값을 설정하는 것입니다.
// 아까전에 논리연산자를 통해서 기본값을 설정해줬었죠?
// 논리연산자 말고도 Button 컴포넌트의 size, color의 기본값을 설정할 수 있습니다.
// 만약 기본값이 설정되어 있지 않다면 에러가 발생하는걸로 알고 있습니다.

Button.defalutProps = {
  size: "md",
  color: "orange",
};

// ✅ 8 Step1이 끝났습니다. 이제 이 코드를 어디에다 복붙해 두신다음에
// 한번 똑같이 쳐보면서 이해해보시기 바랍니다.
// 그리고 과제가 있습니다. color든 fontsize든 변경을 한 후에 결과값을 변경시켜보세요!
// 건방지게 제가 뭐라고 여러분께 과제를 드리냐마는...도움이되었으면 하는 바람입니다..

export default Step1;
```

# 🔗 Reference

- [https://react.vlpt.us/styling/03-styled-components.html](https://react.vlpt.us/styling/03-styled-components.html)
