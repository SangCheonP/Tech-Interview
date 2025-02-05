## **Queue (큐)**

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
