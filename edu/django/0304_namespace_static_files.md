# Namespace & Static files

## Namespace

- namespace(이름공간)
  - 객체를 구분할 수 있는 범위를 나타내는 말
  - 일반적으로 하나의 이름공간에서는 하나의 이름이 단 하나의 객체만을 가리키게 됨
  - django에서는 서로 다른 app의 같은 이름을 가진 url name은 이름공간을 설정해서 구분
  - django는 정해진 경로 하나로 모아서 보기 때문에 중간에 폴더를 임의로 만들어줌으로써 이름공간 설정
- URL namespace
  - 서로 다른 앱에서 동일한 URL 이름을 사용하는 경우에도 이름이 지정된 URL을 고유하게 사용할 수 있음
  - urls.py에 `app_name` attribute 값 작성
  - `<app명>:<url_name>`

- Template namespace
  - Django는 기본적으로 app_name/templates/ 경로에 있는 templates 파일들만 찾을 수 있음
  - INSTALLED_APPS에 작성한 app 순서로 template 검색 후 렌더링
  - 따라서 임의로 templates 폴더 구조를 app_name/templates/app_name 형태로 변경하여 경로 재설정




## Static files

- 웹 서버와 정적 파일
  - 웹 서버의 기본 동작은 특정 위치에 있는 자원(정적 파일)을 요청 받아서 제공하는 응답을 처리하는 것
  - 이는 자원과 접근 가능한 주소가 정적으로 연결된 관계
- Static file(정적 파일)
  - 응답할 때 별도의 처리 없이 파일 내용을 그대로 보여주면 되는 파일
    - 사용자의 요청에 따라 내용이 바뀌는 것이 아니라 요청한 것을 그대로 보여주는 파일
  - 웹 서버는 일반적으로 이미지, 자바 스크립트, CSS와 같은 미리 준비된 추가 파일을 제공해야 함
  - 파일 자체가 고정되어 있고, 서비스 중에도 추가되거나 변경되지 않고 고정되어 있음
- 구성
  1. `django.contrib.staticfiles`가 `INSTALLED_APPS`에 포함되어 있는지 확인
  2. settings.py에서 `STATIC_URL` 정의
  3. 템플릿에서 `static` 템플릿 태그 사용하여 지정된 상대경로에 대한 URL 빌드
  4. 앱의 static 디렉토리에 정적 파일 저장
- `STATICFILES_DIRS`
  - app/static/ 디렉토리 경로(기본 경로) 사용 외에 추가적인 정적 파일 경로 목록을 정의하는 리스트
  - 추가 파일 디렉토리에 대한 전체 경로를 포함하는 문자열 목록으로 작성되어야 함
- `STATIC_URL`
  - `STATIC_ROOT`에 있는 정적 파일을 참조할 때 사용할 URL
    - 개발 단계에서는 실제 정적 파일들이 저장되어 있는 경로 및 추가 경로들을 탐색
  - 실제 파일이나 디렉토리가 아니며 URL로만 존재
  - 비어 있지 않은 값으로 설정한다면 반드시 slash(`/`)로 끝나야 함
- `STATIC_ROOT`
  - collectstatic이 배포를 위해 정적 파일을 수집하는 디렉토리의 절대 경로
  - django 프로젝트에서 사용하는 모든 정적 파일을 한 곳에 모아 넣는 경로
  - 개발 과정에서 settings.py의 `DEBUG` 값이 `True`로 설정되어 있으면 해당 값은 작용하지 않음
    - 직접 작성하지 않으면 django 프로젝트에서는 settings.py에 작성되어 있지 않음
  - 실 서비스 환경(배포 환경)에서 django의 모든 정적 파일을 다른 웹 서버가 직접 제공하기 위함
- Django template tag
  - load
    - 사용자 정의 템플릿 세트를 로드
    - 로드하는 라이브러리, 패키지에 등록된 모든 태그와 필터를 불러옴
    - `{% load static %}`
  - static
    - `STATIC_ROOT`에 저장된 정적 파일에 연결
    - `{% static <파일 경로> %}`