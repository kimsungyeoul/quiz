# 🧑‍💻 Java 클래스 코딩 문제

---

## 🧩 **Coding 1 — 기본 클래스 작성**

### 🧠 문제

다음 요구사항을 만족하는 `Book` 클래스를 작성하시오.

1. `title`, `author`, `price` 세 개의 **private 필드**를 가진다.
2. 생성자를 통해 세 필드를 모두 초기화할 수 있다.
3. `printInfo()` 메서드를 작성하여 다음과 같은 출력 형식을 가진다:

```
제목: 자바의 정석 / 저자: 남궁성 / 가격: 30000원
```

4. `BookTest` 클래스에서 객체를 생성하고 `printInfo()`를 호출하시오.

### ✅ 실행 예시

```java
public class BookTest {
    public static void main(String[] args) {
        Book book = new Book("자바의 정석", "남궁성", 30000);
        book.printInfo();
    }
}
```

**출력 결과**

```
제목: 자바의 정석 / 저자: 남궁성 / 가격: 30000원
```

---

## 🧩 **Coding 2 — 생성자 오버로딩**

### 🧠 문제

다음 조건에 맞게 `Rectangle` 클래스를 작성하시오.

1. `width`, `height` 필드(둘 다 int형)를 가진다.
2. 생성자를 두 개 작성한다.

   * (1) 매개변수 없는 기본 생성자: width=1, height=1
   * (2) 매개변수 두 개를 받는 생성자: width, height를 각각 초기화
3. `getArea()` 메서드를 작성한다. (가로×세로)
4. `printInfo()` 메서드를 작성하여 다음과 같이 출력한다:

```
사각형의 너비: 5, 높이: 3, 면적: 15
```

### ✅ 실행 예시

```java
public class RectangleTest {
    public static void main(String[] args) {
        Rectangle r1 = new Rectangle();
        Rectangle r2 = new Rectangle(5, 3);

        r1.printInfo();
        r2.printInfo();
    }
}
```

---

## 🧩 **Coding 3 — 상속과 super**

### 🧠 문제

부모 클래스 `Person`과 자식 클래스 `Student`를 작성하시오.

1. `Person` 클래스

   * 필드: `name`, `age`
   * 생성자: `Person(String name, int age)`
   * 메서드: `introduce()` →

     ```
     이름: 홍길동, 나이: 25
     ```

2. `Student` 클래스

   * `Person`을 상속받는다.
   * 필드: `studentId`
   * 생성자: `Student(String name, int age, String studentId)`
     → `super()`로 부모 생성자 호출
   * `introduce()` 메서드를 오버라이딩하여 다음처럼 출력:

     ```
     이름: 홍길동, 나이: 25, 학번: 202501
     ```

### ✅ 실행 예시

```java
public class Main {
    public static void main(String[] args) {
        Student s = new Student("홍길동", 25, "202501");
        s.introduce();
    }
}
```

---

## 🧩 **Coding 4 — 메서드 오버로딩**

### 🧠 문제

`Calculator` 클래스를 작성하시오.
다음 조건을 만족해야 한다.

1. `add` 메서드를 3가지 버전으로 오버로딩한다.

   * `int add(int a, int b)`
   * `double add(double a, double b)`
   * `int add(int a, int b, int c)`
2. 각 메서드는 두 수(또는 세 수)의 합을 반환한다.

### ✅ 실행 예시

```java
public class Main {
    public static void main(String[] args) {
        Calculator c = new Calculator();
        System.out.println(c.add(3, 4));        // 7
        System.out.println(c.add(2.5, 3.5));    // 6.0
        System.out.println(c.add(1, 2, 3));     // 6
    }
}
```

---

## 🧩 **Coding 5 — 컴파일 오류 분석**

### 🧠 문제

아래 코드를 읽고, **컴파일 오류가 발생하는 이유를 주석으로 설명**하시오.

```java
class Parent {
    public Parent(String name) {
        System.out.println("Parent 생성자 호출");
    }
}

class Child extends Parent {
    // 여기에 코드 없음
}

public class Main {
    public static void main(String[] args) {
        Child c = new Child();
    }
}
```

---

## **Coding 6 — private 필드와 getter/setter**

### 🧠 문제

`Account` 클래스를 작성하시오.

1. `owner`, `balance` 두 개의 **private 필드**를 가진다.
2. 생성자를 통해 `owner`와 `balance`를 초기화한다.
3. 다음 메서드를 작성한다.

   * `deposit(int amount)` : 잔액을 amount만큼 증가
   * `withdraw(int amount)` : 잔액이 부족하면 `"잔액 부족"` 출력
   * `getBalance()` : 현재 잔액 반환
   * `printInfo()` : `"예금주: 홍길동, 잔액: 10000원"` 형식으로 출력

### ✅ 실행 예시

```java
public class AccountTest {
    public static void main(String[] args) {
        Account acc = new Account("홍길동", 5000);
        acc.deposit(3000);
        acc.withdraw(2000);
        acc.printInfo();
    }
}
```

**출력 결과**

```
예금주: 홍길동, 잔액: 6000원
```

---

## **Coding 7 — 기본 생성자와 명시적 생성자**

### 🧠 문제

다음 요구사항에 맞는 `Dog` 클래스를 작성하시오.

1. 필드: `name`, `age`
2. 생성자 오버로딩

   * 기본 생성자: `name="이름없음"`, `age=0`
   * 매개변수 생성자: 전달된 값으로 필드 초기화
3. `bark()` 메서드: `"멍멍! 나는 땡이(3살)야!"` 형식으로 출력

### ✅ 실행 예시

```java
public class DogTest {
    public static void main(String[] args) {
        Dog d1 = new Dog();
        Dog d2 = new Dog("땡이", 3);

        d1.bark();
        d2.bark();
    }
}
```

**출력 결과**

```
멍멍! 나는 이름없음(0살)야!
멍멍! 나는 땡이(3살)야!
```

---

## **Coding 8 — this() 생성자 호출**

### 🧠 문제

아래 요구사항에 맞게 `Point` 클래스를 작성하시오.

1. 필드: `x`, `y` (int형)
2. 생성자 오버로딩

   * `Point()` → (0,0)
   * `Point(int x)` → (x,0)
   * `Point(int x, int y)` → (x,y)
3. 중복 코드를 줄이기 위해 `this()`를 사용하여 생성자 간 호출 구조를 작성할 것.
4. `print()` 메서드로 좌표 출력:

```
좌표: (10, 20)
```

### ✅ 실행 예시

```java
public class PointTest {
    public static void main(String[] args) {
        Point p1 = new Point();
        Point p2 = new Point(10);
        Point p3 = new Point(10, 20);

        p1.print();
        p2.print();
        p3.print();
    }
}
```

---

## **Coding 9 — 상속과 오버라이딩**

### 🧠 문제

아래 조건을 만족하는 두 클래스를 작성하시오.

1. `Shape` 클래스

   * 필드: `color`
   * 생성자: `Shape(String color)`
   * 메서드: `draw()` → `"도형을 그립니다."` 출력

2. `Circle` 클래스

   * `Shape` 상속
   * 추가 필드: `radius`
   * 생성자: `Circle(String color, double radius)` → 부모 생성자 호출
   * `draw()` 오버라이딩 → `"빨간색 원을 그립니다. (반지름: 3.0)"`

### ✅ 실행 예시

```java
public class ShapeTest {
    public static void main(String[] args) {
        Circle c = new Circle("빨간색", 3.0);
        c.draw();
    }
}
```

**출력 결과**

```
빨간색 원을 그립니다. (반지름: 3.0)
```

---

## **Coding 10 — 생성자 체이닝과 super**

### 🧠 문제

다음 조건을 만족하는 `Employee` 와 `Manager` 클래스를 작성하시오.

1. `Employee` 클래스

   * 필드: `name`, `salary`
   * 생성자: `Employee(String name, int salary)`
   * `printInfo()` → `"이름: 철수, 급여: 5000만원"`

2. `Manager` 클래스

   * `Employee` 상속
   * 필드: `department`
   * 생성자: `Manager(String name, int salary, String department)`
     → `super()`로 부모 생성자 호출
   * `printInfo()` 오버라이딩 → `"이름: 철수, 급여: 5000만원, 부서: 인사부"`

### ✅ 실행 예시

```java
public class Main {
    public static void main(String[] args) {
        Manager m = new Manager("철수", 5000, "인사부");
        m.printInfo();
    }
}
```

**출력 결과**

```
이름: 철수, 급여: 5000만원, 부서: 인사부
```

---

---

## **Coding 11 — 클래스 간 협력 (객체 사용)**

### 🧠 문제

`Student`와 `Course` 클래스를 작성하시오.

* `Student`

  * 필드: `name`, `age`
  * 생성자: `Student(String name, int age)`
  * `printInfo()` → `"학생 이름: 홍길동, 나이: 20"`

* `Course`

  * 필드: `courseName`, `student` (Student 타입)
  * 생성자: `Course(String courseName, Student student)`
  * `showCourse()` → `"강의명: Java, 수강생: 홍길동"`

### ✅ 실행 예시

```java
public class Main {
    public static void main(String[] args) {
        Student s = new Student("홍길동", 20);
        Course c = new Course("Java", s);
        c.showCourse();
    }
}
```

---

## **Coding 12 — 접근 제어자 실습**

### 🧠 문제

다음 조건을 만족하는 클래스를 작성하시오.

* `Person` 클래스

  * `private String name;`
  * `public void setName(String name)`
  * `public String getName()`
* `Main` 클래스에서 `p.name = "홍길동";` 을 시도하면 컴파일 오류가 발생함을 확인하고 이유를 주석으로 설명하시오.

---

## **Coding 13 — 필드 초기화와 디폴트 값**

### 🧠 문제

`Car` 클래스를 작성하시오.

1. 필드: `brand`, `speed`, `color`
2. 아무 생성자도 작성하지 말고, `printInfo()` 메서드에서 각 필드의 값을 출력하시오.
3. main()에서 `new Car()`로 객체를 생성했을 때의 출력 결과를 확인하시오.

💬 **출력 예시**

```
brand: null
speed: 0
color: null
```

---

## **Coding 14 — 메서드 오버로딩 심화**

### 🧠 문제

`Printer` 클래스를 작성하시오.

* `print(String s)` → `"출력: 문자열"`
* `print(int n)` → `"출력: 정수"`
* `print(double d)` → `"출력: 실수"`
* `print(String s, int count)` → 문자열을 count번 반복 출력

### ✅ 실행 예시

```java
public class Main {
    public static void main(String[] args) {
        Printer p = new Printer();
        p.print("Hello");
        p.print(10);
        p.print(3.14);
        p.print("Java", 3);
    }
}
```

**출력 결과**

```
출력: 문자열
출력: 정수
출력: 실수
Java
Java
Java
```

---

## **Coding 15 — 생성자 내부에서 메서드 호출**

### 🧠 문제

`Box` 클래스를 작성하시오.

1. 필드: `width`, `height`, `depth`
2. 생성자: 세 값을 초기화하고, 생성자 내부에서 `volume()` 메서드를 호출
3. `volume()` 메서드는 부피(가로×세로×높이)를 출력

### ✅ 실행 예시

```java
Box b = new Box(2, 3, 4);
```

**출력**

```
Box created. Volume = 24
```

---

## **Coding 16 — static 필드와 인스턴스 필드 구분**

### 🧠 문제

`Counter` 클래스를 작성하시오.

* 필드:

  * `static int totalCount` (전체 객체 생성 수 카운트)
  * `int id` (객체 개별 번호)
* 생성자:

  * 객체가 생성될 때마다 totalCount 증가
  * id = totalCount
* `print()` 메서드 → `"객체 번호: 3 (전체 생성된 객체 수: 3)"`

### ✅ 실행 예시

```java
Counter c1 = new Counter();
Counter c2 = new Counter();
Counter c3 = new Counter();
c3.print();
```

---

## **Coding 17 — super와 this 구분**

### 🧠 문제

`Parent`와 `Child` 클래스를 작성하시오.

* `Parent`

  * 필드: `name`
  * 생성자: `Parent(String name)`
  * `print()` → `"부모 이름: name"`

* `Child`

  * `Parent` 상속
  * 필드: `name`
  * 생성자: `Child(String parentName, String childName)`
    → `super(parentName)`
    → `this.name = childName`
  * `printAll()` → 부모 이름과 자식 이름 모두 출력

### ✅ 실행 예시

```java
Child c = new Child("아버지", "아들");
c.printAll();
```

**출력 결과**

```
부모 이름: 아버지
자식 이름: 아들
```

---

## **Coding 18 — 객체 배열**

### 🧠 문제

`Student` 클래스를 작성하고, 3명의 학생 객체를 배열로 관리하시오.

1. 필드: `name`, `score`
2. 생성자: `Student(String name, int score)`
3. `printInfo()` → `"이름: 홍길동, 점수: 90"`

### ✅ 실행 예시

```java
Student[] arr = {
    new Student("홍길동", 90),
    new Student("이몽룡", 85),
    new Student("성춘향", 95)
};
for (Student s : arr) {
    s.printInfo();
}
```

---

## **Coding 19 — 상속 관계에서 메서드 오버라이딩 + super**

### 🧠 문제

`Animal`과 `Dog` 클래스를 작성하시오.

* `Animal`

  * 메서드: `sound()` → `"동물이 소리를 냅니다."`
* `Dog`

  * `Animal` 상속
  * `sound()` 오버라이딩
    → `"멍멍!" 출력 후 부모 sound()도 호출`

### ✅ 실행 예시

```java
Dog d = new Dog();
d.sound();
```

**출력 결과**

```
멍멍!
동물이 소리를 냅니다.
```

---

## **Coding 20 — 생성자 연결 오류 찾기**

### 🧠 문제

다음 코드에서 컴파일 오류가 발생합니다.
오류 원인을 설명하고 수정 코드를 작성하시오.

```java
class Parent {
    public Parent(String name) { }
}

class Child extends Parent {
    public Child() {
        System.out.println("Child 생성자");
    }
}
```

💬 **정답 예시**

```java
// 오류 이유: Parent 클래스에 기본 생성자가 없기 때문에
// Child() 생성자 내부에서 암묵적으로 super() 호출 시 에러 발생
// 수정 방법: Child 생성자에서 super("이름")을 명시적으로 호출해야 함.
```

---

