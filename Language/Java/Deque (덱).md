## **Deque (덱 - 양방향 큐)**

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
