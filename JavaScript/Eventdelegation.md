# π‘Β μ΄λ²€νΈ μμκ³Ό μ΄λ²€νΈ νΈλ€λ¬

<br/>

# κΈ°μ‘΄ μ΄λ²€νΈ νΈλ€λ¬μ λ§€κ°λ³μλ₯Ό λκΈ°λ λ°©λ² 1

```jsx
<body>
  <ul class="λΆλͺ¨λ°μ€" style="background-color: brown">
    <button class="μμλ²νΌ1">μμ λ²νΌ1</button>
    <button class="μμλ²νΌ2">μμ λ²νΌ2</button>
    <button class="μμλ²νΌ3">μμ λ²νΌ3</button>
  </ul>
</body>;
// <script>
const μμλ²νΌ1 = document.querySelector(".μμλ²νΌ1");

const μ«μ = 12345;

function handleClick(λ§€κ°λ³μ) {
  console.log(λ§€κ°λ³μ);
}
μμλ²νΌ1.addEventListener("click", () => {
  handleClick(μ«μ);
});
// </script>
```

<br/>

- λͺ¨λ  λ²νΌμ μ΄λ²€νΈ μΆκ°νκΈ°

```jsx
<body>
  <ul class="λΆλͺ¨λ°μ€" style="background-color: brown">
    <button class="μμλ²νΌ1">μμ λ²νΌ1</button>
    <button class="μμλ²νΌ2">μμ λ²νΌ2</button>
    <button class="μμλ²νΌ3">μμ λ²νΌ3</button>
  </ul>
</body>;

// <script>
const μμλ²νΌ1 = document.querySelector(".μμλ²νΌ1");
const μμλ²νΌ2 = document.querySelector(".μμλ²νΌ2");
const μμλ²νΌ3 = document.querySelector(".μμλ²νΌ3");

const μ«μ = 12345;
const νμ€νΈ = "νμ€νΈ";
const λΆλ¦¬μΈ = false;

function handleClick(λ§€κ°λ³μ) {
  console.log(λ§€κ°λ³μ);
}
μμλ²νΌ1.addEventListener("click", () => {
  handleClick(μ«μ);
});
μμλ²νΌ2.addEventListener("click", () => {
  handleClick(νμ€νΈ);
});
μμλ²νΌ3.addEventListener("click", () => {
  handleClick(λΆλ¦¬μΈ);
});

// </script>
```

- μ€λ³΅λλ μ½λκ° λ°μνλ€.
- μ½λμ κ°λμ±μ ν΄μΉλ λ¬Έμ κ° λ°μνλ€
- λ§μ λ©λͺ¨λ¦¬ κ³΅κ°μ μ°¨μ§νκ² λλ€.

<br/>

## πΒ  μ΄λ²€νΈ μμμ΄λ?

- μ΄λ²€νΈλ₯Ό μμμμμ νλνλ μ ν΄μ£Όλκ²μ΄ μλ μμ λΆλͺ¨ μμμ μ΄λ²€νΈλ₯Ό νλ² λ±λ‘ ν¨μΌλ‘μ¨ λΆλͺ¨ μμμμ λ±λ‘ν μ΄λ²€νΈκ° μμμμμ μ νλλ κ²μ λ§ν©λλ€.

```jsx
<body>
    <ul class="λΆλͺ¨λ°μ€" style="background-color: brown">
      <button class="μμλ²νΌ1">μμ λ²νΌ1</button>
      <button class="μμλ²νΌ2">μμ λ²νΌ2</button>
      <button class="μμλ²νΌ3">μμ λ²νΌ3</button>
    </ul>
  </body>

  <script>
    const λΆλͺ¨λ°μ€ = document.querySelector(".λΆλͺ¨λ°μ€");

    function handleClick() {
      console.log(" λΉμ μ ν΄λ¦­μ handleClick ν¨μκ° νΈμΆλμμ΅λλ€.");
    }

    λΆλͺ¨λ°μ€.addEventListener("click", () => {
      // handleClick();
      // console.dir(μ΄λ²€νΈκ°μ²΄);
      // console.log(μ΄λ²€νΈκ°μ²΄.currentTarget);
      // console.log(μ΄λ²€νΈκ°μ²΄.target);
      // handleClick(μ΄λ²€νΈκ°μ²΄.target);
    });
  </script>
```

<br/>

> μ΄λ²€νΈ κ°μ²΄λ?

- μ΄λ²€νΈ κ°μ²΄μλ ν΄λΉ ν΄λ¦­ μ΄λ²€νΈκ° λ°μν μμμ λν μ λ³΄μ κ·Έλ¦¬κ³  λ°μν μ΄λ²€νΈμ λνμ¬ μ μ μλ μμ±λ€μ΄ λͺ¨μ¬ μλ κ°μ²΄μλλ€.

<br/>

> μ΄λ²€νΈ μμμ μ₯μ 

- λ§μ μ΄λ²€νΈ νΈλ€λ¬λ₯Ό ν λΉνμ§ μμλ λκΈ° λλ¬Έμ μ΄κΈ°νκ° λ¨μν΄μ§κ³  λ©λͺ¨λ¦¬κ° μ μ½λ©λλ€.
- μμλ₯Ό μΆκ°νκ±°λ μ κ±°ν  λ ν΄λΉ μμμ ν λΉλ νΈλ€λ¬λ₯Ό μΆκ°νκ±°λ μ κ±°ν  νμκ° μκΈ° λλ¬Έμ μ½λκ° μ§§μμ§λλ€.

<br/>

> κ·Έλμ μ΄λ²€νΈ μμμ μνλ©΄ μΈν°λ· μλκ° μ νλλκ±°μΌ?

- λΆλͺ¨λ°μ€μ ν λΉλ νΈλ€λ¬κ° μλ΅ν  νμκ° μλ μ΄λ²€νΈμ΄λ  μλλ  μκ΄μμ΄ λͺ¨λ  μμλ²νΌ μμ λ°μνλ μ΄λ²€νΈμ μλ΅ν΄μΌ νλ―λ‘ CPU μμ λΆνκ° λμ΄λ  μ μμ΅λλ€. κ·Έλ°λ° `μ΄λ° λΆνλ λ¬΄μν λ§ν μμ€μ΄λ―λ‘ μ€μ λ‘λ μ κ³ λ €νμ§ μμ΅λλ€.`

<br/>

# κΈ°μ‘΄ μ΄λ²€νΈ νΈλ€λ¬μ λ§€κ°λ³μλ₯Ό λκΈ°λ λ°©λ² 2

- `onClick`

```jsx
<body>
    <ul class="λΆλͺ¨λ°μ€" style="background-color: brown">
      <button class="μμλ²νΌ1" onclick="handleClick(μ«μ)">μμ λ²νΌ1</button>
      <button class="μμλ²νΌ2" onclick="handleClick(νμ€νΈ)">μμ λ²νΌ2</button>
      <button class="μμλ²νΌ3" onclick="handleClick(λΆλ¦¬μΈ)">μμ λ²νΌ3</button>
    </ul>
  </body>

  <script>

	const μ«μ = 12345
	const νμ€νΈ = "νμ€νΈ"
	const λΆλ¦¬μΈ = false

    function handleClick(λ§€κ°λ³μ) {
      console.log(λ§€κ°λ³μ);
    }
  </script>
```

- HTML λ¬Έμμ μ­ν  ?
- CSS λ¬Έμμ μ­ν  ?
- JavaScript λ¬Έμμ μ­ν  ?

<br/>

# λ¦¬μ‘νΈμμμ μ΄λ²€νΈ νΈλ€λ¬λ μ΄λ»κ² λ§€κ°λ³μλ₯Ό λκΈ°λκ°?

```jsx
function App() {
  const μ«μ = 12345;
  const νμ€νΈ = "νμ€νΈ";
  const λΆλ¦¬μΈ = false;

  const handleClick = (λ§€κ°λ³μ) => {
    console.log(λ§€κ°λ³μ);
  };

  return (
    <>
      <div className="λΆλͺ¨λΈλ">
        <button onClick={() => handleClick(μ«μ)}>μμλ²νΌ1</button>
        <button onClick={() => handleClick(νμ€νΈ)}>μμλ²νΌ2</button>
        <button onClick={() => handleClick(λΆλ¦¬μΈ)}>μμλ²νΌ3</button>
      </div>
    </>
  );
}
```

<br/>

# μ£Όμν  μ 

```jsx
import React from "react";

function App() {
  const μ«μ = 12345;
  const νμ€νΈ = "νμ€νΈ";
  const λΆλ¦¬μΈ = false;

  const handleClick = (λ§€κ°λ³μ) => {
    console.log(λ§€κ°λ³μ);
  };

  return (
    <>
      <div className="λΆλͺ¨λΈλ">
        <button onClick={handleClick(μ«μ)}>μμλ²νΌ1</button>
        <button onClick={handleClick(νμ€νΈ)}>μμλ²νΌ2</button>
        <button onClick={handleClick(λΆλ¦¬μΈ)}>μμλ²νΌ3</button>
      </div>
    </>
  );
}
export default App;
```

<br/>

# πΒ Reference

- [https://ko.javascript.info/event-delegation](https://ko.javascript.info/event-delegation)
