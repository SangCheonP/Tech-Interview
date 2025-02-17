# Java `String.format()` 정리

## 1. 정수 포맷팅
### 기본적인 숫자 포맷팅
| 포맷팅 | 설명 | 입력 값 (`n`) | 결과 |
|--------|------|------|------|
| `%d` | 기본 정수 출력 | `5` | `"5"` |
| `%03d` | 최소 3자리, 빈자리는 `0`으로 채움 | `1` | `"001"` |
| `%05d` | 최소 5자리, `0`으로 채움 | `42` | `"00042"` |

```java
System.out.println(String.format("%03d", 1));  // "001"
System.out.println(String.format("%05d", 42)); // "00042"
```

---
<br>

## 2. 실수 포맷팅
### 기본적인 실수 포맷팅
| 포맷팅 | 설명 | 입력 값 (`x`) | 결과 |
|--------|------|------|------|
| `%.2f` | 소수점 둘째 자리까지 반올림 | `1.23456` | `"1.23"` |
| `%.3f` | 소수점 셋째 자리까지 반올림 | `1.2` | `"1.200"` |
| `%07.2f` | 최소 7자리 확보 후 `0` 채움 | `1.23` | `"0001.23"` |
| `%+08.2f` | 부호(`+/-`) 포함, 총 8자리 확보 | `12.3` | `"+0012.30"` |
| `%-8.2f` | 8자리 확보 후 왼쪽 정렬 | `5.67` | `"5.67    "` |

```java
System.out.println(String.format("%.2f", 1.23456)); // "1.23"
System.out.println(String.format("%07.2f", 1.23));  // "0001.23"
System.out.println(String.format("%+08.2f", 12.3)); // "+0012.30"
System.out.println(String.format("%-8.2f", 5.67));  // "5.67    "
```

---
<br>

## 3. 실수 포맷팅 (내림, 버림, 올림)
### 내림 (floor)
```java
double value = 1.987;
double flooredValue = Math.floor(value * 100) / 100;
System.out.println(String.format("%.2f", flooredValue)); // "1.98"
```

### 버림 (truncate)
```java
double value = 1.987;
double truncatedValue = ((int) (value * 100)) / 100.0;
System.out.println(String.format("%.2f", truncatedValue)); // "1.98"
```

### 올림 (ceil)
```java
double value = 1.981;
double ceiledValue = Math.ceil(value * 100) / 100;
System.out.println(String.format("%.2f", ceiledValue)); // "1.99"
```

| 연산 | 설명 | 예제 값 (1.987) | 결과 (`%.2f` 포맷) |
|------|------|------|------|
| `Math.floor(value * 100) / 100` | **내림** | `1.987` | `"1.98"` |
| `((int) (value * 100)) / 100.0` | **버림** | `1.987` | `"1.98"` |
| `Math.ceil(value * 100) / 100` | **올림** | `1.981` | `"1.99"` |

---
<br>

## 4. `String.format()` 정리
### 정수 (`%d`)
- `%d` → 기본 정수 출력  
- `%03d` → 최소 3자리 확보, `0`으로 채움  
- `%+d` → 부호(`+/-`) 포함

### 실수 (`%f`)
- `%.2f` → 소수점 둘째 자리까지 표시  
- `%07.2f` → 총 7자리 확보, `0`으로 패딩  
- `%+08.2f` → 부호 포함, 총 8자리 확보  
- `%-8.2f` → 왼쪽 정렬  

### 반올림, 내림, 버림, 올림
- **반올림**: `String.format("%.2f", value);`
- **내림**: `Math.floor(value * 100) / 100`
- **버림**: `((int) (value * 100)) / 100.0`
- **올림**: `Math.ceil(value * 100) / 100`
