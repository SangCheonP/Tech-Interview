# Tech Interview

면접을 위한 CS, Java/Spring, Database, Infra 지식을 정리합니다.

## Study Roadmap

학습한 주제를 단순 암기하는 것이 아니라 앞뒤 개념을 연결해 설명할 수 있는 것을 목표로 합니다.

1. [**Java / JVM**](Language/Java/JVM/README.md) - Java 실행 과정과 메모리 관리
2. [**Operating System**](Computer%20Science/Operating%20System/README.md) + [**Java Concurrency**](Language/Java/Concurrency/README.md) - Process, Thread와 동시성
3. [**Database / SQL Performance**](Database/SQL%20Performance/README.md) - SQL 실행 원리와 성능 최적화
4. [**Database / Transaction**](Database/Transaction/README.md) - 트랜잭션과 동시성 제어
5. [**Spring Core**](Framework/Spring/Core/README.md) - IoC, DI, Bean, AOP, Transaction
6. [**JDBC & JPA**](Framework/JPA/README.md) - DB 접근부터 영속성 컨텍스트까지
7. [**Network**](Computer%20Science/Network/README.md) - TCP/IP와 HTTP
8. [**Spring Web**](Framework/Spring/Web/README.md) - HTTP 요청이 Spring에서 처리되는 과정
9. [**Linux**](Infra/Linux/README.md) - 서버 실행 환경
10. [**Docker**](Infra/Docker/README.md) - 컨테이너
11. [**CI/CD**](Infra/CI-CD/README.md) - 빌드와 배포 자동화
12. [**Kubernetes**](Infra/Kubernetes/README.md) - 컨테이너 오케스트레이션
13. [**AWS**](Infra/AWS/README.md) - 클라우드 인프라

## Directory

현재 저장소의 폴더와 파일을 표시했습니다. 이름을 누르면 해당 위치로 이동합니다. 학습 순서는 각 분야의 `README.md`에서 확인할 수 있습니다. 작성 예정 항목은 목차에만 표시하고, 작성된 학습 문서 끝에는 다음 문서 링크를 둡니다.

<pre>
Tech-Interview
├── <a href="Algorithm">Algorithm</a>
│   ├── <a href="Algorithm/%ED%81%AC%EB%A3%A8%EC%8A%A4%EC%B9%BC(Kruskal)%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98.md">크루스칼(Kruskal) 알고리즘.md</a>
│   └── <a href="Algorithm/%ED%94%8C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%9B%8C%EC%85%9C(Floyd-Warshall).md">플로이드-워셜(Floyd-Warshall).md</a>
├── <a href="Computer%20Science">Computer Science</a>
│   ├── <a href="Computer%20Science/Network">Network</a>
│   │   ├── <a href="Computer%20Science/Network/HTTP%20&amp;%20HTTPS.md">HTTP &amp; HTTPS.md</a>
│   │   ├── <a href="Computer%20Science/Network/OSI%20%EA%B3%84%EC%B8%B5%EA%B3%BC%20TCP-UDP.md">OSI 계층과 TCP-UDP.md</a>
│   │   ├── <a href="Computer%20Science/Network/README.md">README.md</a>
│   │   └── <a href="Computer%20Science/Network/TCP%20%EC%97%B0%EA%B2%B0%EA%B3%BC%20%EC%A0%9C%EC%96%B4.md">TCP 연결과 제어.md</a>
│   └── <a href="Computer%20Science/Operating%20System">Operating System</a>
│       ├── <a href="Computer%20Science/Operating%20System/01.%20Program,%20Process%EC%99%80%20%EB%A9%94%EB%AA%A8%EB%A6%AC.md">01. Program, Process와 메모리.md</a>
│       ├── <a href="Computer%20Science/Operating%20System/02.%20Thread,%20%EB%AC%B8%EB%A7%A5%20%EA%B5%90%ED%99%98%EA%B3%BC%20%EB%8F%99%EC%8B%9C%EC%84%B1.md">02. Thread, 문맥 교환과 동시성.md</a>
│       ├── <a href="Computer%20Science/Operating%20System/03.%20CPU%20%EC%8A%A4%EC%BC%80%EC%A4%84%EB%A7%81.md">03. CPU 스케줄링.md</a>
│       ├── <a href="Computer%20Science/Operating%20System/04.%20%EA%B2%BD%EC%9F%81%20%EC%83%81%ED%83%9C%EC%99%80%20%EB%8F%99%EA%B8%B0%ED%99%94,%20%EB%8D%B0%EB%93%9C%EB%9D%BD.md">04. 경쟁 상태와 동기화, 데드락.md</a>
│       └── <a href="Computer%20Science/Operating%20System/README.md">README.md</a>
├── <a href="Database">Database</a>
│   ├── <a href="Database/SQL%20Performance">SQL Performance</a>
│   │   └── <a href="Database/SQL%20Performance/README.md">README.md</a>
│   ├── <a href="Database/Transaction">Transaction</a>
│   │   └── <a href="Database/Transaction/README.md">README.md</a>
│   ├── <a href="Database/%EB%B7%B0(View).md">뷰(View).md</a>
│   ├── <a href="Database/%EC%9D%B8%EB%8D%B1%EC%8A%A4(Index).md">인덱스(Index).md</a>
│   ├── <a href="Database/%EC%A0%95%EA%B7%9C%ED%99%94(Normalization).md">정규화(Normalization).md</a>
│   └── <a href="Database/RDB%20&amp;%20NoSQL.md">RDB &amp; NoSQL.md</a>
├── <a href="docs">docs</a>
│   └── <a href="docs/WRITING_GUIDE.md">WRITING_GUIDE.md</a>
├── <a href="Framework">Framework</a>
│   ├── <a href="Framework/JPA">JPA</a>
│   │   └── <a href="Framework/JPA/README.md">README.md</a>
│   └── <a href="Framework/Spring">Spring</a>
│       ├── <a href="Framework/Spring/Core">Core</a>
│       │   └── <a href="Framework/Spring/Core/README.md">README.md</a>
│       └── <a href="Framework/Spring/Web">Web</a>
│           └── <a href="Framework/Spring/Web/README.md">README.md</a>
├── <a href="Infra">Infra</a>
│   ├── <a href="Infra/AWS">AWS</a>
│   │   └── <a href="Infra/AWS/README.md">README.md</a>
│   ├── <a href="Infra/CI-CD">CI-CD</a>
│   │   └── <a href="Infra/CI-CD/README.md">README.md</a>
│   ├── <a href="Infra/Docker">Docker</a>
│   │   └── <a href="Infra/Docker/README.md">README.md</a>
│   ├── <a href="Infra/Kubernetes">Kubernetes</a>
│   │   └── <a href="Infra/Kubernetes/README.md">README.md</a>
│   └── <a href="Infra/Linux">Linux</a>
│       └── <a href="Infra/Linux/README.md">README.md</a>
├── <a href="Language">Language</a>
│   └── <a href="Language/Java">Java</a>
│       ├── <a href="Language/Java/Concurrency">Concurrency</a>
│       │   ├── <a href="Language/Java/Concurrency/01.%20Java%20Thread.md">01. Java Thread.md</a>
│       │   └── <a href="Language/Java/Concurrency/README.md">README.md</a>
│       ├── <a href="Language/Java/JVM">JVM</a>
│       │   ├── <a href="Language/Java/JVM/01.%20Java%20%EC%8B%A4%ED%96%89%20%EA%B3%BC%EC%A0%95.md">01. Java 실행 과정.md</a>
│       │   ├── <a href="Language/Java/JVM/02.%20JVM%20%EA%B5%AC%EC%A1%B0.md">02. JVM 구조.md</a>
│       │   ├── <a href="Language/Java/JVM/03.%20Stack%EA%B3%BC%20Heap.md">03. Stack과 Heap.md</a>
│       │   ├── <a href="Language/Java/JVM/04.%20%EA%B0%9D%EC%B2%B4%20%EC%83%9D%EC%84%B1%EA%B3%BC%20GC.md">04. 객체 생성과 GC.md</a>
│       │   ├── <a href="Language/Java/JVM/05.%20Class%20Loader.md">05. Class Loader.md</a>
│       │   ├── <a href="Language/Java/JVM/06.%20JIT%20Compiler.md">06. JIT Compiler.md</a>
│       │   └── <a href="Language/Java/JVM/README.md">README.md</a>
│       ├── <a href="Language/Java/%EC%98%A4%EB%B2%84%EB%A1%9C%EB%94%A9%20&amp;%20%EC%98%A4%EB%B2%84%EB%9D%BC%EC%9D%B4%EB%94%A9(Overloading%20&amp;%20Overriding).md">오버로딩 &amp; 오버라이딩(Overloading &amp; Overriding).md</a>
│       ├── <a href="Language/Java/%EC%BB%AC%EB%A0%89%EC%85%98%20List,%20Set,%20Map.md">컬렉션 List, Set, Map.md</a>
│       ├── <a href="Language/Java/%ED%81%B4%EB%9E%98%EC%8A%A4%20&amp;%20%ED%95%A8%EC%88%98%20%EC%A0%95%EB%A6%AC.md">클래스 &amp; 함수 정리.md</a>
│       ├── <a href="Language/Java/Stack,%20Queue,%20Deque%EC%99%80%20PriorityQueue.md">Stack, Queue, Deque와 PriorityQueue.md</a>
│       └── <a href="Language/Java/String.md">String.md</a>
├── <a href="resources">resources</a>
│   └── <a href="resources/UDP_Header.png">UDP_Header.png</a>
└── <a href="README.md">README.md</a>
</pre>

## 학습 문서 읽기

각 문서는 **대표 면접 질문 → 30초 답변 → 핵심 키워드 → 설명과 예제 → 꼬리 질문과 답** 순서로 읽을 수 있습니다. 분야별 질문 범위는 [Interview_Question_for_Beginner](https://github.com/jbee37142/Interview_Question_for_Beginner)를 참고하고, 내용은 공식 자료와 현재 동작에 맞춰 작성합니다. 작성 기준은 [면접 학습 문서 작성 기준](docs/WRITING_GUIDE.md)에 정리했습니다.
