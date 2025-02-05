## **PriorityQueue (우선순위 큐)**

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
