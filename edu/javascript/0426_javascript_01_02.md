# JavaScript 기초

## 함수

- 참조 타입 중 하나로 function 타입에 속함

- 함수 정의 방법

  - 함수 선언식(function declaration)
  - 함수 표현식(function expression)

- JavaScript의 함수는 일급 객체(First-class citizen)에 해당

  - 일급 객체 조건
    - 변수에 할당 가능
    - 함수의 매개변수로 전달 가능
    - 함수의 반환 값으로 사용 가능

- 함수 선언식

  - 함수의 이름과 함께 정의하는 방식

    ```javascript
    function <함수명>(<매개변수>) {
        <내용>
    }
    ```

- 함수 표현식

  - 함수를 표현식 내에서 정의하는 방식

    - 표현식 : 어떤 하나의 값으로 결정되는 코드의 단위

  - 함수의 이름을 생략하고 익명 함수로 정의 가능

    - 익명 함수는 함수 표현식에서만 가능
    - 기명 함수로 정의하더라도 함수 사용 시 변수명으로 호출해야 함

    ```javascript
    const <변수명> = function (<매개변수>) {
        <내용>
    }
    ```

- 기본 인자(default arguments)

  - 함수 작성 시 `<인자> = <기본값>` 형태로 기본 인자 선언 가능

- 매개변수와 전달 인자 개수 불일치 허용

  - 매개변수보다 전달 인자의 개수가 많을 경우
    - 초과 인자들은 무시

  - 매개변수보다 전달 인자의 개수가 적을 경우
    - `undefined`로 전달

- Rest parameter(`...`)
  - 함수가 정해지지 않은 수의 매개변수를 배열로 받음
    - 파이썬의 가변인자리스트(`*<args>`)와 유사
  - 만약 매개변수에 인자가 넘어오지 않을 경우 빈 배열로 처리

- Spread operator(`...`)
  - 배열 인자 전개하여 전달 가능



## 선언식과 표현식

- 함수 선언식은 익명 함수 사용 불가능, 호이스팅 가능
  - 함수 호출 이후에 함수를 선언해도 동작

- 함수 표현식은 익명 함수 사용 가능, 호이스팅 불가능
  - Airbnb Style Guide 권장 방식
  - 함수 선언 이전에 호출 시 에러 발생
    - 함수 표현식으로 정의된 함수는 변수로 평가되어 변수의 scope 규칙을 따름
    - 함수 표현식을 `var` 키워드로 작성하는 경우 변수가 선언 전 `undefined`로 초기화되어 에러 발생

- 타입은 모두 `function`으로 동일



## Arrow Function

- 화살표 함수
  - 함수를 비교적 간결하게 정의할 수 있는 문법
  - `function` 키워드 생략 가능
  - 함수의 매개변수가 단 하나 뿐이라면 `()`도 생략 가능
  - 함수 몸통이 표현식 하나라면 `{}`와 `return`도 생략 가능
  - 기존 `function` 키워드 사용 방식과의 차이점은 `this` 키워드



## 문자열

- 메서드
  - `.includes(<value>)`
    - 특정 문자열의 존재 여부를 참/거짓으로 반환

  - `.split(<value>)`
    - 문자열을 토큰 기준으로 나눈 배열 반환
    - 인자가 없으면 기존 문자열을 배열에 담아 반환
    - 빈 문자열(`''`)인 경우 각 문자로 나눈 배열 반환

  - `.replace(<from>, <to>)`
    - 해당 문자열을 대상 문자열로 교체하여 반환(해당하는 첫 문자열 하나만 교체)
    - `.replaceAll(<from>, <to>)`
      - 해당 문자열을 대상 문자열로 모두 교체하여 반환

  - `.trim()`
    - 문자열의 좌우 공백(스페이스, 탭, 엔터 등) 제거하여 반환
    - `.trimStart()`
      - 문자열 시작 부분 공백 제거

    - `.trimEnd()`
      - 문자열 끝 부분 공백 제거




## 배열(Arrays)

- 배열
  - 키와 속성들을 담고 있는 참조 타입의 객체(object)
  - 순서를 보장하는 특징이 있음
  - 주로 대괄호를 이용하여 생성하고 0을 포함한 양의 정수 인덱스로 특정 값에 접근 가능
  - 배열의 길이는 `array.length` 형태로 접근 가능
    - 배열의 마지막 원소는 `array.length-1`로 접근
  - spread operator(`...`)를 사용하여 배열 내부에서 배열 전개 가능
    - ES5까지 `.concat()` 메서드 사용
    - 얕은 복사에 활용 가능
- 메서드
  - `.reverse()`
    - 원본 배열의 요소들의 순서를 반대로 정렬
  - `.push(<value>)` & `.pop()`
    - 배열의 가장 뒤에 요소를 추가 또는 제거
  - `.unshift(<value>)` & `.shift()`
    - 배열의 가장 앞에 요소를 추가 또는 제거
  - `.includes(<value>)`
    - 배열에 특정 값이 존재하는지 판별 후 참/거짓 반환
  - `.indexOf(<value>)`
    - 배열에 특정 값이 존재하는지 판별 후 있으면 첫 번째 해당 요소 인덱스 반환
    - 요소가 없을 경우 -1 반환
  - `.join(<separator>)`
    - 배열의 모든 요소를 구분자를 이용하여 연결
    - 구분자 생략 시 쉼표(`,`)를 기본값으로 사용
  - `.forEach(<callback>(<element>[, <index>[, <array>]]))`
    - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
      - 콜백 함수
        - 어떤 함수 내부에서 실행될 목적으로 인자로 넘겨받는 함수
        - 매개변수 구성
          - 배열 요소
          - 배열 요소 인덱스
          - 배열 자체
    - 반환 값이 없음
    - `break`, `continue` 사용 불가능
  - `.map(<callback>(<element>[, <index>[, <array>]]))`
    - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
    - 콜백 함수의 반환 값을 요소로 하는 새로운 배열 반환
    - 기존 배열 전체를 다른 형태로 바꿀 때 유용
  - `.filter(<callback>(<element>[, <index>[, <array>]]))`
    - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
    - 콜백 함수의 반환 값이 참인 요소들만 모아서 새로운 배열 반환
    - 기존 배열의 요소들을 필터링할 때 유용
  - `.reduce(<callback>(<acc>, <element>[, <index>[, <array>]])[, <initialValue>])`
    - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
    - 콜백 함수의 반환 값들을 하나의 값에 누적 후 반환
    - 매개변수
      - `<acc>` : 이전 콜백 함수의 반환 값이 누적되는 변수
      - `<initialValue>` : 최초 콜백 함수 호출 시 `<acc>`에 할당되는 값(기본값 : 배열의 첫 번째 값)
    - 빈 배열의 경우 `<initialValue>`를 제공하지 않으면 에러 발생
  - `.find(<callback>(<element>[, <index>[, <array>]]))`
    - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
    - 콜백 함수의 반환 값이 참이면 조건을 만족하는 첫 번째 요소 반환
    - 찾는 값이 배열에 없으면 `undefined` 반환
  - `.some(<callback>(<element>[, <index>[, <array>]]))`
    - 배열의 요소 중 하나라도 주어진 판별 함수를 통과하면 참을 반환
    - 모든 요소가 통과하지 못하면 거짓 반환
    - 빈 배열은 항상 거짓 반환
  - `every(<callback>(<element>[, <index>[, <array>]]))`
    -  배열의 모든 요소가 주어진 판별 함수를 통과하면 참을 반환
    - 하나의 요소라도 통과하지 못하면 거짓 반환
    - 빈 배열은 항상 참 반환



## 객체

- 객체
  - 객체는 속성의 집합이며 중괄호 내부에 key와 value의 쌍으로 표현
  - key는 문자열 타입만 가능
    - key 이름에 띄어쓰기 등의 구분자가 있으면 따옴표로 묶어서 표현
  - value는 모든 타입(함수 포함) 가능
  - 객체 요소 접근은 점 또는 대괄호로 가능
    - key 이름에 띄어쓰기 같은 구분자가 있으면 대괄호 접근만 가능
- 메서드
  - 어떤 객체의 속성이 참조하는 함수
  - `<객체명>.<메서드명>()`으로 호출 가능
  - 메서드 내부에서는 `this` 키워드가 객체를 의미함
- 객체 관련 ES6 문법
  - 속성명 축약(shorthand)
    - 객체를 정의할 때 key와 할당하는 변수의 이름이 같으면 축약 가능
      - `: <변수명>` 생략 가능
  - 메서드명 축약(shorthand)
    - 메서드 선언 시 function 키워드 생략 가능
      - `: function` 생략 가능
  - 계산된 속성(computed property name)
    - 객체를 정의할 때 key의 이름을 표현식을 이용하여 동적으로 생성 가능
      - `[<변수명>] : <value>` 등
  - 구조 분해 할당(destructing assignment)
    - 배열 또는 객체를 분해하여 속성을 변수에 쉽게 할당할 수 있음
      - `[ <key> ] = <배열명>`
        - 키 개수만큼 인덱스 순으로 할당
      - `{ <key> } = <객체명>`
        - 해당 속성과 key 이름이 같아야 함
    - `<key1>, <key2>, ...` 등 여러 개 동시에 할당 가능
  - Spread operator(`...`)를 사용하여 객체 내부에서 객체 전개 가능
    - ES5까지는 `.assign()` 메서드 사용
    - 얕은 복사에 활용 가능
- JSON(JavaScript Object Notation)
  - key-value쌍의 형태로 데이터를 표기하는 언어 독립적 표준 포맷
  - 자바스크립트의 객체와 유사하게 생겼으나 실제로는 문자열 타입
    - 자바스크립트의 객체로 조작하기 위해서는 parsing 필수
    - 내장 메서드
      - `JSON.parse()` : JSON에서 자바스크립트 객체로 변환
      - `JSON.stringify()` : 자바스크립트 객체에서 JSON으로 변환




## this

- 실행 문맥(execution context)에 따라 다른 대상을 가리킴
  - class 내부의 생성자(constructor) 함수
    - 생성되는 객체를 가리킴(Python의 `self`)
  - 메서드(`<객체명>.<메서드명>()`으로 호출 가능한 함수)
    - 해당 메서드가 소속된 객체를 가리킴
  - 이외의 경우는 모두 최상위 객체(window)를 가리킴
- 화살표 함수
  - 함수 내부의 함수에서 `this` 키워드 사용 시 최상위 객체(window)를 가리킴
    - `.bind(this)` 메서드를 사용하여 내부 함수에서도 접근할 수 있음
  - 화살표 함수를 사용하면 bind 과정 없이 접근 가능



## lodash

- 모듈성, 성능 및 추가 기능을 제공하는 JavaScript 유틸리티 라이브러리
- array, object 등 자료구조를 다룰 때 사용하는 유용하고 간편한 유틸리티 함수들을 제공
  - `reverse()`, `sortBy()`, `range()`, `random()`, `cloneDeep()` 등
- `cloneDeep()`
  - 깊은 복사 함수
  - 자바스크립트에 깊은 복사 관련 내장함수 없음