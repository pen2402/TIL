- 

- Model

  - 단일한 데이터에 대한 정보를 가짐
    - 사용자가 저장하는 데이터들의 필수적인 필드들과 동작들을 포함


  - 저장된 데이터베이스의 구조(layout)
  - django는 model을 통해 데이터에 접속하고 관리
  - 일반적으로 각각의 model은 하나의 데이터베이스 테이블에 매핑됨

- Database

  - 데이터베이스(DB)
    - 체계화된 데이터의 모임

  - 쿼리(Query)
    - 데이터를 조회하기 위한 명령어
    - 조건에 맞는 데이터를 추출하거나 조작하는 명령어
    - Query를 날리는 것은 DB를 조작하는 것

- Database의 기본 구조

  - 스키마(Schema)
    - 데이터베이스에서 자료의 구조, 표현방법, 관계 등을 정의한 구조(structure)
    - 데이터베이스의 구조와 제약 조건(자료의 구조, 표현 방법, 관계)에 관련한 전반적인 명세를 기술한 것

  - 테이블(Table)
    - 열(column) : 필드(field) or 속성
      - 각 열에는 고유한 데이터 형식이 지정(INTEGER, TEXT, NULL 등)

    - 행(row) : 레코드(record) or 튜플
      - 테이블의 데이터는 행에 저장

    - 기본키(PK)
      - 각 행의 고유값으로 Primary Key로 불림
      - 반드시 설정해야 하며, 데이터베이스 관리 및  관계 설정 시 주요하게 활용(django에서는 id)

- Model

  - 웹 애플리케이션의 데이터를 구조화하고 조작하기 위한 도구

- ORM

  - Object_Relational-Mapping
  - 객체 지향 프로그래밍 언어를 사용하여 호환되지 않는 유형의 시스템 간에(Django - SQL) 데이터를 변환하는 프로그래밍 기술
  - OOP 프로그래밍에서 RDBMS을 연동할 때, 데이터베이스와 객체 지향 프로그래밍 언어 간의 호환되지 않는 데이터를 변환하는 프로그래밍 기법
  - Django는 내장 Django ORM을 사용
  - 장점
    - SQL을 잘 알지 못해도 DB 조작 가능
    - SQL의 절차적 접근이 아닌 객체 지향적 접근으로 인한 높은 생산성

  - 단점
    - ORM만으로 완전한 서비스를 구현하기 어려운 경우 존재

  - 현대 웹 프레임워크의 요점은 웹 개발의 속도를 높이는 것(생산성)
  - DB를 객체로 조작하기 위해 사용

- `CharField(max_length=None, **options)`

  - 길이 제한이 있는 문자열을 넣을 때 사용
  - CharField의 max_length는 필수 인자
  - 필드의 최대 길이(문자), 데이터베이스 레벨과 Django의 유효성 검사(값 검증)에서 활용

- `TextField(**options)`

  - 글자 수가 많을 때 사용
  - `max_length` 옵션 작성 시 자동 양식 필드인 textarea 위젯에 반영은 되지만 모델과 데이터베이스 수준에는 적용되지 않음
  - `max_length`는 `CharField()`에서 사용해야 함




## Migrations

- django가 model에 생긴 변화를 반영하는 방법
-  Migration 실행 및 DB 스키마를 다루기 위한 몇 가지 명령어
  - `makemigrations`
    - model을 변경한 것에 기반한 새로운 마이그레이션을 만들 때 사용
  - `migrate`
    - 마이그레이션을 DB에 반영하기 위해 사용
    - 설계도를 실제 DB에 반영하는 과정
    - 모델에서의 변경 사항들과 DB의 스키마가 동기화를 이룸
  - `sqlmigrate`
    - 마이그레이션에 대한 SQL 구문을 보기 위해 사용
    - 마이그레이션이 SQL문으로 어떻게 해석되어서 동작할지 미리 확인할 수 있음
  - `showmigrations`
    - 프로젝트 전체의 마이그레이션 상태를 확인하기 위해 사용
    - 마이그레이션 파일들이 migrate 되었는지 아닌지 여부를 확인할 수 있음
- DataField 옵션
  - auto_now_add
    - 최초 생성 일자
    - django ORM이 최초 insert(테이블에 데이터 입력) 시에만 현재 날짜와 시간으로 갱신(테이블에 어떤 값을 최초로 넣을 때)
  - auto_now
    - 최종 수정 일자
    - Django ORM이 save를 할 때마다 현재 날짜와 시간으로 갱신
- migration 3단계
  1. models.py
     - model 변경사항 발생 시
  2. $ python manage.py makemigrations
     - migrations 파일 생성
  3. $ python manage.py migrate
     - DB 반영(모델과 DB의 동기화)



## Database API

- DB를 조작하기 위한 도구

- django가 기본적으로 ORM을 제공함으로써 편하게 조작할 수 있도록 도움

- Model을 만들면 django는 객체들을 만들고 읽고 수정하고 지울 수 있는 database-abstract API를 자동으로 만듦

- ```
  Article.objects.all()
  # Article : Class Name
  # objects : Manager('objects'로 고정)
  # all() : QuerySet API(메소드)
  ```

- Manager

  - django 모델에 데이터베이스 query 작업이 제공되는 인터페이스
  - 기본적으로 모든 Django 모델 클래스에 objects라는 Manager를 추가

- QuerySet

  - 데이터베이스로부터 전달받은 객체 목록
  - queryset 안의 객체는 0개, 1개 혹은 여러 개일 수 있음
  - 데이터베이스로부터 조회, 필터, 정렬 등을 수행할 수 있음

- Django shell

  - 일반 Python shell을 통해서는 장고 프로젝트 환경에 접근할 수 없음
  - 그래서 장고 프로젝트 설정이 load된 Python shell을 활용해 DB API 구문 테스트 진행
  - 기본 django shjell 보다 더 많은 기능을 제공하는 shell_plus를 사용해서 진행
    - Django-extensions 라이브러리의 기능 중 하나



## CRUD

- 대부분의 컴퓨터 소프트웨어가 가지는 기본적인 데이터 처리 기능
- Create(생성), Read(읽기), Update(갱신), Delete(삭제)를 묶어서 일컫는 말

- CREATE 관련 메소드
  - `save()`
    - saving objects
    - 객체를 데이터베이스에 저장
    - 데이터 생성 시 save()를 호출하기 전에는 객체의 ID 값이 무엇인지 알 수 없음
      - ID 값은 django가 아니라 DB에서 계산되기 때문
    - 단순히 모델을 인스턴스화하는 것은 DB에 영향을 미치지 않기 때문에 반드시 save() 필요
  - str
    - 표준 파이썬 클래스의 메소드인 str()을 정의하여 각각의 object가 사람이 읽을 수 있는 문자열을 반환하도록 할 수 있음
  - `full_clean()`
    - 유효성 검사
- READ
  - QuerySet API method를 사용해 다양한 조회를 하는 것이 중요
  - QuerySet API method는 크게 2가지로 분류
    - Methods that return new querysets
    - Methods that do not return querysets
  - all()
    - 현재 QuerySet의 복사본을 반환
  - `get()`
    - 주어진 lookup 매개변수와 일치하는 객체를 반환
    - 객체를 찾을 수 없으면 `DoesNotExist` 예외 발생 시킴
    - 둘 이상의 객체를 찾으면 `MultipleObjectReturned` 예외 발생 시킴
    - 따라서 primary key와 같이 고유성(unique)을 보장하는 조회에서 사용해야 함
    - `get_object_or_404` 함수를 사용하여 객체가 존재하지 않으면 404 error 전달
  - `filter()`
    - 주어진 lookup 매개변수와 일치하는 객체를 포함하는 새 QuerySet을 반환
  - `delete()`
    - 모든 행에 대해 SQL 삭제 쿼리를 수행하고, 삭제된 객체 수와 객체 유형당 삭제 수가 포함된 딕셔너리 반환
  - Field lookups
    - 조회 시 특정 검색 조건을 지정
    - QuerySet 메소드 filter(), exclude() 및 get()에 대한 키워드 인수로 지정
  - QuerySet API
    - https://docs.Djangoproject.com/en/3.2/ref/models/querysets/#queryset-api-reference



## Admin Site

- Automatic admin interface
  - 사용자가 아닌 서버의 관리자가 활용하기 위한 페이지
  - Model class를 `admin.py`에 등록하고 관리
  - `django.contrib.auth` 모듈에서 제공
  - record 생성 여부 확인에 매우 유용하며 직접 record를 삽입할 수도 있음