# 변수와 타입

## 변수

- 변수
  - 값을 저장할 수 있는 메모리의 특정 번지에 붙이는 이름
  - 하나의 변수에 하나의 값만 저장할 수 있음
  - 변수에 값을 지정하면 JVM이 메모리에 알아서 저장

### 변수 선언

```java
int age;			// 정수(int)형 변수 age 선언
double value;		// 실수(double)형 변수 value 선언

int x, y, z;		// 같은 타입의 변수는 콤마(,)로 한번에 선언 가능
```

- 타입
  - 변수에 저장되는 값의 종류와 범위를 결정짓는 요소
- 변수명 작성 규칙
  - 문자나 숫자, 특수문자 `$`, `_`만 사용이 가능하고, 첫 문자는 숫자로 시작할 수 없음(필수)
    - 가능 : `price`, `$price`, `_companyName`
    - 불가능 : `1v`, `@speed`, `$#value`
  - 영어 대소문자 구분(필수)
  - 자바 예약어 사용할 수 없음(필수)
    - 예약어로 변수 선언 시 컴파일 에러 발생
    - 예약어 : 해당 프로그래밍 언어에서 의미를 갖고 사용되는 단어
  - 카멜 케이스(관례)
    - 첫 문자는 영어 소문자로 시작하되, 다른 단어가 붙을 경우 해당 단어의 첫 문자로 대문자로 함
  - 문자 수 길이 제한 없음
  - 한글을 포함하지 않는 것이 좋으며, 어떤 값을 저장하는지 쉽게 파악할 수 있는 이름으로 짓는 것이 좋음
- 예약어
  - 기본 타입
    - `boolean`, `byte`, `char`, `short`, `int`, `long`, `float`, `double`
  - 접근 제한자
    - `private`, `protected`, `public`
  - 클래스 관련
    - `class`, `abstract`, `interface`, `extends`, `implements`, `enum`
  - 객체 관련
    - `new`, `instanceof`, `this`, `super`, `null`
  - 메소드 관련
    - `void`, `return`
  - 제어문 관련
    - `if`, `else`, `switch`, `case`, `default`, `for`, `do`, `while`, `break`, `continue`
  - 논리값
    - `true`, `false`
  - 예외 처리 관련
    - `try`, `catch`, `finally`, `throw`, `throws`
  - 기타
    - `package`, `import`, `synchronized`, `final`, `static`

### 값 저장

- 대입 연산자(`=`)

  - 변수에 값을 저장할 때에는 대입 연산자 사용

    ```java
    int score;			// 변수 선언
    score = 90;			// 변수 초기화
    
    int score = 90;		// 변수 선언과 동시에 초기화
    ```

    - 변수 선언 : 저장되는 값의 종류와 변수 이름을 언급하는 것
    - 변수 초기화 : 변수에 최초로 값이 저장되어 변수가 생성되는 것
      - 초기값 : 변수에 최초로 저장된 값

    ```java
    int value;					// 변수 선언
    int result = value + 10;	// 컴파일 에러 발생
    ```

    - 초기화 되지 않은 변수 사용 시 컴파일 에러 발생

### 변수 사용

- 출력문이나 연산식 내부에서 변수에 저장된 값을 출력하거나 연산할 때 사용

```java
int hour = 3;
int minute = 5;
int totalMinute = (hour * 60) + minute;		// 각각의 변수에 저장된 값으로 대치
```

```java
int x = 10;
int y = x;		// 변수 x에 저장된 값을 변수 y에 복사(저장)
```

- 변수 값 교환

  ```java
  int x = 3;
  int y = 5;
  int temp = x;
  x = y;
  y = temp;			// x: 5, y: 3
  ```

### 변수 사용 범위

- 로컬 변수(local variable) : 메소드 블록 내에서 선언된 변수
- 변수 선언은 블록 내 어디에서든 할 수 있으나 변수 사용은 자신이 선언된 블록 내부에서만 사용할 수 있음
- 변수 선언 시 해당 변수를 어떤 범위에서 사용될 것인지 고려
  - 메소드 블록 전체에서 사용하려면 메소드 블록 첫머리에서 선언
  - 특정 블록 내부에서만 사용된다면 해당 블록 내에 선언

```java
int v1 = 15;
if (v1 > 10) {
    int v2;
    v2 = v1 - 10;
}
int v3 = v1 + v2 + 5;		// 컴파일 에러
```

- 변수가 선언된 블록 외부에서 해당 변수 사용 시 컴파일 에러 발생



## 기본 타입

- 정수 타입
  - `byte`, `char`, `short`, `int`, `long`
- 실수 타입
  - `float`, `double`
- 논리 타입
  - `boolean`

### 정수 타입

- `byte`
  - 1byte(8bit)
  - -128 ~ 127
- `short`
  - 2byte(16bit)
  - -32,768 ~ 32,767
- `char`
  - 2byte(16bit)
  - 0 ~ 65,535(유니코드)
- `int`
  - 4byte(32bit)
  - -2,147,483,648 ~ 2,147,483,647
- `long`
  - 8byte(64bit)
  - -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807
- 정수 리터럴(literal)
  - 소스 코드에서 프로그래머에 의해 직접 입력된 값
  - 기본적으로 `int` 타입으로 간주
  - 자바가 정수로 인식하는 리터럴
    - 2진수
      - `0b` 또는 `0B`로 시작하고 0과 1로 구성
      - `0b1011`
    - 8진수
      - 0으로 시작하고 0~7의 숫자로 구성
      - `0206`
    - 10진수
      - 소수점이 없는 0~9의 숫자로 구성
      - `365`
    - 16진수
      - `0x` 또는 `0X`로 시작하고 0~9의 숫자와 A~F 또는 a~f로 구성
      - `0xB3`

```java
byte var = 128;			// 컴파일 에러
```

- byte 타입 변수에 허용 범위를 초과한 값 대입 시 컴파일 에러 발생

- 기본적으로 컴파일러는 정수 리터럴을 `int` 타입으로 간주

  - 허용 범위 초과 시 리터럴 뒤에 대문자 `L`을 붙여 컴파일러에 `long` 타입임을 알려야 함

    ```java
    long balance = 30000000000;		// 컴파일 에러
    long balance = 30000000000L;
    ```

    - 소문자 `l`도 가능하나 숫자 `1`과 혼동되므로 대문자 `L` 권장

#### char 타입

- 문자 리터럴
  - 작은따옴표(`'`)로 감싼 하나의 문자
- 유니코드로 변환되어 저장
  - 유니코드는 정수이므로 `char`도 정수 타입에 속함
  - `char` 타입 변수에 저장하면 문자로 매핑되어 출력
  - `int` 타입 변수에 저장하면 유니코드 자체가 출력

#### String 타입

- 문자열 리터럴

  - 큰따옴표(`"`)로 감싼 문자들

- `String` 타입은 기본 타입이 아닌 클래스 타입

- 문자열 비교 시 `equals()` 메소드 사용

  ```java
  String str = "문자열"
  boolean result = str.equals("문자열")
  ```

- 이스케이프(escape) 문자

  - 문자열 내부에 역슬래시(`\`)가 붙은 문자

  - 문자열 내부에 특정 문자를 포함시킬 수 있음

    ```java
    String str = "나는 \"자바\"를 좋아합니다.";		// 나는 "자바"를 좋아합니다.
    ```

  - `\t`
    - 탭만큼 띄움
  - `\n`
    - 줄 바꿈(라인 피드)
  - `\r`
    - 캐리지리턴
  - `\"`
    - 큰따옴표(`"`) 출력
  - `\'`
    - 작은따옴표(`'`) 출력
  - `\\`
    - 역슬래시(`\`) 출력
  - `\u<16진수>`
    - 16진수 유니코드에 해당하는 문자 출력

### 실수 타입

- `float`
  - 4byte(32bit)
- `double`
  - 8byte(64bit)
- 숫자 리터럴
  - 소수점이 있는 숫자
    - `0.25`
  - 알파벳 소문자 `e` 또는 대문자 `E`가 포함된 숫자
    - `5e2` = 500.0
    - `0.12e-2` = 0.0012

```java
float var = 3.14;		// 컴파일 에러
double var = 3.14;
```

- 실수 리터럴을 `float` 타입 변수에 저장 시 컴파일 에러 발생

  - 자바는 기본적으로 실수 리터럴을 `double` 타입으로 해석

  - 실수 리터럴 뒤에 소문자 `f`나 대문자 `F`를 붙여 컴파일러에게 `float` 타입임을 알림

    ```java
    float var = 3.14f;
    ```

- 메모리에 여유가 있고 특별한 이유가 없는 한 실수 리터럴 저장 시 `double` 타입 사용 권장

  - `float` 타입보다 `double` 타입이 허용하는 소수점 이하 자리가 더 크므로 정밀도가 더 높음

### 논리 타입

- 논리 리터럴
  - 참과 거짓을 의미하는 `true`와 `false`



## 타입 변환

### 자동 타입 변환

- 값의 허용 범위가 작은 타입이 허용 범위가 큰 타입으로 저장될 때 발생

```
byte < short < int < long < float < double
```

- `char` 타입이 `int` 타입으로 자동 타입 변환되면 유니코드 값이 저장됨

- 예외

  ```java
  byte byteValue = 65;
  char charValue = byteValue;			// 컴파일 에러
  ```

  - `char` 타입은 음수를 포함하지 않기 때문에 `byte` 타입은 `char` 타입으로 자동 타입 변환될 수 없음

### 강제 타입 변환

- 큰 허용 범위 타입을 작은 허용 범위 타입으로 강제로 나눠서 저장하는 것

```java
int intValue = 10;
byte byteValue = (byte) intValue;		// 강제 타입 변환
```

- 실수 타입을 정수 타입으로 강제 타입 변환 시 소수점 이하 부분은 버려지고 정수 부분만 저장됨

### 정수 연산에서의 자동 타입 변환

- 정수 연산식에서 두 피연산자 중 허용 범위가 큰 타입으로 자동 타입 변환되어 연산 수행

```java
byte x = 10;
byte y = 20;
byte result = x + y;		// 컴파일 에러
int result = x + y;
```

- `byte`, `short` 타입의 변수가 피연산자로 사용되면 `int` 타입으로 자동 타입 변환되어 연산 수행
  - 정수 연산에 사용되는 변수는 `int` 타입으로 선언하여 타입 변환을 줄여줌으로써 성능 향상

### 실수 연산에서의 자동 타입 변환

- 피연산자 중 하나라도 `double` 타입인 경우 모두 `double` 타입으로 자동 타입 변환되어 연산 수행

### + 연산에서의 문자열 자동 타입 변환

- 피연산자가 모두 숫자인 경우 덧셈 연산 수행

- 피연산자가 문자열일 경우 이후 피연산자는 모두 문자열로 자동 변환되어 문자열 결합 연산 수행

  ```java
  int value = 1 + 2 + 3;
  String str1 = 1 + 2 + "3";		// 33
  String str2 = 1 + "2" + 3;		// 123
  String str2 = "1" + 2 + 3;		// 123
  ```

  - 순차적으로 `+` 연산을 수행하지 않고 우선 연산하려는 경우 해당 부분을 괄호(`()`)로 감싸줌

### 문자열을 기본 타입으로 강제 타입 변환

- `Byte.parseByte(<문자열>)`
  - `String` → `byte`
- `Short.parseShort(<문자열>)`
  - `String` → `short`
- `Integer.parseInt(<문자열>)`
  - `String` → `int`
- `Long.parseLong(<문자열>)`
  - `String` → `long`
- `Float.parseFloat(<문자열>)`
  - `String` → `float`
- `Double.parseDouble(<문자열>)`
  - `String` → `double`
- `Boolean.parseBoolean(<문자열>)`
  - `String` → `boolean`
- `String.valueOf(<기본 타입 값>)`
  - 기본 타입 → `String`

```java
String str = "1a";
int value = Integer.parseInt(str);		// NumberFormatException(숫자 형식 예외)
```

- 숫자가 아닌 알파벳, 특수 문자, 한글 등을 포함하고 있는 문자열을 숫자 타입으로 변환 시 숫자 형식 예외 발생



## 변수와 시스템 입출력

### 모니터로 변수값 출력하기

- `System.out.println(<내용>)`

  - 괄호 안 내용 출력 후 개행

- `System.out.print(<내용>)`

  - 괄호 안 내용 출력

- `System.out.printf(<형식 문자열>, <값 1>, <값 2>, ...)`

  - 괄호 안 첫 번째 문자열 형식대로 내용 출력

  - `% [argument_index$] [flags] [width] [.precision] <변환 문자>`

    - `%`, 변환 문자 외 생략 가능

    - `%`

      - 형식 문자열의 시작

    - `argument_index`

      - 형식 문자열에 포함될 값이 2개 이상일 경우 값의 순번 지정

    - `flags`

      - 빈 자리를 채우는 방법

        ```java
        System.out.printf("%d", 123);		// `123`
        System.out.printf("%6d", 123);		// `   123`
        System.out.printf("%-6d", 123);		// `123   `
        System.out.printf("%06d", 123);		// `000123`
        ```

        - `width` 크기의 자리 중 값이 차지하지 않는 빈 자리를 공백(생략), 0(`0`)으로 채움
        - `-`는 값의 오른쪽을 채움

    - `width`

      - 전체 자릿수

    - `precision`

      - 소수 자릿수

    - 변환 문자

      - 정수(`d`)
      - 실수(`f`)
      - 문자열(`s`)

### 키보드에서 입력된 내용을 변수에 저장하기

- `System.in.read()`
  - 엔터 키가 입력되면 엔터 키를 포함하여 이전에 입력된 키들의 키코드(`int` 타입)들을 하나씩 읽음
  - 2개 이상의 키가 조합된 문자(한글 등)나 입력된 내용을 통 문자열로 읽지 못함

```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);
String inputData = scanner.nextLine();
```

- `scanner.nextLine()`
  - 엔터 키가 입력되면 입력된 모든 내용을 문자열로 읽음