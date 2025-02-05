## **Set (집합)**

📍 **집합 생성**
```java
Set<Type> hashSet = new HashSet<>();
Set<Type> treeSet = new TreeSet<>(); // 자동 오름차순 정렬
Set<Type> linkedHashSet = new LinkedHashSet<>();
```

---

📍 **원소 추가**
```java
set.add(element); // 원소 추가 (중복된 값은 추가되지 않음)
set.addAll(Collection c); // 다른 컬렉션의 모든 원소 추가 (합집합)
```

---

📍 **원소 제거**
```java
set.remove(element); // 특정 원소 제거
set.clear(); // 집합의 모든 원소 제거
```

---

📍 **집합 크기 및 확인**
```java
set.size();    // 집합 크기 반환
set.isEmpty(); // 집합이 비어있는지 확인 (true / false)
```

---

📍 **특정 원소 존재 여부 확인**
```java
set.contains(element); // 특정 원소 포함 여부 확인 (true / false)
```

---

📍 **집합 변환**
```java
set.toArray(new Type[0]); // 집합을 배열로 변환
```

---

📍 **집합 연산**
```java
set1.addAll(set2); // 합집합 (set1 ∪ set2)
set1.retainAll(set2); // 교집합 (set1 ∩ set2)
set1.removeAll(set2); // 차집합 (set1 - set2)
```

---

📍 **집합 복사**
```java
Set<Type> newSet = new HashSet<>(set); // 집합 복사
```

---

📍 **집합 초기화**
```java
set.clear(); // 집합의 모든 원소 제거
```
