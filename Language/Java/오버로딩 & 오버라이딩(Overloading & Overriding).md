# 오버로딩 & 오버라이딩(Overloading & Overriding)
## 오버로딩
```
같은 이름의 메서드를 매개변수의 개수나 타입을 다르게 정의하는 것

* 메서드 이름은 같지만, 매개변수의 시그니처(타입, 개수, 순서)가 다릅
```

### 특징
- 하나의 클래스 내에서 사용됨

- 반환 타입은 오버로딩의 기준이 되지 않음

- **컴파일 타임**에 어떤 메서드가 호출될지 결정됨

### 예제 코드
```
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(2, 3));           // 5
        System.out.println(calc.add(2.5, 3.5));       // 6.0
        System.out.println(calc.add(1, 2, 3));        // 6
    }
}
```

<br>

## 오버라이딩
```
부모 클래스의 메서드를 자식 클래스에서 재정의하는 것
```

<br>

### 특징
- 상속 관계에서만 사용됨

- **부모 클래스의 메서드와 시그니처(이름, 매개변수, 반환 타입)가 완전히 동일**해야 함

- **@Override** 어노테이션을 붙여 코드 가독성을 높이고 컴파일러가 올바르게 오버라이딩했는지 검사

- **런타임**에 결정됨

<br>

### 예제 코드
```
class Parent {
    void display() {
        System.out.println("Parent 클래스의 display 메서드");
    }
}

class Child extends Parent {
    @Override
    void display() {
        System.out.println("Child 클래스의 display 메서드");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent obj = new Child();
        obj.display(); // "Child 클래스의 display 메서드"
    }
}
```