> ViewPage

```jsx
import Button from "./Button";
import styled, { ThemeProvider } from "styled-components";

const ResultButton = () => {
  return (
    <Background>
      <ThemeProvider
        theme={{
          palette: {
            orange: "#F26E22",
            lightOrange: "#FFC7A7",
            gray: "#DBDBDB",

            kakaoOrange: "#F2C94C",
            googleGray: "#767676",
            facebookBlue: "#2D9CDB",
          },
        }}
      >
        <ButtonGroup>
          <Button size="sm" width="100px" color="orange">
            팔로우
          </Button>
          <Button size="sm" width="100px">
            취소
          </Button>
        </ButtonGroup>
        <ButtonGroup>
          {/* 활성화 */}
          <Button size="ms" width="90px" color="orange">
            저장
          </Button>
          {/* 비활성화 */}
          <Button size="ms" width="90px">
            저장
          </Button>
        </ButtonGroup>
        <ButtonGroup>
          {/* 활성화 */}
          <Button size="ms" width="90px" color="orange">
            업로드
          </Button>
          {/* 비 활성화 */}
          <Button size="ms" width="90px" color="lightOrange">
            업로드
          </Button>
        </ButtonGroup>
        <ButtonGroup>
          {/* 활성화 */}
          <Button size="md" width="120px" color="orange">
            팔로우
          </Button>
          {/* 비 활성화 */}
          <Button size="md" width="120px" color="lightOrange">
            팔로우
          </Button>
          <Button size="md" width="120px" color="gray" outline>
            언팔로우
          </Button>
          <Button size="md" width="120px" color="gray" outline>
            프로필 수정
          </Button>
          <Button size="md" width="100px" color="gray" outline>
            상품 등록
          </Button>
        </ButtonGroup>
        <ButtonGroup>
          <Button size="lg" width="322px" color="kakaoOrange" outline>
            카카오톡 계정으로 로그인
          </Button>
          <Button size="lg" width="322px" color="googleGray" outline>
            구글 계정으로 로그인
          </Button>
          <Button size="lg" width="322px" color="facebookBlue" outline>
            페이스북 계정으로 로그인
          </Button>
        </ButtonGroup>
        <ButtonGroup>
          {/* 활성화 */}
          <Button size="lg" width="322px" color="orange">
            감귤마켓 시작하기
          </Button>
          {/* 비 활성화 */}
          <Button size="lg" width="322px" color="lightOrange">
            감귤마켓 시작하기
          </Button>
          <Button size="lg" width="120px" color="orange">
            이전페이지
          </Button>
          <Button size="lg" width="120px" color="orange">
            검색하기
          </Button>
        </ButtonGroup>
      </ThemeProvider>
    </Background>
  );
};
const ButtonGroup = styled.div`
  width: 100%;
  display: flex;
  margin: 10px;
`;
const Background = styled.div`
  background-color: #f1ecec7c;
`;

export default ResultButton;
```

> StyleComponents

```jsx
import styled, { css } from "styled-components";

const sizeMap = {
  lg: {
    height: "44px",
    fontSize: "14px",
    boarderRadius: "44px",
  },
  md: {
    height: "34px",
    fontSize: "14px",
    boarderRadius: "30px",
  },
  ms: {
    height: "32px",
    fontSize: "14px",
    boarderRadius: "32px",
  },
  sm: {
    height: "28px",
    boarderRadius: "28px",
    fontSize: "12px",
  },
};

const sizeStyles = css`
  ${({ size }) => css`
    height: ${sizeMap[size].height};
    border-radius: ${sizeMap[size].boarderRadius};
    font-size: ${sizeMap[size].fontSize};
  `}
`;

const colorStyles = css`
  ${({ theme, color }) => {
    const selected = theme.palette[color];
    return css`
      background: ${selected};
      }
      ${props =>
        props.outline &&
        css`
          color: #767676;
          background: none;
          border: 1px solid ${selected};
        `}
    `;
  }}
`;

const StyledButton = styled.button`
  /* 공통 스타일 */
  width: ${props => props.width || "100px"};
  display: inline-flex;
  align-items: center;
  justify-content: center;
  outline: none;
  border: none;
  color: white;
  font-weight: bold;
  cursor: pointer;

  /* 사이즈 */
  ${sizeStyles}

  /* 컬러 */
  ${colorStyles}

  /* 구분짓기 위함 */
  &+& {
    margin-left: 30px;
  }
`;

function Button({ children, size, width, color, ...rest }) {
  return (
    <StyledButton size={size} width={width} color={color} {...rest}>
      {children}
    </StyledButton>
  );
}

Button.defalutProps = {
  size: "md",
  color: "orange",
};

export default Button;
```
