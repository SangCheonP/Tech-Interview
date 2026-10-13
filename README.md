# Tech Interview

면접을 위한 CS, Java/Spring, Database, Infra 지식을 정리합니다.

## Study Roadmap

학습한 주제를 단순 암기하는 것이 아니라 앞뒤 개념을 연결해 설명할 수 있는 것을 목표로 합니다.

1. **Java / JVM** - Java 실행 과정과 메모리 관리
2. **Operating System + Java Concurrency** - Process, Thread와 동시성
3. **Database / SQL Performance** - SQL 실행 원리와 성능 최적화
4. **Database / Transaction** - 트랜잭션과 동시성 제어
5. **Spring Core** - IoC, DI, Bean, AOP, Transaction
6. **JDBC & JPA** - DB 접근부터 영속성 컨텍스트까지
7. **Network** - TCP/IP와 HTTP
8. **Spring Web** - HTTP 요청이 Spring에서 처리되는 과정
9. **Linux** - 서버 실행 환경
10. **Docker** - 컨테이너
11. **CI/CD** - 빌드와 배포 자동화
12. **Kubernetes** - 컨테이너 오케스트레이션
13. **AWS** - 클라우드 인프라

## Directory

현재 저장소에 있는 파일까지 표시했습니다. 학습 순서가 있는 디렉터리의 `README.md`에서 체크리스트를 볼 수 있습니다.

```text
Tech-Interview
├── Algorithm
│   ├── 크루스칼(Kruskal) 알고리즘.md
│   └── 플로이드-워셜(Floyd-Warshall).md
├── Computer Science
│   ├── Network
│   │   ├── HTTP & HTTPS.md
│   │   ├── OSI 7계층 & TCP IP.md
│   │   ├── README.md
│   │   ├── TCP 3 & 4 way handshake.md
│   │   ├── TCP 흐름제어 & 혼잡제어.md
│   │   └── UDP.md
│   ├── Operating System
│   │   ├── 01. Program과 Process.md
│   │   ├── 02. Process 메모리 구조.md
│   │   ├── 03. Process와 Thread.md
│   │   ├── 04. Context Switching.md
│   │   ├── 05. 동시성과 병렬성.md
│   │   └── README.md
│   └── OS
│       ├── 경쟁 상태(Race Condition).md
│       ├── 데드락(DeadLock).md
│       ├── 뮤텍스 & 세마포어(Mutex & Semaphore).md
│       ├── 세마포어(Semapoer).md
│       ├── 프로세스 & 스레드.md
│       └── CPU 스케줄링(CPU Scheduling).md
├── Database
│   ├── SQL Performance
│   │   └── README.md
│   ├── Transaction
│   │   └── README.md
│   ├── 뷰(View).md
│   ├── 인덱스(Index).md
│   ├── 정규화(Normalization).md
│   └── RDB & NoSQL.md
├── docs
│   └── WRITING_GUIDE.md
├── Framework
│   ├── JPA
│   │   └── README.md
│   └── Spring
│       ├── Core
│       │   └── README.md
│       ├── Web
│       │   └── README.md
│       └── 스프링(Spring).md
├── Infra
│   ├── AWS
│   │   └── README.md
│   ├── CI-CD
│   │   └── README.md
│   ├── Docker
│   │   └── README.md
│   ├── Kubernetes
│   │   └── README.md
│   └── Linux
│       └── README.md
├── Language
│   └── Java
│       ├── Concurrency
│       │   ├── 01. Java Thread.md
│       │   └── README.md
│       ├── JVM
│       │   ├── 01. Java 실행 과정.md
│       │   ├── 02. JVM 구조.md
│       │   ├── 03. Stack과 Heap.md
│       │   ├── 04. 객체 생성과 메모리.md
│       │   ├── 05. GC (Garbage Collection).md
│       │   ├── 06. Class Loader.md
│       │   ├── 07. JIT Compiler.md
│       │   └── README.md
│       ├── 오버로딩 & 오버라이딩(Overloading & Overriding).md
│       ├── 컴파일 & 런타임(Complile & Run-time).md
│       ├── 클래스 & 함수 정리.md
│       ├── Deque (덱).md
│       ├── GC(Garbage Collection).md
│       ├── List(리스트).md
│       ├── Map(맵).md
│       ├── PriorityQueue (우선순위 큐).md
│       ├── Queue(큐).md
│       ├── Set(집합).md
│       ├── Stack(스택).md
│       └── String.md
├── resources
│   └── UDP_Header.png
└── README.md
```

## 학습 문서 읽기

각 문서는 **대표 면접 질문 → 30초 답변 → 핵심 키워드 → 설명과 예제 → 꼬리 질문과 답** 순서로 읽을 수 있습니다. 분야별 질문 범위는 [Interview_Question_for_Beginner](https://github.com/jbee37142/Interview_Question_for_Beginner)를 참고하고, 내용은 공식 자료와 현재 동작에 맞춰 작성합니다. 작성 기준은 [면접 학습 문서 작성 기준](docs/WRITING_GUIDE.md)에 정리했습니다.
