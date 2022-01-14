# 💡 Eslint & Prettier

> EsLint란?

우리가 리액트 프로젝트, 혹은 다른 자바스크립트 프로젝트를 진행하게 될 때, 우리는 문법 검사 및 더 나은 자바스크립트 코딩 스타일을 위하여 ESLint 라는 도구를 사용한다

<br/>

> EsLint 사용이유

예를들어서 const로 값을 선언하지 않고 사용하는 경우 코드의 스타일에 따라서 쌍따옴표롤 쓸건지 말건지를 결정할 수 있다 또한 들여쓰기 설정을 통하여 공백의 갯수를 정할수도 있다. ESLint를 사용하면 지정된 스타일을 사용하지 않을 경우에 주의를 준다.

<br/>

> prettier

ESLinst 를 사용하면 코딩 스타일을 준수하기 위하여 코딩 스타일과 맞지 않는다면 경고나 에러를 띄움으로써 제대로 된 코드를 작성 할 수 있게 도와준다. 이런 세부 설정을 유지해가면서, 코드를 자동으로 정리해주는 도구는 바로 Prettier 이다. 커스터 마이징와 ESLint와 연동이 가능하다는 점에서 많이 사용한다

<br/>

> 프리티어 설정

- json 파일 만들기

```jsx
npm init -y
```

<br/>

- prettier 파일

```jsx
/** @type {import('prettier').Options} */
module.exports = {
  singleQuote: false,
  // 문자열은 홑따옴표로 formatting
  semi: true,
  //코드 마지막에 세미콜른이 있게 formatting
  useTabs: false,
  //탭의 사용을 금하고 스페이스바 사용으로 대체하게 formatting
  tabWidth: 2,
  // 들여쓰기 너비는 2칸
  trailingComma: "all",
  // 자세한 설명은 구글링이 짱이긴하나 객체나 배열 키:값 뒤에 항상 콤마를 붙히도록 formatting
  printWidth: 80,
  // 코드 한줄이 maximum 80칸
  arrowParens: "avoid",
  // 화살표 함수가 하나의 매개변수를 받을 때 괄호를 생략하게 formatting
  endOfLine: "auto",
  // windows에 뜨는 'Delete cr' 에러 해결
};
```

<br/>

> 프리티어 배포하기

1. 파일 작성

```jsx
{
  "name": "jaeyoung-prettier",
  "version": "1.0.0",
  "description": "내가설정한 프리티어 배포하기",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "jaeyoung",
  "license": "ISC",
  "dependencies": {
    "@types/prettier": "^2.4.3"
  },
  "devDependencies": {
    "prettier": "2.5.1"
  }
}
```

이때 prettier는 의존성을 갖지 않게하여 패키지를 다운받은 프로젝트의 prettier를 따로 설치함으로써 버전관리를 쉽게 할 수 있게 해주었다.

1. [npm 사이트](https://www.npmjs.com/)에서 회원가입을 한 후에 해당 프로젝트 파일에서 login

```jsx
npm login
```

1. 패키지 배포

```jsx
npm publish
```

1. 패키지 사용

```jsx
npm install jaeyoung-prettier
```

1. 해당 prettier 규칙을 적용할 json에 아래와 같이 명시

```jsx
"prettier":"jaeyoung-prettier",
```

<br/>

> EsLint 설정 및 prettier와 연동하기

- Eslint 설치

```jsx
npm install -d eslint
```

- eslint초기 값 설정

```jsx
eslint --init
```

```jsx
To check syntax and find problems
JavaScript modules (import/export)
React
No - typeScript
Browser
json
Yes - eslint-plugin-react@latest
```

<br/>

```jsx
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": ["eslint:recommended", "plugin:react/recommended"],
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": 13,
    "sourceType": "module"
  },
  "plugins": ["react"],
  "rules": {
    "no-unused-vars": "warn"
  }
}
```

<br/>

> Eslint와 prettier 연동

```jsx
npm install prettier-eslint
```

적용 후에 extend파일에 plugin에 prettier와 연동시킨다.

```jsx
module.exports = {
  env: {
    browser: true,
    es2021: true,
    node: true, // 에러 방지 위해 browswer, node 둘다 true
  },
  extends: ["eslint:recommended", "airbnb-base", "plugin:prettier/recommended"],
  parserOptions: {
    ecmaVersion: 13,
    sourceType: "module",
  },
  rules: {
    rules: { "no-unused-vars": "warn" }, // 경고 수준을 warn으로 바꿔주기
  },
};
```

<br/>

> VSCode에서 적용하기

Extention: prettier 설치

Extention: EsLint 설치

```jsx

1. ctrl + shift + p를 눌러 팔레트를 연다.
2. format document with ~
3. config default formatter
4. prettier 선택

ESLint - Setting -> 기본 포메터로 지정하지 않기
prettier - Setting -> 기본 포메터로 지정하기

{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
// vscode에서 기본 format을 prettier로 설정
  "editor.formatOnSave": true,
// 저장시 코드 자동 포멧팅
}
```

<br/>

# 🔗 Reference

- [https://react-etc.vlpt.us/03.prettier-eslint.html](https://react-etc.vlpt.us/03.prettier-eslint.html)
- [https://younho9.dev/sharing-prettier-config](https://younho9.dev/sharing-prettier-config)
- [https://heropy.blog/2019/01/31/node-js-npm-module-publish/](https://heropy.blog/2019/01/31/node-js-npm-module-publish/)
- [https://sunmon.github.io/vscode-eslint-prettier-setting/](https://sunmon.github.io/vscode-eslint-prettier-setting/)
