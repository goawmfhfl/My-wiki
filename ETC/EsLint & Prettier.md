# ๐กย Eslint & Prettier

> EsLint๋?

์ฐ๋ฆฌ๊ฐ ๋ฆฌ์กํธ ํ๋ก์ ํธ, ํน์ ๋ค๋ฅธ ์๋ฐ์คํฌ๋ฆฝํธ ํ๋ก์ ํธ๋ฅผ ์งํํ๊ฒ ๋  ๋, ์ฐ๋ฆฌ๋ ๋ฌธ๋ฒ ๊ฒ์ฌ ๋ฐ ๋ ๋์ ์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋ฉ ์คํ์ผ์ ์ํ์ฌ ESLint ๋ผ๋ ๋๊ตฌ๋ฅผ ์ฌ์ฉํ๋ค

<br/>

> EsLint ์ฌ์ฉ์ด์ 

์๋ฅผ๋ค์ด์ const๋ก ๊ฐ์ ์ ์ธํ์ง ์๊ณ  ์ฌ์ฉํ๋ ๊ฒฝ์ฐ ์ฝ๋์ ์คํ์ผ์ ๋ฐ๋ผ์ ์๋ฐ์ดํ๋กค ์ธ๊ฑด์ง ๋ง๊ฑด์ง๋ฅผ ๊ฒฐ์ ํ  ์ ์๋ค ๋ํ ๋ค์ฌ์ฐ๊ธฐ ์ค์ ์ ํตํ์ฌ ๊ณต๋ฐฑ์ ๊ฐฏ์๋ฅผ ์ ํ ์๋ ์๋ค. ESLint๋ฅผ ์ฌ์ฉํ๋ฉด ์ง์ ๋ ์คํ์ผ์ ์ฌ์ฉํ์ง ์์ ๊ฒฝ์ฐ์ ์ฃผ์๋ฅผ ์ค๋ค.

<br/>

> prettier

ESLinst ๋ฅผ ์ฌ์ฉํ๋ฉด ์ฝ๋ฉ ์คํ์ผ์ ์ค์ํ๊ธฐ ์ํ์ฌ ์ฝ๋ฉ ์คํ์ผ๊ณผ ๋ง์ง ์๋๋ค๋ฉด ๊ฒฝ๊ณ ๋ ์๋ฌ๋ฅผ ๋์์ผ๋ก์จ ์ ๋๋ก ๋ ์ฝ๋๋ฅผ ์์ฑ ํ  ์ ์๊ฒ ๋์์ค๋ค. ์ด๋ฐ ์ธ๋ถ ์ค์ ์ ์ ์งํด๊ฐ๋ฉด์, ์ฝ๋๋ฅผ ์๋์ผ๋ก ์ ๋ฆฌํด์ฃผ๋ ๋๊ตฌ๋ ๋ฐ๋ก Prettier ์ด๋ค. ์ปค์คํฐ ๋ง์ด์ง์ ESLint์ ์ฐ๋์ด ๊ฐ๋ฅํ๋ค๋ ์ ์์ ๋ง์ด ์ฌ์ฉํ๋ค

<br/>

> ํ๋ฆฌํฐ์ด ์ค์ 

- json ํ์ผ ๋ง๋ค๊ธฐ

```jsx
npm init -y
```

<br/>

- prettier ํ์ผ

```jsx
/** @type {import('prettier').Options} */
module.exports = {
  singleQuote: false,
  // ๋ฌธ์์ด์ ํ๋ฐ์ดํ๋ก formatting
  semi: true,
  //์ฝ๋ ๋ง์ง๋ง์ ์ธ๋ฏธ์ฝ๋ฅธ์ด ์๊ฒ formatting
  useTabs: false,
  //ํญ์ ์ฌ์ฉ์ ๊ธํ๊ณ  ์คํ์ด์ค๋ฐ ์ฌ์ฉ์ผ๋ก ๋์ฒดํ๊ฒ formatting
  tabWidth: 2,
  // ๋ค์ฌ์ฐ๊ธฐ ๋๋น๋ 2์นธ
  trailingComma: "all",
  // ์์ธํ ์ค๋ช์ ๊ตฌ๊ธ๋ง์ด ์งฑ์ด๊ธดํ๋ ๊ฐ์ฒด๋ ๋ฐฐ์ด ํค:๊ฐ ๋ค์ ํญ์ ์ฝค๋ง๋ฅผ ๋ถํ๋๋ก formatting
  printWidth: 80,
  // ์ฝ๋ ํ์ค์ด maximum 80์นธ
  arrowParens: "avoid",
  // ํ์ดํ ํจ์๊ฐ ํ๋์ ๋งค๊ฐ๋ณ์๋ฅผ ๋ฐ์ ๋ ๊ดํธ๋ฅผ ์๋ตํ๊ฒ formatting
  endOfLine: "auto",
  // windows์ ๋จ๋ 'Delete cr' ์๋ฌ ํด๊ฒฐ
};
```

<br/>

> ํ๋ฆฌํฐ์ด ๋ฐฐํฌํ๊ธฐ

1. ํ์ผ ์์ฑ

```jsx
{
  "name": "jaeyoung-prettier",
  "version": "1.0.0",
  "description": "๋ด๊ฐ์ค์ ํ ํ๋ฆฌํฐ์ด ๋ฐฐํฌํ๊ธฐ",
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

์ด๋ prettier๋ ์์กด์ฑ์ ๊ฐ์ง ์๊ฒํ์ฌ ํจํค์ง๋ฅผ ๋ค์ด๋ฐ์ ํ๋ก์ ํธ์ prettier๋ฅผ ๋ฐ๋ก ์ค์นํจ์ผ๋ก์จ ๋ฒ์ ๊ด๋ฆฌ๋ฅผ ์ฝ๊ฒ ํ  ์ ์๊ฒ ํด์ฃผ์๋ค.

1. [npm ์ฌ์ดํธ](https://www.npmjs.com/)์์ ํ์๊ฐ์์ ํ ํ์ ํด๋น ํ๋ก์ ํธ ํ์ผ์์ login

```jsx
npm login
```

1. ํจํค์ง ๋ฐฐํฌ

```jsx
npm publish
```

1. ํจํค์ง ์ฌ์ฉ

```jsx
npm install jaeyoung-prettier
```

1. ํด๋น prettier ๊ท์น์ ์ ์ฉํ  json์ ์๋์ ๊ฐ์ด ๋ช์

```jsx
"prettier":"jaeyoung-prettier",
```

<br/>

> EsLint ์ค์  ๋ฐ prettier์ ์ฐ๋ํ๊ธฐ

- Eslint ์ค์น

```jsx
npm install -d eslint
```

- eslint์ด๊ธฐ ๊ฐ ์ค์ 

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

> Eslint์ prettier ์ฐ๋

```jsx
npm install prettier-eslint
```

์ ์ฉ ํ์ extendํ์ผ์ plugin์ prettier์ ์ฐ๋์ํจ๋ค.

```jsx
module.exports = {
  env: {
    browser: true,
    es2021: true,
    node: true, // ์๋ฌ ๋ฐฉ์ง ์ํด browswer, node ๋๋ค true
  },
  extends: ["eslint:recommended", "airbnb-base", "plugin:prettier/recommended"],
  parserOptions: {
    ecmaVersion: 13,
    sourceType: "module",
  },
  rules: {
    rules: { "no-unused-vars": "warn" }, // ๊ฒฝ๊ณ  ์์ค์ warn์ผ๋ก ๋ฐ๊ฟ์ฃผ๊ธฐ
  },
};
```

<br/>

> VSCode์์ ์ ์ฉํ๊ธฐ

Extention: prettier ์ค์น

Extention: EsLint ์ค์น

```jsx

1. ctrl + shift + p๋ฅผ ๋๋ฌ ํ๋ ํธ๋ฅผ ์ฐ๋ค.
2. format document with ~
3. config default formatter
4. prettier ์ ํ

ESLint - Setting -> ๊ธฐ๋ณธ ํฌ๋ฉํฐ๋ก ์ง์ ํ์ง ์๊ธฐ
prettier - Setting -> ๊ธฐ๋ณธ ํฌ๋ฉํฐ๋ก ์ง์ ํ๊ธฐ

{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
// vscode์์ ๊ธฐ๋ณธ format์ prettier๋ก ์ค์ 
  "editor.formatOnSave": true,
// ์ ์ฅ์ ์ฝ๋ ์๋ ํฌ๋ฉงํ
}
```

<br/>

# ๐ย Reference

- [https://react-etc.vlpt.us/03.prettier-eslint.html](https://react-etc.vlpt.us/03.prettier-eslint.html)
- [https://younho9.dev/sharing-prettier-config](https://younho9.dev/sharing-prettier-config)
- [https://heropy.blog/2019/01/31/node-js-npm-module-publish/](https://heropy.blog/2019/01/31/node-js-npm-module-publish/)
- [https://sunmon.github.io/vscode-eslint-prettier-setting/](https://sunmon.github.io/vscode-eslint-prettier-setting/)
