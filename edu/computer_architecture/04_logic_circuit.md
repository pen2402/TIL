# 논리 회로

## 기본 논리 회로

- 게이트(gate)
  
  - 디지털 신호를 나타내기 위해 사용되는 논리회로

### 논리곱(AND) 회로

- 입력이 모두 1의 상태일 때만 출력이 1의 상태가 되고 그 외의 경우 0이 되는 회로

- 연산 기호 : `*`, `∧`, `∩`

### 논리합(OR) 회로

- 입력이 모두 0의 상태일 때만 출력이 0의 상태가 되고 그 외의 경우 1이 되는 회로

- 연산 기호 : `+`, `∨`, `∪`

### 부정(NOT) 회로

- 입력이 0의 상태일 때 출력이 1의 상태가 되고, 입력이 0일 때 출력이 1이 되는 회로

- 인버터(inverter) 회로 또는 보수(complement) 회로라 부름

- 연산 기호 : `´`

### NAND 회로

- AND 게이트 출력단에 인버터를 채용한 회로

- 연산 기호 : `↑`

### NOR 회로

- OR 게이트 출력단에 인버터를 채용한 회로

- 연산 기호 : `↓`

### XOR 회로

- 입력이 서로 다르면 출력이 1의 상태가 되고, 입력이 서로 같으면 출력이 0이 되는 회로

- 배타적 OR 또는 불일치 판정 회로라고도 함

- 적용
  
  - DES(Data Encryption Standard)
    
    - 대칭키 암호로 56비트의 키 사용
    
    - 미국 NBS(National Bureau of Standards, 현재 NIST)에서 국가 표준으로 정함
    
    - 전치(Transposition)와 환자(Substitution)를 반복해서 평문을 암호화
    
    - 안정성이 매우 높아 현대 관용 암호 방식에 사용
  
  - PN(Pseudo Noise) 코드
    
    - 랜덤 잡음과 유사한 특성을 보이나 일정한 규칙을 갖는 코드
    
    - 동일한 코드를 사용하지만 시간 천이(Time Shift)를 통해 서로를 구별

## 불 대수(Boolean Algebra)

- 불 대수
  - 스위칭 대수(Switching Algebra)라고도 부름

### 기본 용어

- 논리 변수(불 변수)
  
  - 논리 관계를 나타내기 위해 논리 대상을 나타내는 변수

- 기본 논리 동작
  
  - 논리곱(AND)
  
  - 논리합(OR)
  
  - 부정(NOT)

- 논리 함수(불 함수), 논리식(불 식)
  
  - 논리 변수들과 논리 기호들로 나타내어진 논리 관계를 표현한 식

### 표현식

- 기본 정리
  
  - `x = 0 혹은 1`
  
  - `0 · 0 = 0`
  
  - `0 + 0 = 0`
  
  - `1 · 1 = 1`
  
  - `0 · 1 = 1 · 0 = 0`
  
  - `0 + 1 = 1 + 0 = 1`

- 표현식
  
  - 교환법칙 : `x + y = y + x`, `xy = yx`
  
  - 결합법칙 : `x + (y + z) = (x + y) + z`, `x(yz) = (xy)z`
  
  - 분배법칙 : `x · (y + z) = xy + xz`, `x + y·z = (x + y)(x + z)`
    
    ```
    (x + y)(x + z)
    = x·x + x·z + y·x + y·z
    = x + x·z + y·x + y·z        # 1·1 = 1, 0·0 = 0, x·x = x
    = x(1 + z + y) + y·z         # z, y 상관없이 1 + z + y = 1이므로
    = x + y·z
    ```
  
  - 항등법칙 : `x + 0 = x`, `x · 1 = x`
  
  - 보수법칙 : `x + x´ = 1`, `xx´ = 0`
  
  - 멱등법칙 : `x + x = x`, `xx = x`
  
  - 유계법칙 : `x + 1 = 1`, `x · 0 = 0`
  
  - 흡수법칙 : `x + xy = x`, `x(x + y) = x`
  
  - 이중보수법칙 : `x´´` = `x`
  
  - 드 모르강의 법칙 : `(x + y)´ = x´y´`, `(xy)´ = x´ + y´`
  
  - 0과 1의 법칙 : `0´ = 1`, `1´ = 0`

- 쌍대성(Duality)
  
  - A에 대한 어떤 정리가 성립하면 B에 대해서도 똑같이 성립하는 성질
  
  - 각 정리는 어느 논리 관계에서 0을 1로, 1을 0으로, +를 ·으로, ·을 +로 치환할 수 있음

## 논리 회로의 간략화

### 논리합 정규형태(Disjunctive Canonical Form)에 의한 방법

- 최소항(Minterm)
  
  - 주어진 변수들을 논리곱으로 결합시킨 항들
  
  - n개의 논리 변수로 2^n개의 최소항을 만들 수 있음

- SOP(Sum of Products)
  
  - 최소항에 의한 논리합의 형식
  
  - 진리표의 결과 중 1로 나오는 항
  
  - SOP 정규형태 : SOP를 정규형태로 표현한 것

### 논리곱 정규형태(Conjunctive Canonical Form)에 의한 방법

- 최대항(Maxterm)
  
  - 주어진 변수들을 논리합으로 결합시킨 항들
  
  - n개의 논리 변수로 2^n개의 최대항을 만들 수 있음

- POS(Product of Sums)
  
  - 최대항에 의한 논리곱의 형식
  
  - 진리표의 결과 중 0으로 나오는 항
  
  - POS 정규형태 : POS를 정규형태로 표현한 것

### 카르노 맵(Karnaugh Map)에 의한 방법

- 경제적인 논리 회로 구성을 위해 도형을 이용해 논리식을 간략화하여 나타내는 방법

- 진리표가 각 입력 상태에 따른 출력을 표시한다면 카르노 맵은 이에 필요한 표시도

- n개의 논리 변수로 표현하는 조합의 수는 2^n가지로 2^n칸짜리 카르노 맵 작성

- 논리식 간략화 순서
  
  - 동일한 출력을 갖는 인접 항을 가능한 2^n개씩 원으로 묶음
  
  - 이들 원은 서로 중복되어도 좋으며, 변화되지 않은 각 변수를 AND로 나타냄
  
  - AND로 표현된 항이 두 개 이상일 경우 이들은 서로 OR로 연결

### 무관(Don't care) 조건

- 카르노 맵의 각 셀 값에 상관없이 동일한 불 함수 값을 갖는 경우

- 카르노 맵에서 d로 표시

- 논리함수를 단순화할 때 1 또는 0 아무 값이나 사용할 수 있고 사용하지 않을 수도 있음

## 조합 회로(Combinational Circuit)

- 조합 회로
  
  - 입력과 출력을 가진 논리 게이트들의 집합으로서 기억능력이 없는 회로
  
  - 입력 값 0과 1의 조합에 의해 출력 값 결정

- 설계 방법
  
  - 입력과 출력 간 관계를 0과 1의 조합으로 나타낸 진리표(Truth Table) 작성
  
  - 진리표로부터 논리식을 이끌고 되도록 이를 간소화
  
  - 논리식을 논리회로로 나타냄

### 반가산기(Half Adder)

- 두 입력에 대해 두 출력의 합과 자리올림수를 만들어내는 회로

- 두 개의 비트를 서로 산술적으로 합하여 합과 자리올림수를 만들어내는 회로

- 설계 절차
  
  - 진리표 작성하여 진리표에서 논리식을 만듦
    
    - Sum of products 방법, Product of sums 방법
  
  - 구한 논리식을 논리회로로 나타냄

### 전가산기(Full Adder)

- 두 입력과 자리올림수를 포함한 총 3개의 입력으로 합과 자리올림수를 구하는 회로

- 설계 절차
  
  - 진리표를 작성하여 진리표에서 논리식을 만듦
    
    - 카르노 맵
  
  - 구한 논리식을 논리회로로 나타냄
    
    - 반가산기 2개와 OR 게이트로 구성

### 디코더 & 인코더

- 디코더(Decoder)
  
  - 코드화된 데이터로부터 정보를 찾아내는 조합 논리회로
  
  - 2진 코드를 해독하여 이에 대응하는 1개의 신호를 출력하는 것
  
  - 사용
    
    - 멀티플렉서 및 디멀티플렉서의 중심이 되고 특정 칩을 선택하는 데 사용
    
    - ROM, RAM과 같은 메모리에서 특정 번지를 선택
    
    - 명령 레지스터의 명령어 해독

- 인코더(Encoder)
  
  - 부호기로 10진수나 8진수를 2진수나 BCD와 같은 코드를 변환시키는 회로

### 멀티플렉서 & 디멀티플렉서

- 멀티플렉서(MUX, Multiplexer)
  
  - 여러 입력을 받아 그 중 선택된 입력을 출력하는 조합회로
    
    - 데이터 선택기(Data Selector)라고도 함
  
  - 선택선의 값으로 특정 입력선의 선택을 제어
  
  - 비트 조합에 의해 입력 선택을 결정하는 n개의 선택선과 2^n개의 입력선 존재

- 디멀티플렉서(DEMUX, Demultiplexer)
  
  - 1개의 입력을 받아 2^n개의 출력 중 하나를 선택하여 정보를 내보내는 조합회로
    
    - 데이터 분배기(Data Distributer)라고도 함
  
  - 하나의 입력선, 2^n개의 출력선, n개의 선택선으로 구성

## 순서 회로(Sequential Circuit)

- 회로의 이전 상태와 현재 상태에 따라 출력 값이 결정되는 회로

- 신호 타이밍에 따른 분류
  
  - 동기 순서 회로(Synchronous Sequential Circuit)
    
    - 각 시간에 순간적으로 들어오는 클록 펄스에 의해 일률적으로 동작 및 제어
  
  - 비동기 순서 회로(Asynchronous Sequential Circuit)
    
    - 시간에 관계없이 입력이 변화하는 순서에 따라 동작
    
    - 펄스가 필요 없고 어떤 시각에도 변화될 수 있음

### 플립플롭(Flip-flop)

- 클록 신호에 의한 특정 시점의 입력을 샘플링하여 출력에 저장하는 동기식 순서 논리소자

- 쌍안정 멀티바이브레이터라고도 함

- 클럭이 변화하는 순간(Edge)에 출력 값 갱신

- 래치
  
  - 클록에 관계없이 언제든지 출력을 변화시키는 비동기식 순서 논리소자
  
  - 클럭 상태가 유지되는 동안 출력 값 갱신

- RS 플립플롭(SR 플립플롭)
  
  - `set`과 `reset`의 두 논리 상태를 갖고 정상 출력과 보수 출력이 나타남

- JK 플립플롭
  
  - RS 플립플롭과 T 플립플롭을 결합하여 R과 S의 입력에 이전 상태 출력을 AND 처리
  
  - RS 플립플롭의 결점을 보완하여 R과 S가 동시에 1이 되는 경우 허용
  
  - 토글(Toggle)
    
    - 클록 펄스 뒤에 현재 출력 상태를 보수 상태로 바꾸는 것

- D 플립플롭
  
  - RS 플립플롭 회로에 NOT 게이트를 연결해 변형한 회로
  
  - 클록 펄스가 인가될 때 입력에 인가되는 신호가 출력에 그대로 나타남
  
  - 지연형으로 정보를 일시적으로 유지하는 래치 회로나 시프트 레지스터 등에 사용

- T 플립플롭
  
  - J와 K를 연결하여 변형한 회로
  
  - 클록 펄스가 들어올 때마다 출력 신호 상태가 바뀜
  
  - 보수(Complement) 플립플롭 또는 토글(Toggle) 플립플롭이라고도 부름

### 레지스터(Register)

- 플립플롭 회로를 여러 개 접속시켜 여러 비트의 데이터를 일시적으로 저장하는 기억장치

### 카운터(Counter)

- 입력 펄스에 따라 그 상태가 미리 정해진 순서대로 바뀌는 레지스터

- 종류
  
  - 동기식 카운터
    
    - 모든 플립플롭이 하나의 공통 클록에 연결되어 동시에 동작
  
  - 비동기식 카운터
    
    - 이전 플립플롭의 출력이 다음 플립플롭의 클록으로 사용하여 동작
    
    - 리플(Ripple) 카운터라고도 함

- 모드 수(Mod Number)
  
  - 카운터가 완전한 하나의 사이클에서 거치는 상태의 총 가짓수
  
  - 리플 카운터에서 플립플롭의 수가 N개일 때 2^N개의 모드 수를 가짐
