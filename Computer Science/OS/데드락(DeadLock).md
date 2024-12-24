# 데드락 (Deadlock)

## 데드락(Deadlock)이란?
```
둘 이상의 작업(프로세스 또는 스레드)이 서로 자원을 기다리며 영원히 대기 상태에 빠지는 상황
```

<br>

<img src="https://files.prepinsta.com/2023/01/Deadlock-in-Operating-System-1-1024x640.webp">

<br>

### 데드락 발생 조건(교착 상태 발생 조건)
1. **상호 배제(Mutual Exclusion)**
    - 자원은 한 번에 하나의 프로세스만 사용할 수 있음

2. **점유 대기(Hold and Wait)**
    - 자원을 점유한 프로세스가 다른 자원을 요청하며 대기 상태에 있음

3. **비선점(Non-Preemption)**
    - 점유한 자원은 해당 프로세스가 작업을 완료할 때까지 강제로 빼앗을 수 없음

4. **순환 대기(Circular Wait)**
    - 프로세스들이 순환적으로 자원을 대기하고 있는 상태<br>
    예: P1 → P2 → P3 → P1

<br>

### 데드락 해결 방법
1. 자원 할당 순서 정하기
    - 모든 스레드가 자원을 요청할 때 고정된 순서로 요청하도록 설정<br>
    예: 항상 resource1 → resource2 순서로 자원을 요청

<br>

2. 타임 아웃 설정
    - 자원을 획득하지 못할 경우 일정 시간 후 대기 상태를 종료

<br>

3. 데드락 회피 (Deadlock Avoidance)
    - 자원이 한 종류 : 자원 할당 그래프(Resource Allocation Graph Algorithm)
    - 자원이 두 종류이상 : 은행원 알고리즘(Banker's Algorithm)으로 자원의 상태를 미리 분석하여 데드락을 회피

<br>

### 자원 할당 그래프(Resource Allocation Graph Algorithm)
```
 자원이 하나일 때 사용하는 알고리즘. 자원 할당 그래프에 요청 간선과 할당 간선에 추가하여, 예약간선이라는 새로운 유형의 간선을 도입
```

<img src="https://velog.velcdn.com/images/youngju307/post/f0fbc0c8-ce63-47fc-9d10-edf41445842d/image.png">


#### 교착상태 확인 방법
1. 자원할당 그래프의 사이클이 존재하는 지 확인

2. 사이클이 존재한다면
  - 자원 유형에 하나의 사례만 있으면 교착상태

  - 자원 유형에 여러 사례가 있으면 교착상태 가능성

<br>

### 은행원 알고리즘(Banker's Algorithm)
```
프로세스가 자원을 요청했을 때 최대요청의 값을 보고 받아들일지, 받아들이지 않을 것인지를 결정하는 알고리즘
```

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FP8ePa%2FbtsD0Lb2rzv%2FxSxWrO59ESNTQDBYNlCQ01%2Fimg.png">

<br>

#### 장점
1. 교착 상태가 발생하기 전에 예방

2. 교착 상태를 예방하기 때문에 시스템 성능 향상

<br>

#### 단점
1. 프로세스의 자원 요청 순서를 변경하지 못할 경우 사용하지 못함

2. 프로세스가 얼만큼의 자원을 사용할 지 미리 파악하고 알고있어야 하며 중간에 자원 사용량이 늘어나는 상황은 허용하지 않음

3. 항상 Safe State를 유지해야 하기 때문에 자원 사용량이 낮아짐