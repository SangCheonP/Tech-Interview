## **Stack (스택)**

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

📍 **스택 반복 및 순회**
```java
while (!stack.isEmpty()) {
    System.out.println(stack.pop()); // 스택에서 하나씩 꺼내면서 출력
}

// 또는 Iterator 사용
for (Type element : stack) {
    System.out.println(element);
}
```

---

📍 **스택 초기화**
```java
stack.clear(); // 스택의 모든 원소 제거
```

---

이제 `Stack`을 효율적으로 활용할 수 있습니다! 🚀
