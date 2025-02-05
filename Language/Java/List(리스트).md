## List(리스트)

<img src="https://javagoal.com/wp-content/uploads/2020/08/42.png">

<br>

📍 리스트 생성
```java
List<Integer> arrayList = new ArrayList<>(); // ArrayList 생성
List<Integer> linkedList = new LinkedList<>(); // LinkedList 생성
```

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
