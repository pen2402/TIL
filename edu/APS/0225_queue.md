# 큐(Queue)

- 큐(Queue)의 특성
  - 스택과 마찬가지로 삽입과 삭제의 위치가 제한적인 자료구조
  - 선입선출 구조(FIFO, First In First Out)
    - 머리(Front) : 저장된 원소 중 첫 번째 원소(또는 삭제된 위치)
    - 꼬리(Rear) : 저장된 원소 중 마지막 원소
  - 큐의 기본 연산
    - enQueue(item) : 큐의 뒤쪽(rear 다음)에 원소를 삽입하는 연산
    - deQueue() : 큐의 앞쪽(front)에서 원소를 삭제하고 반환하는 연산
    - createQueue() : 공백 상태의 큐를 생성하는 연산
    - isEmpty() : 큐가 공백 상태인지를 확인하는 연산
    - isFull() : 큐가 포화 상태인지를 확인하는 연산
    - Qpeek() : 큐의 앞쪽에서 원소를 삭제 없이 반환하는 연산



## 선형 큐

- 1차원 배열을 이용한 큐
  - 큐의 크기 = 배열의 크기
  - front : 저장된 첫 번째 원소의 인덱스
  - rear : 저장된 마지막 원소의 인덱스
- 상태 표현
  - 초기 상태 : front = rear = -1
  - 공백 상태 : front == rear
  - 포화 상태 : rear == n-1 (n : 배열의 크기, n-1 : 배열의 마지막 인덱스)
- 문제
  - 잘못된 포화상태 인식
    - 삽입과 삭제를 계속할 경우 배열 앞부분에 활용할 수 있는 공간이 있음에도 포화상태로 인식
  - 해결 방법
    - 매 연산 시에 저장된 원소들을 배열 앞부분으로 모두 이동
    - 그러나 원소 이동에 많은 시간이 소요되어 큐의 효율성이 급격히 떨어짐
    - 따라서 원형 큐를 이용하여 해결 가능



## 원형 큐

- 1차원 배열을 사용하되, 논리적으로 배열의  처음과 끝이 연결되어 원형의 형태를 이룬다고 가정한 큐
- 인덱스의 순환
  - front와 rear의 위치가 배열의 마지막 인덱스를 가리킨 후, 다시 배열의 처음 인덱스로 이동
  - 이를 구현하기 위해 나머지 연산자 mod 사용
- 상태 표현
  - 초기 공백 상태 : front = rear = 0
  - 포화 상태 : 삽입할 rear의 다음 위치 == 현재 front
  - 공백 상태와 포화 상태를 구분하기 위해 front가 있는 자리는 사용하지 않고 항상 비워둠




## 우선순위 큐(Priority Queue)

- 우선순위를 가진 항목들을 저장하는 큐
- 원소를 삽입하는 과정에서 우선순위를 비교하여 적절한 위치에 삽입
- FIFO 순서가 아니라 우선순위가 높은 순서대로 먼저 나감
- 적용 분야
  - 시뮬레이션 시스템
  - 네트워크 트래픽 제어
  - 운영체제의 태스크 스케줄링

- 문제점
  - 배열을 사용하므로 삽입이나 삭제 연산이 일어날 때 원소의 재배치가 발생
  - 이에 소요되는 시간이나 메모리 낭비가 큼



## 큐의 활용 : 버퍼(Buffer)

- 버퍼
  - 데이터를 한 곳에서 다른 한 곳으로 전송하는 동안 일시적으로 그 데이터를 보관하는 메모리의 영역
  - 버퍼링 : 버퍼를 활용하는 방식 또는 버퍼를 채우는 동작을 의미
- 버퍼의 자료구조
  - 일반적으로 입출력 및 네트워크와 관련된 기능에서 이용
  - 순서대로 입력/출력/전달되어야 하므로 FIFO 방식의 자료구조인 큐가 활용됨



## 너비 우선 탐색(BFS, Breadth First Search)

- 시작점의 인접한 정점들을 모두 차례로 방문한 후, 방문했던 정점을 다시 시작점으로 하여 탐색하는 방식
- 인접한 정점들에 대해 먼저 탐색하는 과정을 반복하므로 선입선출 형태의 자료구조인 큐를 활용
