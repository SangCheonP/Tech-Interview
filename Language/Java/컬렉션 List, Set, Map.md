# Java 컬렉션: List, Set, Map

관련 개념을 한 문서에서 이어서 학습합니다.

## List

### List(리스트)

<img src="https://javagoal.com/wp-content/uploads/2020/08/42.png">

<br>

📍 리스트 생성
```java
List<Integer> arrayList = new ArrayList<>(); // ArrayList 생성
List<Integer> linkedList = new LinkedList<>(); // LinkedList 생성
```

<hr>

📍 원소 추가
```
list.add(element) : 리스트 끝에 원소 추가
list.add(index, element) : 특정 위치에 원소 추가
list.addAll(Collection c) : 여러 개의 원소 추가
```

<hr>

📍 원소 삭제
```
list.remove(index) : 특정 인덱스의 원소 삭제
list.remove(Integer.valueOf(value)) : 특정 값 삭제
list.clear() : 리스트의 모든 원소 삭제
```

<hr>

📍 원소 접근 및 변경
```
list.get(index) : 특정 인덱스의 원소 가져오기
list.set(index, element) : 특정 인덱스의 원소 변경
```

<hr>

📍 리스트 크기 및 탐색
```
list.size() : 리스트 크기 반환
list.contains(element) : 특정 값 포함 여부 확인
list.indexOf(element) : 특정 값의 첫 번째 등장 위치 반환
list.lastIndexOf(element) : 특정 값의 마지막 등장 위치 반환
```

<hr>

📍 리스트 정렬
```
Collections.sort(list) : 오름차순 정렬
Collections.sort(list, Collections.reverseOrder()) : 내림차순 정렬
list.sort((a, b) -> Integer.compare(a, b) : 오름차순 정렬;
```

<hr>

📍 리스트 변환
```
list.toArray(new Integer[0]) : 리스트 → 배열 변환
new ArrayList<>(Arrays.asList(array)) : 수정 가능한 리스트 변환
```

<hr>

📍 리스트 뒤집기 및 섞기
```
Collections.reverse(list) : 리스트 뒤집기
```

<hr>

📍 리스트 비교
```
list.equals(otherList) : 두 리스트 비교
```

## Set

### **Set (집합)**

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

## Map

### **Map (맵)**

<img src="https://miro.medium.com/v2/resize:fit:1086/1*b7bd4tJ7GiDYnvScHtCNTA.png">

<br>

📍 **맵 생성**
```java
Map<KeyType, ValueType> map = new HashMap<>();
Map<KeyType, ValueType> treeMap = new TreeMap<>(); // 키를 기준으로 정렬된 TreeMap 사용
Map<KeyType, ValueType> linkedHashMap = new LinkedHashMap<>(); // 입력된 순서대로 저장
```

---

📍 **원소 추가 및 갱신 (Put)**
```java
map.put(key, value);   // 키-값 쌍 추가 또는 갱신
map.putIfAbsent(key, value); // 키가 없을 경우에만 추가
```

---

📍 **원소 가져오기 (Get)**
```java
map.get(key);   // 키에 해당하는 값 반환 (없으면 null)
map.getOrDefault(key, defaultValue); // 키가 없으면 기본값 반환
```

---

📍 **원소 제거 (Remove)**
```java
map.remove(key);       // 특정 키의 원소 삭제
map.remove(key, value); // 특정 키-값 쌍이 일치할 때 삭제
```

---

📍 **맵 크기 및 확인**
```java
map.size();    // 맵의 크기 반환
map.isEmpty(); // 맵이 비어있는지 확인 (true / false)
```

---

📍 **특정 키 또는 값 존재 여부 확인**
```java
map.containsKey(key);   // 특정 키 존재 여부 확인
map.containsValue(value); // 특정 값 존재 여부 확인
```

---

📍 **맵 반복 및 순회**
```java
// 키를 기준으로 반복
for (KeyType key : map.keySet()) {
    System.out.println(key + " : " + map.get(key));
}

// 값만 반복
for (ValueType value : map.values()) {
    System.out.println(value);
}

// 키-값 쌍을 반복
for (Map.Entry<KeyType, ValueType> entry : map.entrySet()) {
    System.out.println(entry.getKey() + " : " + entry.getValue());
}
```

---

📍 **맵 변환**
```java
map.keySet().toArray(new KeyType[0]); // 키를 배열로 변환
map.values().toArray(new ValueType[0]); // 값을 배열로 변환
```

---

📍 **맵 초기화**
```java
map.clear(); // 맵의 모든 원소 제거
```

---

[다음: Stack, Queue, Deque와 PriorityQueue](<Stack, Queue, Deque와 PriorityQueue.md>)
