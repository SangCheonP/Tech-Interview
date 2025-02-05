## **Map (맵)**

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
