# Java 자료구조: Stack, Queue, Deque와 PriorityQueue

관련 개념을 한 문서에서 이어서 학습합니다.

## Stack

### **Stack (스택)**

<img src="https://velog.velcdn.com/images/hyhy9501/post/9082764d-08fa-4a38-87d1-966da9b11195/image.png">

<br>

📍 **스택 생성**
```java
Stack<Type> stack = new Stack<>();
```

---

📍 **원소 추가 (Push)**
```java
stack.push(element); // 스택의 맨 위에 원소 추가
```

---

📍 **원소 제거 (Pop)**
```java
stack.pop(); // 스택의 맨 위 원소 제거 및 반환 (스택이 비어있으면 예외 발생)
```

---

📍 **맨 위 원소 조회 (Peek)**
```java
stack.peek(); // 스택의 맨 위 원소 확인 (제거하지 않음)
```

---

📍 **스택 크기 및 확인**
```java
stack.size(); // 스택 크기 반환
stack.isEmpty(); // 스택이 비어있는지 확인 (true / false)
```

---

📍 **특정 원소 탐색**
```java
stack.contains(element); // 특정 원소 포함 여부 확인 (true / false)
stack.search(element); // 특정 원소 위치 반환 (맨 위가 1, 없으면 -1)
```

---

📍 **스택 변환**
```java
stack.toArray(new Integer[0]); // 스택 → 배열 변환
```

---

📍 **스택 복사**
```java
Stack<Type> newStack = (Stack<Type>) stack.clone(); // 스택 복사
```

---

📍 **스택 비교**
```java
stack.equals(otherStack); // 두 스택 비교
```

---

📍 **스택 초기화**
```java
stack.clear(); // 스택의 모든 원소 제거
```

## Queue

### **Queue (큐)**

<img src="https://blog.kakaocdn.net/dn/dkmZKQ/btrZoq7tUOg/42Rwjx12k7ca48qrpcA9z1/img.png">

<br>

📍 **큐 생성**
```java
Queue<Type> queue = new LinkedList<>();
```

---

📍 **원소 추가 (Enqueue)**
```java
queue.add(element);    // 큐의 끝에 원소 추가 (실패 시 예외 발생)
queue.offer(element);  // 큐의 끝에 원소 추가 (실패 시 false 반환)
```

---

📍 **원소 제거 (Dequeue)**
```java
queue.remove(); // 큐의 맨 앞 원소 제거 및 반환 (비어있으면 예외 발생)
queue.poll();   // 큐의 맨 앞 원소 제거 및 반환 (비어있으면 null 반환)
```

---

📍 **맨 앞 원소 조회 (Peek)**
```java
queue.element(); // 큐의 맨 앞 원소 조회 (비어있으면 예외 발생)
queue.peek();    // 큐의 맨 앞 원소 조회 (비어있으면 null 반환)
```

---

📍 **큐 크기 및 확인**
```java
queue.size();    // 큐 크기 반환
queue.isEmpty(); // 큐가 비어있는지 확인 (true / false)
```

---

📍 **특정 원소 탐색**
```java
queue.contains(element); // 특정 원소 포함 여부 확인 (true / false)
```

---

📍 **큐 변환**
```java
queue.toArray(new Integer[0]); // 큐 → 배열 변환
```

---

📍 **큐 복사**
```java
Queue<Type> newQueue = new LinkedList<>(queue); // 큐 복사
```

---

📍 **큐 비교**
```java
queue.equals(otherQueue); // 두 큐 비교
```

---

📍 **큐 초기화**
```java
queue.clear(); // 큐의 모든 원소 제거
```

## Deque

### **Deque (덱 - 양방향 큐)**

<img src="https://media.geeksforgeeks.org/wp-content/uploads/anod.png">

<br>

📍 **덱 생성**
```java
Deque<Type> deque = new ArrayDeque<>(); // 일반적인 덱 사용
Deque<Type> linkedDeque = new LinkedList<>(); // LinkedList 기반 덱
```

---

📍 **앞/뒤 원소 추가**
```java
deque.addFirst(element);  // 앞쪽에 원소 추가 (실패 시 예외 발생)
deque.offerFirst(element); // 앞쪽에 원소 추가 (실패 시 false 반환)

deque.addLast(element);   // 뒤쪽에 원소 추가 (실패 시 예외 발생)
deque.offerLast(element); // 뒤쪽에 원소 추가 (실패 시 false 반환)
```

---

📍 **앞/뒤 원소 제거**
```java
deque.removeFirst();  // 앞쪽 원소 제거 및 반환 (비어있으면 예외 발생)
deque.pollFirst();    // 앞쪽 원소 제거 및 반환 (비어있으면 null 반환)

deque.removeLast();   // 뒤쪽 원소 제거 및 반환 (비어있으면 예외 발생)
deque.pollLast();     // 뒤쪽 원소 제거 및 반환 (비어있으면 null 반환)
```

---

📍 **앞/뒤 원소 조회**
```java
deque.getFirst();  // 앞쪽 원소 조회 (제거하지 않음, 비어있으면 예외 발생)
deque.peekFirst(); // 앞쪽 원소 조회 (제거하지 않음, 비어있으면 null 반환)

deque.getLast();   // 뒤쪽 원소 조회 (제거하지 않음, 비어있으면 예외 발생)
deque.peekLast();  // 뒤쪽 원소 조회 (제거하지 않음, 비어있으면 null 반환)
```

---

📍 **덱 크기 및 확인**
```java
deque.size();    // 덱의 크기 반환
deque.isEmpty(); // 덱이 비어있는지 확인 (true / false)
```

---

📍 **특정 원소 존재 여부 확인**
```java
deque.contains(element); // 특정 원소 포함 여부 확인 (true / false)
```

---

📍 **덱 변환**
```java
deque.toArray(new Type[0]); // 덱을 배열로 변환
```

---

📍 **덱 초기화**
```java
deque.clear(); // 모든 원소 제거
```

---

📍 **사용 예제: 앞뒤로 원소 추가 및 제거**
```java
Deque<Integer> deque = new ArrayDeque<>();
deque.addFirst(1);
deque.addLast(2);
deque.addFirst(0);
System.out.println(deque); // 출력: [0, 1, 2]

deque.removeFirst();
System.out.println(deque); // 출력: [1, 2]

deque.removeLast();
System.out.println(deque); // 출력: [1]
```

---

📍 **사용 예제: 큐처럼 사용 (FIFO)**
```java
Deque<Integer> queue = new ArrayDeque<>();
queue.offer(1);  // = addLast()
queue.offer(2);
queue.offer(3);
System.out.println(queue.poll()); // 출력: 1 (가장 먼저 추가된 원소 제거)
```
```

## PriorityQueue

### **PriorityQueue (우선순위 큐)**

📍 **우선순위 큐 생성**
```java
PriorityQueue<Type> minHeap = new PriorityQueue<>(); // 기본: 최소 힙 (오름차순)
PriorityQueue<Type> maxHeap = new PriorityQueue<>(Collections.reverseOrder()); // 최대 힙 (내림차순)
PriorityQueue<Type> customQueue = new PriorityQueue<>((a, b) -> a.compareTo(b)); // 사용자 정의 정렬 기준
```

---

📍 **원소 추가 (Enqueue)**
```java
priorityQueue.add(element);  // 원소 추가 (실패 시 예외 발생)
priorityQueue.offer(element); // 원소 추가 (실패 시 false 반환)
```

---

📍 **원소 제거 (Dequeue)**
```java
priorityQueue.poll();  // 가장 높은 우선순위 원소 제거 및 반환 (비어있으면 null 반환)
priorityQueue.remove(); // 가장 높은 우선순위 원소 제거 (비어있으면 예외 발생)
```

---

📍 **우선순위 원소 조회 (Peek)**
```java
priorityQueue.peek(); // 가장 높은 우선순위 원소 조회 (제거하지 않음, 비어있으면 null 반환)
```

---

📍 **큐 크기 및 확인**
```java
priorityQueue.size();    // 큐 크기 반환
priorityQueue.isEmpty(); // 큐가 비어있는지 확인 (true / false)
```

---

📍 **특정 원소 존재 여부 확인**
```java
priorityQueue.contains(element); // 특정 원소 포함 여부 확인 (true / false)
```

---

📍 **우선순위 큐 변환**
```java
priorityQueue.toArray(new Type[0]); // 우선순위 큐 → 배열 변환
```

---

📍 **우선순위 큐 초기화**
```java
priorityQueue.clear(); // 모든 원소 제거
```

---

[다음: JVM 학습 목차](<JVM/README.md>)
