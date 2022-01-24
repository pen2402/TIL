# 에러/예외 처리(Error/Exception Handling)

- 디버깅
  - print문 활용
  - 개발 환경(text editor, IDE) 등에서 제공하는 기능 활용
  - Python tutor 활용(단순 파이썬 코드)
- 코드 작성 중
  - 에러 메시지 발생 시
    - 해당 위치를 찾아 메시지 해결
  - 로직 에러 발생 시
    - 해당 위치 파악이 어려워 해결하기 어려움



## 에러와 예외

- 문법 에러(Syntac Error)
  - 프로그램이 실행되지 않음
  - 파일이름, 줄번호, `^` 문자를 통해 파이썬이 코드를 읽어나갈 때(parser) 문제가 발생한 위치 표현
  - 종류
    - Invalid syntax
    - assign to literal
    - EOL(End of Line)
    - EOF(End of File)
- 예외(Exception)
  - 실행 도중 예상치 못한 상황(에러)을 맞이하면 실행을 멈춤
  - 모든 내장 예외는 Exception Class를 상속받아 이뤄짐
  - 사용자 정의 예외를 만들어 관리할 수 있음
  - 종류
    - ZeroDivisionError : 0으로 나누고자 할 때 발생
    - NameError : namespace 상에 이름이 없는 경우
    - TypeError : 타입 불일치, 인자 누락 또는 개수 초과
    - ValueError : 타입은 올바르나 값이 적절하지 않거나 없는 경우
    - IndexError : 인덱스가 존재하지 않거나 범위를 벗어나는 경우
    - KeyError : 해당 키가 존재하지 않는 경우
    - ModuleNotFoundError : 존재하지 않는 모듈을 import하는 경우
    - ImportError : 모듈은 존재하나 존재하지 않는 클래스나 함수를 가져오는 경우
    - KeyboardInterrupt : 임의로 프로그램을 종료한 경우
    - IndentationError : Indentation이 적절하지 않는 경우
  - 파이썬 내장 예외(built-in-exceptions)
    - [파이썬 내장 예외 클래스 계층 구조](https://docs.python.org/ko/3/library/exceptions.html#exception-hierachy)



## 예외처리

- `try`

  - 오류가 발생할 가능성이 있는 코드를 실행
  - 예외가 발생되지 않으면 `except` 없이 실행 종료(반드시 한 개 이상의 except문 필요)

- `except`

  - 예외가 발생하면 except절 실행
  - 예외 상황을 처리하는 코드를 받아서 적절히 조치

- `else`

  - try문에서 예외가 발생하지 않으면 실행

- `finally`

  - 예외 발생 여부와 관계없이 항상 실행

- ```python
  try:
      <명령문>
  except 예외그룹-1 as 변수-1:		# as 키워드로 원본 에러 메시지 사용 가능
      <예외처리 명령문 1>
  except 예외그룹-2 as 변수-2:
      <예외처리 명령문 2>
  finally:						# finally는 선택사항
      <최종 정리문>
  ```



## 에러 발생 시키기

- `raise <표현식>(메시지)`
  - 실제 프로덕션(서비스용) 코드에서 활용
- `assert <표현식>, <메시지>`
  - 특정 조건의 디버깅 용도로 활용
  - `<표현식>`이 `False`인 경우 AssertionError 발생