# 산술과 논리 연산

## ALU(Arithmetic and Logical Unit)

- 구성 요소
  - 가산기
  - 레지스터
    - 누산기(Accumulator)
      - 연산의 중심이 되는 레지스터
      - 연산 결과를 일시적으로 보존
    - 범용 레지스터(GR, General Register)
      - 산술 및 논리 연산, 연산 결과의 임시 보존, 어드레스의 인덱싱 등의 목적에 사용되는 레지스터
      - 주로 고정소수점 연산에 사용
    - 부동소수점 레지스터(Floating Point Register)
      - 소수점이 있는 실수 형태로 수치 데이터를 저장하는 레지스터
    - 상태 레지스터(Status Register)
      - 산술 및 논리 연산 결과로 발생된 carry, zero, overflow 등 CPU 상태를 저장하는 레지스터
    - 시프트 레지스터(Shift Register)
      - 수치 데이터 내용을 좌우로 이동 시킬 수 있는 레지스터
    - 스택 포인터(Stack Pointer)
      - 스택의 현 위치를 지시하는 레지스터
      - 스택은 주로 함수를 호출할 때 인수의 전달 등에 이용
  - 보수기
  - 오버플로 검출기
- 기능
  - 명령을 해독한 디코더의 지시에 따라 레지스터를 사용하면서 산술 연산과 논리 연산 담당
  - 연산 종류
    - 비수치 연산(논리 연산)
      - 단항 연산
        - move
        - complement
        - shift
        - rotate
        - clear
        - increment
        - decrement
      - 이항 연산
        - AND
        - XOR
        - compare
        - 사칙 연산
    - 수치 연산(산술 연산)
      - 정수 표현
        - 언팩 십진법
        - 팩 십진법
        - 고정 소수점 연산
        - 기타 형식 코드 표현
      - 실수 표현
        - 부동 소수점 표현



## 수의 표현 방법

### 문자 데이터의 표현

- 문자 데이터 내부 표시 문제
  - EBCDIC이나 ASCII로 입력하는 컴퓨터에서는 입력된 코드 그대로 기억
  - ASCII로 입력 받는 컴퓨터에서는 이것을 EBCDIC 또는 내부 ASCII로 변환 후 기억
    - 내부 ASCII 코드(USASCII-8)
      - 패리티 비트의 한 비트를 이용해 가나문자, 기타 문자도 표시하는 내부 코드

### 숫자 데이터의 표현

- 2진화 10진 코드
  - 존 형식(Zone Format)
    - 한 바이트에 2진화 10진수 한 자리를 저장하는 방식
    - EBCDIC처럼 존과 수치가 하나의 바이트에 표시되는 방식
    - 문자로서의 숫자 표시이기 때문에 그 자체로서 연산 불가능
  - 팩 형식(Packed Format)
    - 한 바이트에 두 자리의 10진수를 표시하는 방식
    - 최하위 바이트의 하위 4비트를 부호로 사용
    - 수치 연산용으로 입출력은 불가능하며 입출력을 하기 위해서는 존 형식으로 변형해야 함
    - 기억공간이 절약되고 문자 코드로의 변환 용이
    - 계산이 복잡하지 않고 입출력 데이터의 양은 많으나 연산량이 적은 경우(사무 처리 등)에 유리
- 2진수
  - 2진수 체계에서는 어떤 수를 0과 1, 부호 및 소수점으로 표현
  - 컴퓨터가 데이터를 저장하거나 처리하는 과정에서는 0과 1만 사용할 수 있음
  - 고정소수점 표현(Fixed Point Representation)
    - 소수점 위치가 특수한 자리에 고정되어 있는 방식
    - 절대치 표현
      - 비트 수가 n이라면 맨 좌측 비트는 부호 비트, 나머지 n-1개의 비트들은 수의 크기를 나타냄
      - 수의 크기 부분은 부호 없는 정수에 대한 2진수 표현과 같은 방법으로 변환
      - 부호 비트에서 양수는 0, 음수는 1로 표현
      - 0에 대한 표현이 2가지(+0, -0)
    - 1의 보수 표현
      - 어떤 양수 값에 해당하는 2진수의 내용을 0은 1로, 1은 0으로 바꾸어주는 방법
    - 2의 보수 표현
      - 어떤 양수를 1의 보수 형식으로 고친 후 LSB에 해당하는 자릿값에 1을 더함
      - 1의 보수보다 동일한 비트들로 표현할 수 있는 수의 개수가 더 많음(0에 대한 표현 1가지)
    - 비트 확장
      - 절대치 표현의 경우 부호 비트를 맨 좌측 위치로 이동하고 그 외  비트들은 0으로 채움
      - 2의 보수 표현의 경우 확장되는 비트들을 부호 비트와 같은 값으로 채움
  - 부동소수점 표현(Floating Point Representation)
    - 소수부와 지수부를 두는 실수 형태의 데이터를 표현하는 방식
      - 소수점 위치가 부동적
    - 정규화(normalization)
      - 가수부와 지수부를 조정하는 것
    - 정밀도
      - 가수는 정밀도를 결정하고 지수는 표현 가능한 수의 범위를 결정(상충 관계)
      - 단일 정밀도(Single-precision)는 32비트, 복수 정밀도(Double-precision)는 64비트 길이
      - 바이어스된 수(Biased Number)
        -  어떤 수에 바이어스 값이 더해진 수
        - (-) 부호를 가진 지수를 (+) 형태로 나타내기 위해 전체적으로 (+) 방향으로 편향시켜야 함
    - IEEE 754
      - 사용자의 불편 개선과 프로그램 이식성 향상을 위해 제안된 부동소수점 표현에 대한 국제 표준
      - 32비트 단일 정밀도 형식
        - 부호 비트와 지수 8비트를 제외한 23비트가 가수 표현에 사용
        - 가수가 정규화된 형태를 가지며 가수부 최초 비트의 1 생략
          - 정규화된 2진수로 표시할 경우 최초 비트의 숫자는 반드시 1이므로 생략함



## 논리 연산

- 연산에 사용되는 변수가 하나면 유너리(unary) 연산, 둘이면 바이너리(binary) 연산

### AND 연산

- 두 데이터의 같은 위치에 있는 비트들이 모두 1인 경우에는 결과 데이터 비트가 1, 하나라도 0이면 0이 됨
- 마스크 데이터
  - 마스크(mask) : 필요 없는 부분을 지우는 것
  - 수치가 아닌 데이터층에서 필요 없는 부분을 지우고 원하는 부분만을 남겨 놓고자 할 때 사용

### OR 연산

- 두 데이터의 같은 위치에 있는 비트들 중 하나라도 1인 경우 결과 데이터 비트가 1, 모두 0이면 0이 됨
- 선택적 세트 데이터
  - 특정 비트 또는 어느 부분을 1로 세트하고자 할 때 사용

### XOR 연산

- 두 데이터의 같은 위치에 있는 비트들이 서로 다른 값을 가지면 결과 데이터 비트가 1, 같은 값을 가지면 0이 됨
- 선택적 보수 데이터
  - 어큐뮬레이터의 내용을 모두 지우고자 할 때도 사용

### NOT 연산

- 데이터를 비트별로 반전하거나 1의 보수를 얻고자 할 때 사용

### 삽입(insert) 연산

- 새로운 비트 값들을 데이터 단어 내의 특정 위치에 삽입
  - 삽입하고자 하는 비트 위치들에 대해 마스크 연산(AND 연산) 수행
  - 새로 삽입될 비트들과 OR 연산 수행



## 시프트(shift) 연산

### 논리 시프트(Logical Shift)

- 데이터의 모든 비트들이 좌측 혹은 우측의 이웃 비트로 자리를 옮김
- 밀려 나가는 비트는 상실되거나 carry 비트로 들어가고 0의 비트가 새로 들어옴
- 논리 좌측 시프트(Logical Shift-left)
  - 비트들이 왼쪽으로 한 칸씩 이동하며 맨 우측 비트로 0이 들어옴
- 논리 우측 시프트(Logical Shift-right)
  - 비트들이 오른쪽으로 한 칸씩 이동
  - 최상위 비트로 0이 들어오고 최하위 비트는 버림

### 순환 시프트(Circular Shift)

- 데이터의 모든 비트들이 좌측 혹은 우측의 이웃 비트로 자리를 옮김
- 밀려나가는 비트가 반대편 끝으로 되돌아옴
  - 대개의 경우 carry 비트를 통해 순환
  - 외부로부터의 0 입력은 들어오지 않음
- 순환 좌측 시프트(Circular Shift-left)
  - 최상위 비트가 최하위 비트 위치로 이동
- 순환 우측 시프트(Circular Shift-right)
  - 최하위 비트가 최상위 비트 위치로 이동

### 산술 시프트(Arithmetic Shift)

- 레지스터에 저장된 데이터가 부호를 가진 정수인 경우에 부호 비트를 고려하여 수행되는 시프트
  - 부호 비트는 그대로 두고, 수의 크기를 나타내는 비트들만 시프트함
- 산술 좌측 시프트
  - 부호 비트는 유지하고 나머지 비트들이 왼쪽으로 한 칸씩 이동하며 맨 우측 비트로 0이 들어옴
- 산술 우측 시프트
  - 부호 비트는 유지하고 나머지 비트들이 오른쪽으로 한 칸씩 이동
    - 부호 비트의 우측 비트는 부호 비트와 같은 비트로 채워짐



## 산술 연산

### 2의 보수 체계에서의 가산

- 2의 보수로 표현된 두 수를 더한 후 올림수가 발생하는 경우 버림
- 오버플로우(Overflow)
  - 가산 과정에서 수의 표현 범위가 초과되는 경우 결과 값이 틀리는 것
  - 최상위 비트들 및 그 다음 비트들의 가산 과정에서 발생하는 올림수들이 서로 다른 경우에 발생
    - 두 올림수들 간 XOR 연산으로 결과 값이 1이 나오는 경우

### 2의 보수 체계에서의 감산

- 부호 비트를 포함하여 감수에 2의 보수를 취함
  - 감수가 양수면 2의 보수 형태로 된 음수로 바뀌고 음수이면 본래의 2진 형태로 된 양수로 바뀜
    - A - (+B) = A + (-B)
    - A - (-B) = A + (+B)
- 감수에 2의 보수를 취한 후 피감수를 더함
  - 피감수는 본래의 형태를 유지하며 이 가산의 결과는 차를 나타냄
  - 이 차의 부호 비트로 (+), (-)인지, 2진 형태인지 2의 보수 형태인지 결정

### 1의 보수 체계에서의 감산

- 순환 자리 올림
  - 1의 보수 체계의 감산 과정에서 발생된 자리 올림을 감산 결과의 최하위 비트에 더하는 것

### BCD 가산

- 본래의 2진수 가산을 사용해 각 자릿값 위치에 맞는 BCD 코드를 더함
- 합이 9 이하인 곳에서는 수정할 필요가 없으나 9보다 크면 0110(6)의 수정 인자가 합에 더해져야 함