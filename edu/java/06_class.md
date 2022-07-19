## 멤버 변수

- 멤버 변수
  
  - 필드라고도 함
  
  - 객체의 고유 데이터, 부품 객체, 상태 정보를 저장하는 곳
  
  - 클래스 내부(메서드나 생성자 밖)에 선언된 변수
    
    - 지역 변수
      - 메서드나 생성자 내부에 선언된 변수
  
  - 클래스 변수
    
    - 클래스 로딩 시 생성되는 변수
      - 최초 생성 시 메모리에 할당되어 프로그램이 종료되기 전까지 유지
    - 모든 인스턴스가 공통된 값을 공유
    - `static` 키워드로 선언
  
  - 인스턴스 변수
    
    - 인스턴스가 생성될 때마다 생성되는 변수
    - 각 인스턴스마다 메모리에 새로 할당
  
  - 외부 클래스의 멤버 변수 사용 시 우선 해당 클래스 객체를 생성해야 함
  
  - 멤버 변수 선언
    
    ```java
    <타입> <멤버 변수명> [= 초기값];
    ```
  
  - 초기값이 지정되지 않은 멤버 변수는 기본 초기값으로 설정
    
    - 숫자 타입은 `0`(`char`는 빈 공백)
    - 논리 타입은 `false`
    - 참조 타입(배열, 클래스, 인터페이스)은 `null`
  
  - 필드 사용
    
    - Car 클래스
      
      ```java
      public class Car {
          int speed;        // 멤버 변수
          Car() {            // 생성자
              speed = 0;
          }
      }
      ```
    
    - Person 클래스
      
      ```java
      void method() {
          Car myCar = new Car();    // 객체 생성
          myCar.speed = 60;        // 해당 객체 클래스의 멤버 변수 사용
      }
      ```
      
      - 도트(`.`) 연산자는 객체 접근 연산자

## 메서드

### 메서드 선언

```java
<리턴 타입> <메서드명> ([매개변수, ...]) {        // 선언부(메서드 시그니처)
    // 실행 코드(실행 블록)
}
```

- 리턴 타입
  
  - 리턴값의 타입
    - 리턴값 : 메서드 실행 후의 결과값
  - 리턴값이 있는 경우 선언부에 명시되어야 함
  - 리턴값이 없는 경우 `void` 키워드 작성

- 메서드명
  
  - 숫자로 시작하거나 `$`, `_`를 제외한 특수 문자 사용 불가
  - 카멜 케이스(관례)
  - 어떤 기능을 수행하는지 쉽게 파악할 수 있도록 작성 권장

- 매개변수
  
  - 메서드가 실행할 때 필요한 데이터를 외부로부터 받는 변수
    
    - 인자 : 메서드 호출 시 전달되는 실제 값
  
  - 인자는 매개변수의 타입과 부합되어야 함
    
    ```java
    double divide(int x, int y) {
        double result = x/y;
        return result;
    }
    
    byte b1 = 10;
    byte b2 = 20;
    double result = divide(b1, b2);
    ```
    
    - `byte`는 `int`로 자동 타입 변환되므로 컴파일 에러가 발생하지 않음

- 매개변수의 개수를 모를 경우
  
  ```java
  int sum1(int[] values) { ... }
  
  int result = sum1(new int[] { 1, 2, 3, 4, 5 });
  ```
  
  - 메서드 호출 시 배열을 넘김으로써 배열의 항목 값들을 모두 전달할 수 있음
    - 배열 항목 수는 호출 시 결정
  
  ```java
  int sum2(int ... values) { ... }
  
  int result1 = sum2(1, 2, 3, 4, 5);
  int result2 = sum2(new int[] { 1, 2, 3, 4, 5 });
  ```
  
  - `...` 키워드를 사용하여 가변 매개변수로 선언
  - 메서드 호출 시 넘겨받은 값의 수에 따라 자동으로 배열이 생성되어 해당 값들을 인자로 사용
  - 배열을 직접 인자로 넘길 수도 있음
  
  ```java
  int sum3(String name, int ... values) { ... }
  ```
  
  - 가변 매개변수를 다른 매개변수와 함께 사용하는 경우 가변 매개변수는 마지막에 위치

### return문

- 리턴값이 있는 메서드
  
  - 리턴 타입이 있는 메서드는 반드시 return문을 사용하여 리턴값을 지정해야 함
    - return문이 없는 경우 컴파일 에러 발생
  - return문이 실행되면 메서드는 즉시 종료
    - 이후의 실행문은 실행되지 않으며, 실행문이 오는 경우 `Unreachable code` 컴파일 에러 발생

- 리턴값이 없는 메서드
  
  - 리턴값이 없는 메서드는 리턴 타입으로 `void` 사용
  
  - `void`로 선언된 메서드에서도 return문 사용할 수 있음
    
    ```java
    return;
    ```
    
    - 메서드 실행을 강제 종료

### 메서드 호출

- 객체 내부에서 호출
  
  ```java
  <메서드명>([인자, ...]);                        // 메서드 호출
  <타입> <변수명> = <메서드명>([인자, ...]);        // 메서드 호출하여 변수에 리턴값 저장
  ```
  
  - 메서드가 매개변수를 갖고 있는 경우 타입과 수에 맞게 인자 제공하여 호출

- 객체 외부에서 호출
  
  ```java
  <클래스명> <참조변수명> = new <클래스명>([인자, ...]);
  <참조변수명>.<메서드명>([인자, ...]);                        // 리턴값이 없거나 받지 않을 경우
  <타입> <변수명> = <참조변수명>.<메서드명>([인자, ...]);        // 리턴값이 있고 받을 경우
  ```
  
  - 외부 클래스에서 메서드 호출 시 우선 해당 클래스로부터 객체를 생성해야 함
    - 메서드는 객체에 소속된 멤버로 객체가 전제되어야 함

### 메서드 오버로딩

- 오버로딩(Overloading)
  
  - 클래스 내에 같은 이름의 메서드를 여러 개 선언하는 것
  
  - 매개 변수 타입, 개수, 순서 중 하나가 달라야 함
    
    ```java
    String func(int a, char b) { ... }
    String func(char a, int b) { ... }    // 순서가 다르므로 에러 발생하지 않음
    ```
    
    ```java
    int plus(int x, int y) { ... }
    int plus(int y, int x) { ... }    // 매개변수 이름만 다르므로 에러 발생
    ```
    
    - 모두 같을 경우 매개변수 이름이 다르더라도 메서드 오버로딩이 아님
    
    - 리턴 타입만 다른 경우도 오버로딩이 아님
    
    - 오버로딩이 아닌 경우 컴파일 에러 발생
  
  - 매개값을 다양하게 받아 처리할 수 있도록 하기 위함
    
    ```java
    int plus(int x, int y) {
        int result = x + y;
        return result;
    }
    
    double plus(double x, double y) {
        double result = x + y;
        return result;
    }
    ```
    
    - `double` 타입의 값을 처리하기 위해 `plus()` 메서드 오버로딩
  
  - 오버로딩된 메서드를 호출할 경우 JVM은 인자 값의 타입을 보고 메서드를 선택
    
    - 매개변수 타입과 일치하지 않을 경우 자동 타입 변환이 가능한지 검사
  
  ```java
  String concat(String delim, String ... args) {
      String result = "";
      for (String str : args) {
          result += str + delim;
      }
      return result
  }
  
  String concat(String ... args) {
      return concat("", args);
  }
  ```
  
  - 가변 매개변수를 JVM에서 구분하지 못해 컴파일 에러가 발생할 수 있으므로 주의

- 장점
  
  - 하나의 이름으로 여러 기능을 구현할 수 있음
  - 메서드 이름 절약하고 가독성을 높임

## 인스턴스 멤버와 정적 멤버

### 인스턴스 멤버와 this

- 인스턴스 멤버
  
  - 객체(인스턴스)를 생성한 후 사용할 수 있는 멤버 변수(인스턴스 멤버 변수)와 메서드(인스턴스 메서드)

- `this`
  
  - 객체 내부에서 인스턴스 멤버에 접근하기 위해 사용되는 키워드
  
  - 주로 생성자와 메서드의 매개변수 이름이 멤버 변수와 같을 때 인스턴스 멤버임을 명시하고자 사용
    
    ```java
    public class Car  {
        String model;
        Car(String model) {                    // 생성자
            this.model = model;
        }
        void setModel(String model) {        // 메서드
            this.model = model;
        }
    }
    ```

### 클래스 멤버(정적 멤버)와 static

- 클래스 멤버(정적 멤버)
  
  - 클래스에 고정되어 객체를 생성 없이 사용할 수 있는 멤버 변수(클래스 변수)와 메서드(클래스 메서드)

- 클래스 멤버 선언
  
  ```java
  public class <클래스명> {
      static <타입> <필드> [= 초기값];                            // 클래스 멤버 변수
      static <리턴 타입> <메서드명>([매개변수, ...]) { ... };        // 클래스 메서드
  }
  ```
  
  - `static` 키워드를 추가로 붙여 선언

- 클래스 로더가 클래스(바이트 코드)를 로드하여 메서드 메모리 영역에 적재할 때 클래스별로 관리됨

- 클래스 멤버 사용
  
  ```java
  public class Calculator {
      static int plus(int x, int y) { ... };
      static int minus(int x, int y) { ... };
  }
  
  int result1 = Calculator.plus(10, 5);        // 원칙
  
  Calculator myCal = new Calculator();
  int result2 = myCal.minus(10, 5);            // 허용
  ```
  
  - 클래스 멤버는 원칙적으로 클래스 이름으로 접근해야 하나 객체 참조 변수로도 접근 가능
    - 클래스 이름으로 접근하는 것을 권장

- 클래스 메서드 선언 시 주의사항
  
  ```java
  public class ClassName {
      int field1;                                // 인스턴스 멤버 변수
      void method1() { ... }                    // 인스턴스 메서드
      static int field2;                        // 클래스 멤버 변수
      static void method2() { ... }            // 클래스 메서드
  
      static void method3() {                    // 클래스 메서드
          this.field1 = 10;                    // 컴파일 에러
          this.method1();                        // 컴파일 에러
          field2 = 10;
          method2();
      }
  }
  ```
  
  - 클래스 메서드 선언 시 내부에 인스턴스 멤버와 `this` 키워드 사용 불가
  
  ```java
  static void method3() {                        // 클래스 메서드
      ClassName obj = new ClassName();
      obj.field1 = 10;
      obj.method1();
  }
  ```
  
  - 클래스 메서드에서 인스턴스 멤버를 사용하려는 경우 객체를 생성한 후 참조 변수로 접근해야 함