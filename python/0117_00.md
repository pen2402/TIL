# Python 기초

## 파이썬 (Python)

- 문법이 간단하고 엄격하지 않음
- 크로스 플랫폼 언어 : 다양한 운영체제에서 실행 가능
- 인터프리터 언어 (Interpreter) : 컴파일 과정 없이 코드 한 줄씩 실행 후 바로 확인 가능
- 객체 지향 프로그래밍 (Object Oriented Programming)
  - 객체(Object) : 숫자, 문자, 클래스 등 값을 가지고 있는 모든 것



## 파이썬 개발환경

### IDLE (Intergrated Development and Learning Environment)

- 파이썬 기본 인터프리터
- 디버깅 및 코드 편집, 반복 실행이 곤란



### Jupyter Lab

- 웹 브라우저 환경에서 코드를 작성할 수 있는 오픈소스
- 데이터 분석 / 머신러닝 / 딥러닝 시 많이 활용 가능(Google colab 등)



## 기초 문법

### 코드 스타일 가이드

- 파이썬에서 제안하는 스타일 가이드 : PEP8
- 기업, 오픈소스 등에서 사용되는 스타일 가이드 : Google Style guide 등



### 들여쓰기(Identation)

- Space Sensitive
- 문장 구분 시 중괄호(`{}`) 대신 사용
- `space` 4번 또는 `tab` 1번
  - 한 코드 안에서는 반드시 한 종류의 들여쓰기 사용



### 변수(Variable)

- 컴퓨터 메모리 어딘가에 저장되어 있는 객체를 참조하기 위해 사용되는 이름
- 할당 연산자(`=`) 를 통해 값을 할당
- `type()` : 변수에 할당된 값의 타입
- `id()` : 변수에 할당된 값(객체)의 고유한 아이덴티티(identity) 값, 메모리 주소



### 변수 할당

- 같은 값을 동시에 할당할 수 있음

  ```python
  x = y = 1
  ```

- 다른 값을 동시에 할당할 수 있음

  ```python
  x, y = 1, 2
  ```




### 식별자(Identifiers)

- 파이썬 객체(변수, 함수, 모듈, 클래스 등)를 식별하는데 사용하는 이름(name)

- 규칙

  - 식별자의 이름은 영문 알파벳, 언더스코어(`_`), 숫자로 구성

  - 첫 글자에 숫자가 올 수 없음

  - 길이 제한이 없고, 대소문자를 구별

  - 예약어 키워드는 사용할 수 없음

    ```python
    False, None, True, __peg_parser__, and, as, assert, async, await, break, class, continue, def, del, elif, else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield
    ```

  - 내장함수, 모듈 등의 이름으로도 만들면 안됨(print 등)



### 사용자 입력

- `input([prompt])`
  - 사용자로부터 값을 즉시 입력 받을 수 있는 내장함수
  - 대괄호 부분에 문자열을 넣으면 입력 시 해당 문자열 출력
  - 반환값은 항상 문자열의 형태로 반환



### 주석(Comment)

- 코드에 대한 설명

  ```python
  # 한 줄 주석
  """여러 줄 주석
  여러 줄 주석"""
  '''여러 줄 주석
  여러 줄 주석'''
  ```

- `"""` 또는 `'''`으로 표현하는 방법은 docstring을 위해 사용

  - docstring : 함수/클래스의 설명을 작성




## 파이썬 자료형

### 자료형 분류

- 불린형(Boolean Type)
- 수치형(Numeric Type)
- 문자열(String Type)
- None Type



### 불린형(Boolean)

- True / False 값을 가진 타입은 bool
- 비교/논리 연산을 수행
- 다음은 모두 False 반환
  - `0`, `0.0`, `[]`, `{}`, `''`, `None`
  - [0]은 True

- `bool()` : 특정 데이터가 True인지 False인지 검증



### 수치형(Numeric Type)

#### 정수(Int)

- 모든 정수 타입은 int
- 매우 큰 수를 나타낼 때 오버플로우가 발생하지 않음
  - 오버플로우(Overflow) : 데이터 타입별로 사용할 수 있는 메모리 크기를 넘어서는 상황
  - Arbitrary precision arithmetic(임의 정밀도 산술)을 통해 가용 메모리들을 활용하여 모든 수 표현
- 진수 표현
  - 2진수 : `0b` + `2진수`
  - 8진수 : `0o` + `8진수`
  - 16진수 : `0x` + `16진수`



#### 실수(Float)

- 정수가 아닌 모든 소수는 float 타입

- 부동소수점

- Floating point rounding error
  - 부동소수점에서 실수 연산 과정에서 발생 가능
  
  - 매우 작은 수보다 작은지 확인하거나 math 모듈 활용
  
    ```python
    abs(a - b) <= 1e-10
    ```
  
    ```python
    import sys
    print(abs(a - b) <= sys.float_info.epsilon)
    ```
  
    ```python
    import math
    math.isclose(a, b)		# 추천하는 방법
    ```



#### 복소수(Complex)

- 실수부와 허수부로 구성된 복소수는 모두 complex 타입
  - 허수부를 j로 표현




### 문자열(String Type)

- 모든 문자는 str 타입

- 문자열은 작은 따옴표나 큰 따옴표를 활용하여 표기

- Immutable : 일부만 변경할 수 없음

- Iterable : 값을 차례대로 반환할 수 있음

- 중첩따옴표(Nested Quotes) : 따옴표 안에 따옴표를 표현하는 경우

  - 작은 따옴표는 큰 따옴표, 큰 따옴표는 작은 따옴표로 문자열 생성

- 삼중따옴표(Triple Quotes) : 작은 따옴표나 큰 따옴표를 삼중으로 사용

  - 여러 줄을 나눠 입력할 때 편리

- Escape sequence : 문자열 내에서 특정 문자나 조작을 위해 역슬래시(`\`)를 활용하여 구분

  - `\n` : 줄바꿈

  - `\t` : 탭

  - `\r` : 캐리지리턴

  - `\0` : 널(Null)

  - `\\` : \
  - `\'` : 단일인용부호( ' )
  - `\"` : 이중인용부호( " )

- String Interpolation

  - 문자열을 변수로 활용하여 만드는 법

  - %-formatting : 대부분 프로그래밍 언어에서 사용

    ```python
    print('Hello, %s' % name)
    print('성적은 %d' % score)
    ```

  - str.format()

    ```python
    print('Hello, {}! 성적은 {}'.format(name, score))
    ```

  - f-strings : python 3.6+에서 사용 가능

    ```python
    print(f'Hello, {name}! 성적은 {score}')
    ```
    
    ```python
    pi = 3.141592
    print(f'원주율은 {pi:.3}. 반지름이 2일 때 원의 넓이는 {pi * 2**2}.')
    ```




### None

- 값이 없음을 표현
- 일반적으로 반환 값이 없는 함수에서 사용하기도 함



## 컨테이너(Container)

- 여러 개의 값을 담을 수 있는 객체로, **서로 다른 자료형을 저장**할 수 있음
- 순서가 있는 데이터(Ordered), 순서가 없는 데이터(Unordered)로 분류
  - 순서 != 정렬
- 시퀀스형
  - 가변형 : 리스트
  - 불변형 : 튜플, 레인지

- 비시퀀스형
  - 가변형 : 세트, 딕셔너리




### 시퀀스형 컨테이너(Sequence Container)

#### 리스트(List)

- 순서를 가지는 0개 이상의 객체를 참조하는 **가변 자료형**
- 항상 대괄호 형태로 출력
- 대괄호 `[]` 또는 `list()`를 통해 생성
- 인덱스로 접근 가능(시퀀스형) : `list[i]`



#### 튜플(Tuple)

- 순서를 가지는 0개 이상의 객체를 참조하는 **불변 자료형**

- 항상 소괄호 형태로 출력

- 소괄호 `()` 또는 `tuple()` 을 통해 생성

- 인덱스로 접근 가능(시퀀스형) : `tuple[i]`

- 단일 항목의 경우 : 값 뒤에 쉼표 붙여야 함

  ```python
  a = 1,
  ```

- 복수 항목의 경우 : 마지막 항목 뒤 쉼표 불필요

  ```python
  b = 1, 2, 3
  ```

- 튜플 대입 : 우변의 값을 좌변의 변수에 한번에 할당하는 과정
  - 함수에서 복수의 값을 반환하는 경우에도 활용



#### 레인지(Range)

- 숫자의 시퀀스를 나타내기 위해 사용
  - 기본형(`range(n)`) : 0부터 n-1까지의 숫자 시퀀스
  - 범위 지정(`range(n, m)`) : n부터 m-1까지의 숫자 시퀀스
  - 범위 및 스텝 지정(`range(n, m, s)`) : n부터 m-1까지 s만큼 증가시킨 숫자의 시퀀스



#### 패킹/언패킹(Packing/Unpacking)

- 모든 시퀀스형(리스트, 튜플 등)은 패킹/언패킹 연산자(`*`)를 사용해 객체의 패킹/언패킹 가능

- 패킹

  - 대입문 좌변 변수에 위치

  - 리스트 형태로 대입

  - 우변의 객체 수가 좌변의 변수 수보다 많을 경우 객체를 순서대로 대입

  - 나머지 항목들은 모두 연산자 표시된 변수에 리스트로 대입

    ```python
    x, *y = 1, 2, 3, 4		# x = 1, y = [2, 3, 4]
    ```

- 언패킹

  - argument 이름이 `*`로 시작하는 경우, argument unpacking이라 함
  - 튜플 형태로 대입

- 산술연산자와 구분

  - `*`가 대입식 좌측에 위치하는 경우 또는 단항 연산자로 사용되는 경우 : **패킹/언패킹 연산자**
  - `*`가 이항연산자로 사용되는 경우 : **산술 연산자**



### 비시퀀스형 컨테이너(Associative Container)

#### 셋(Set)

- 중복과 순서 없이 0개 이상의 해시 가능한(immutable) 객체를 참조하는 **가변 자료형**
- 수학에서의 집합과 동일한 구조를 가짐
- 중괄호(`{}`) 또는 `set()`을 통해 생성
- 셋을 활용해 중복된 값을 쉽게 제거할 수 있음
  - 순서가 무시되므로 순서가 중요한 경우 사용할 수 없음




#### 딕셔너리(Dictionary)

- 순서 없이 키-값(key-value) 쌍으로 이뤄진 객체를 참조하는 자료형
- 키(Key) : 해시 가능한 불변 자료형만 가능
- 값(Values) : 어떠한 형태든 관계 없이 설정 가능
- 중괄호(`{}`) 또는 `dict()`을 통해 생성



#### 형 변환(Typecasting)

- 암시적 형 변환(Implicit) : 사용자가 의도하지 않고 파이썬 내부적으로 자료형을 변환
- 명시적 형 변환(Explicit) : 사용자가 특정 함수를 활용하여 의도적으로 자료형을 변환



#### 컨테이너 형 변환(Container Typecasting)

|                | string |     list      |     tuple     | range |      set      | dictionary |
| :------------: | :----: | :-----------: | :-----------: | :---: | :-----------: | :--------: |
|   **string**   |        |       O       |       O       |   X   |       O       |     X      |
|    **list**    |   O    |               |       O       |   X   |       O       |     X      |
|   **tuple**    |   O    |       O       |               |   X   |       O       |     X      |
|   **range**    |   O    |       O       |       O       |       |       O       |     X      |
|    **set**     |   O    |       O       |       O       |   X   |               |     X      |
| **dictionary** |   O    | O<br/>(key만) | O<br/>(key만) |   X   | O<br/>(key만) |            |



#### 연산자(Operator)

- 산술 연산자(Arithmetic Operator)
  - `+` : 덧셈
  - `-` : 뺄셈
  - `*` : 곱셈
  - `/` : 나눗셈
  - `//`  : 몫
  - `%` : 나머지
  - `**` : 거듭제곱
- 비교 연산자 : 값을 비교하며 True / False 값 반환
  - `<` : 미만
  - `<=` : 이하
  - `>` : 초과
  - `>=` : 이상
  - `==` : 같음
  - `!=` : 같지 않음
  - `is` : 객체 아이덴티티(OOP)
  - `is not` : 객체 아이덴티티가 아닌 경우
- 논리 연산자(Logical Operator)
  - A `and` B : A와 B 모두 True면 True
  - A `or` B : A와 B 모두 False면 False
  - `Not` : True를 False로, False를 True로
  - 결과가 확실한 경우 두번째 값은 확인하지 않고 첫번째 값 반환
  - `and` : 첫 번째 값 False인 경우 무조건 False로 첫 번째 값 반환, True인 경우 두 번째 값 반환
  - `or` : 첫 번째 값 True인 경우 무조건 True로 첫 번째 값 반환, False인 경우 두 번째 값 반환
- 복합 연산자(In-Place Operator)
  - 복합 연산자는 연산과 대입이 함께 이뤄짐(`+=` 등)

- 식별 연산자(Identity Operator)
  - `is` 연산자를 통해 동일한 객체인지 확인 가능
- 멤버십 연산자(Membership Operator)
  - 시퀀스 포함 여부 확인(`in`, `not in`)
- 시퀀스형 연산자(Sequence Type Operator)
  - 산술 연산자(`+`) : 시퀀스 간 연결(concatenation)
  - 반복 연산자(`*`) : 시퀀스를 반복
- 인덱싱(Indexing) : 시퀀스의 특정 인덱스 값에 접근
  - 해당 인덱스가 없는 경우 IndexError
- 슬라이싱(Slicing) : 시퀀스를 특정 단위로 슬라이싱
  - `[n:m]`
  - `[n:m:s]`

- set 연산자
  - `|` : 합집합
  - `&` : 교집합
  - `-` : 여집합
  - `^` : 대칭차
- 연산자 우선 순위
  - `()`
  - Slicing
  - Indexing
  - `**`
  - 단항 연산자(`+`, `-`)
  - 산술 연산자(`*`, `/`, `%`)
  - 산술 연산자(`+`, `-`)
  - 비교 연산자(`in`, `is`)
  - `not`
  - `and`
  - `or`



## 파이썬 프로그램 구성 단위

- 식별자(Identifier) : 변수, 함수, 클래스 등 프로그램이 실행되는 동안 다양한 값을 가질 수 있는 이름
- 리터럴(Literal) : 읽혀지는 대로 쓰여있는 값 그 자체
- 표현식(Expression) : 새로운 데이터 값을 생성하거나 계산하는 코드 조각(값)
  - `a = 10`과 같은 할당은 명령으로 표현식이 아닌 문장
  - if-else, 함수 호출 자체는 표현식
- 문장(Statement) : 특정 작업을 수행하는 최소한의 코드 단위
- 함수(Function) : 특정 명령을 수행하는 함수 묶음
- 모듈(Module) : 함수/클래스의 모음 또는 하나의 프로그램을 구성하는 단위
- 패키지(Package) : 프로그램(실행하기 위한 것)과 모듈(불러와 사용하기 위한 것) 묶음
- 라이브러리(Library) : 패키지 모음