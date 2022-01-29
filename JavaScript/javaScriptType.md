# 원시 타입에는 어떠한 것들이 있나요 ?

[JavaScript](https://developer.mozilla.org/ko/docs/Glossary/JavaScript)에서 **원시 값**(primitive, 또는 원시 자료형)이란 [객체](https://developer.mozilla.org/ko/docs/Glossary/Object)가 아니면서 [메서드](https://developer.mozilla.org/ko/docs/Glossary/Method)도 가지지 않는 데이터입니다. 원시 값에는 [`string`](https://developer.mozilla.org/ko/docs/Glossary/String), [`number` (enUS)](https://developer.mozilla.org/en-US/docs/Glossary/Number), [`bigint` (enUS)](https://developer.mozilla.org/en-US/docs/Glossary/BigInt), [`boolean`](https://developer.mozilla.org/ko/docs/Glossary/Boolean), [`undefined`](https://developer.mozilla.org/ko/docs/Glossary/undefined), [`symbol`](https://developer.mozilla.org/ko/docs/Glossary/Symbol), 그리고 [`null`](https://developer.mozilla.org/ko/docs/Glossary/Null)이 존재합니다.

`🔗 Reference`

[https://developer.mozilla.org/ko/docs/Glossary/Primitive](https://developer.mozilla.org/ko/docs/Glossary/Primitive)

<br/>

# 참조 타입에는 어떠한 것들이 있나요 ?

자바스크립트에서 원시 타입을 제외한 나머지는 참조타입(객체(Object))이라 할 수 있다. 배열과 객체, 그리고 함수가 대표적이며, 원시타입과 가장 큰 차이점은 변수의 크기가 동적으로 변한다는 것이다. 이러한 특징 때문에 Object의 데이터 자체는 별도의 메모리 공간(heap)에 저장되며, 변수에 할당 시 데이터에 대한 주소 ( 힙(Heap) 메모리의 주소값)가 저장되기 때문에 자바스크립트 엔진이 변수가 가지고 있는 메모리 주소를 이용해서 변수의 값에 접근하게 되는것이다.

`🔗 Reference`

[https://velog.io/@nomadhash/Java-Script-깊은-복사와-얕은-복사](https://velog.io/@nomadhash/Java-Script-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC%EC%99%80-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC)

<br/>

# 원시 래퍼 타입이란 무엇인가요?

## 원시 래퍼 타입

원시 타입을 객체처럼 편리하게 사용하도록 도와준다.

### 원시 래퍼 타입의 종류

- String
- Number
- Boolean

### 원시 래퍼 타입의 특징

원시 타입을 객체처럼 사용하는 순간, 자바스크립트 내부에서 사용하는 데이터의 인스턴스를 만들게 된다. 이렇게 만들어진 객체는 코드를 실행 후 바로 다음 줄에서 파괴된다. 이러한 과정일 **오토박싱** 이라고 한다.

`🔗 Reference`

[https://velog.io/@kero1004/javascript-타입](https://velog.io/@kero1004/javascript-%ED%83%80%EC%9E%85)

# 얕은복사, 깊은복사

> 원시 타입의 불변성

자바스크립트에서 원시 타입 **(string, number, bigint, boolean, undefined, ES6 부터 추가된 symbol)** 은 변수에 할당될 때, 메모리의 고정 크기로 원시 값을 저장하고 해당 저장된 값을 변수가 직접적으로 가리키는 형태를 띈다. 또한 값이 절때 변하지않는 불변성을 갖고있기때문에 때문에 재할당 시 기존 값이 변하는것 처럼 보일지 몰라도 사실 새로운 메모리에 재할당한 값이 저장되고 변수가 가리키는 메모리가 달라졌을 뿐이다.

> 주의해야 할 점

참조 타입의 변수는 실제 데이터가 저장된 주소를 참조하기에 참조(reference) 타입이라고 불리는 것이다. 그렇기에 변수의 복사나 수정 시 참조 여부를 잘 고려해야 한다. 만일 이러한 특성을 고려하지 않은 채 중요한 정보를 담고있는 객체나 배열에 수정 및 복사를 가하게되면 원본 데이터가 예상치 못한 방향 으로 변경될 수 있으므로 항상 이를 고려하자.

`🔗 Reference`

[https://velog.io/@nomadhash/Java-Script-깊은-복사와-얕은-복사](https://velog.io/@nomadhash/Java-Script-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC%EC%99%80-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC)

<br/>

> 깊은 복사 얕은 복사 어떻게 진행하는게 좋을까?

얕은 복사 Shllow Copy

1. Object.assign()
2. 전개연산자

깊은 복사 Deep Copy

1. 재귀함수를 이용한 복사

2. JSON.stringify()

3. 라이브러리 사용 (lodash) 나머지 하나 기억안남

`🔗 Reference`

[https://velog.io/@th0566/Javascript-얕은-복사-깊은-복사](https://velog.io/@th0566/Javascript-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC)
