# 제어문

## 제어문(Control Statement)

- 파이썬은 기본적으로 위에서 아래로 순차적으로 명령 수행
- 특정 상황에 따라 코드를 선택적으로 실행(분기/조건)하거나
- 계속하여 실행(반복)하는 제어 필요
- 순서도(flow chart)로 표현 가능



## 조건문(Conditional Statement)

### 조건문 기본

- 참/거짓을 판단할 수 있는 조건식과 함께 사용

  ```python
  if <expression == True>:
      # expression 조건이 참인 경우 이곳 코드 실행
  else:
      # expression 조건이 참이 아닌 경우 이곳 코드 실행
  ```

- else는 선택적으로 활용 가능



### 복수 조건문

- 복수의 조건식을 활용할 경우 `elif` 를 활용하여 표현함

  ```python
  if <expression_1>:
      # <expression_1> 조건이 참인 경우 이곳 코드 실행
  elif <expression_2>:
      # 위의 조건이 참이 아니고 <expression_2> 조건이 참인 경우 이곳 코드 실행
  elif <expression_3>:
      # 위의 조건들이 모두 참이 아니고 <expression_3> 조건이 참인 경우 이곳 코드 실행
  else:
      # 위의 조건들이 모두 참이 아닌 경우 이곳 코드 실행
  ```




### 중첩 조건문

- 조건문은 다른 조건문에 중첩되어 사용될 수 있음(들여쓰기 유의)

  ```python
  if <expression_1>:
      # <expression_1> 조건이 참인 경우 이곳 코드 실행
  	if <expression_2>:
      	# <expression_1> 조건이 참이고 <expression_2> 조건이 참인 경우 이곳 코드 실행
  else:
      # <expression_1> 조건이 참이 아닌 경우 이곳 코드 실행



### 조건 표현식(Conditional Expression)

- 일반적으로 조건에 따라 값을 정할 때 활용

- 삼항 연산자(Ternary Operator)라 부르기도 함

  ```python
  value = num if num >= 0 else -num		# num이 음수일 경우 value = -num
  ```



## 반복문

- 특정 조건에 도달할 때까지 계속 반복되는 일련의 문장

### while문

- 조건식이 참인 경우 반복적으로 코드를 실행
- 종료조건이 반드시  필요



### For문

- 시퀀스를 포함한 순회 가능한 객체 요소를 모두 순회

- 딕셔너리는 기본적으로 key를 순회하며, key를 통해 값을 활용

  - `keys()` : Key로 구성된 결과
  - `values()` : value로 구성된 결과
  - `items()` : (Key, value)의 튜플로 구성된 결과

- `enumerate()`

  - 인덱스와 객체를 쌍(index, value)으로 담은 열거형(enumerate) 객체 반환
  - `enumerate(members, start=1)` : index가 0부터 순차적으로 증가(`start` 기본값 : 0)

- List comprehension : 특정한 값을 가진 리스트를 간결하게 생성하는 방법

  ```python
  [num**3 for num in range(1, 4)]		# [<expression> for <변수> in <iterable>]
  							#[<expression> for <변수> in <iterable> if <조건식>]
  ```

- Dictionary Comprehension : 특정한 값을 가진 딕셔너리를 간결하게 생성하는 방법

  ```python
  {num: num**3 for num in range(1, 4)}		# {key: value for <변수> in <iterable>}
  								# {key: value for <변수> in <iterable> if <조건식>}
  ```



### 반복문 제어

- break : 반복문을 종료
- continue : 이후의 코드 블록은 수행하지 않고 다음 반복 수행
- pass : 아무것도 하지 않음
- for-else : 반복문이 끝까지 실행되면 else문 실행(break로 반복문 종료 시 실행되지 않음)