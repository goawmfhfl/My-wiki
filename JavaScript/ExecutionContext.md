# 💡 ExecutionContext

자바스크립트의 코드들이 실행되기 위한 환경이다. 전역컨텍스트, 함수 컨텍스트 2가지가 존재한다
전역컨텍스트를 하나 생성 후에 함수를 호출할 떄마다 함수 컨텍스트가 생성이 됩니다.
컨텍스트 생성시에는 변수객체, 스코프체인, this가 생성이 됩니다.
컨텍스트가 생성된 후 함수가 실행되는데 사용되는 변수들은 변수 객체 안에서 값을 찾고 없다면 스코프 체인을 따라가서 올라가면서 찾는다.
정리하자면 실행컨텍스트는 자바스크립트의 코드가 실행되는 데 필요한 변수객체, 스코프체인, this의 정보를 담고 있는 곳이다.

<br/>

# 🔗 Reference

- https://poiemaweb.com/js-execution-context
