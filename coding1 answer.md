# 🧑‍💻 **Java 클래스 코딩 문제 정답**

---

## ✅ **Coding 1 — Book 클래스**

```java
public class Book {
    private String title;
    private String author;
    private int price;

    public Book(String title, String author, int price) {
        this.title = title;
        this.author = author;
        this.price = price;
    }

    public void printInfo() {
        System.out.println("제목: " + title + " / 저자: " + author + " / 가격: " + price + "원");
    }
}
```

---

## ✅ **Coding 2 — Rectangle 클래스**

```java
public class Rectangle {
    int width;
    int height;

    public Rectangle() {
        this.width = 1;
        this.height = 1;
    }

    public Rectangle(int width, int height) {
        this.width = width;
        this.height = height;
    }

    public int getArea() {
        return width * height;
    }

    public void printInfo() {
        System.out.println("사각형의 너비: " + width + ", 높이: " + height + ", 면적: " + getArea());
    }
}
```

---

## ✅ **Coding 3 — 상속과 super**

```java
class Person {
    protected String name;
    protected int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("이름: " + name + ", 나이: " + age);
    }
}

class Student extends Person {
    private String studentId;

    public Student(String name, int age, String studentId) {
        super(name, age); // 부모 생성자 호출
        this.studentId = studentId;
    }

    @Override
    public void introduce() {
        System.out.println("이름: " + name + ", 나이: " + age + ", 학번: " + studentId);
    }
}
```

---

## ✅ **Coding 4 — Calculator 클래스**

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }

    public int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

---

## ✅ **Coding 5 — 컴파일 오류 분석**

```java
/*
오류 이유:
Parent 클래스에는 기본 생성자(파라미터 없는 생성자)가 없기 때문에,
Child 클래스가 super()를 자동으로 호출할 때 적절한 생성자를 찾을 수 없음.
*/

class Parent {
    public Parent(String name) {
        System.out.println("Parent 생성자 호출");
    }
}

class Child extends Parent {
    public Child() {
        super("기본 이름"); // 부모 생성자를 명시적으로 호출해야 함
    }
}
```

---

## ✅ **Coding 6 — Account 클래스**

```java
public class Account {
    private String owner;
    private int balance;

    public Account(String owner, int balance) {
        this.owner = owner;
        this.balance = balance;
    }

    public void deposit(int amount) {
        balance += amount;
    }

    public void withdraw(int amount) {
        if (balance < amount) {
            System.out.println("잔액 부족");
        } else {
            balance -= amount;
        }
    }

    public int getBalance() {
        return balance;
    }

    public void printInfo() {
        System.out.println("예금주: " + owner + ", 잔액: " + balance + "원");
    }
}
```

---

## ✅ **Coding 7 — Dog 클래스**

```java
public class Dog {
    private String name;
    private int age;

    public Dog() {
        this.name = "이름없음";
        this.age = 0;
    }

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void bark() {
        System.out.println("멍멍! 나는 " + name + "(" + age + "살)야!");
    }
}
```

---

## ✅ **Coding 8 — Point 클래스**

```java
public class Point {
    int x;
    int y;

    public Point() {
        this(0, 0); // this()로 다른 생성자 호출
    }

    public Point(int x) {
        this(x, 0);
    }

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public void print() {
        System.out.println("좌표: (" + x + ", " + y + ")");
    }
}
```

---

## ✅ **Coding 9 — Shape / Circle 클래스**

```java
class Shape {
    protected String color;

    public Shape(String color) {
        this.color = color;
    }

    public void draw() {
        System.out.println("도형을 그립니다.");
    }
}

class Circle extends Shape {
    private double radius;

    public Circle(String color, double radius) {
        super(color);
        this.radius = radius;
    }

    @Override
    public void draw() {
        System.out.println(color + " 원을 그립니다. (반지름: " + radius + ")");
    }
}
```

---

## ✅ **Coding 10 — Employee / Manager**

```java
class Employee {
    protected String name;
    protected int salary;

    public Employee(String name, int salary) {
        this.name = name;
        this.salary = salary;
    }

    public void printInfo() {
        System.out.println("이름: " + name + ", 급여: " + salary + "만원");
    }
}

class Manager extends Employee {
    private String department;

    public Manager(String name, int salary, String department) {
        super(name, salary);
        this.department = department;
    }

    @Override
    public void printInfo() {
        System.out.println("이름: " + name + ", 급여: " + salary + "만원, 부서: " + department);
    }
}
```

---

## ✅ **Coding 11 — Student / Course 협력**

```java
class Student {
    String name;
    int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void printInfo() {
        System.out.println("학생 이름: " + name + ", 나이: " + age);
    }
}

class Course {
    String courseName;
    Student student;

    public Course(String courseName, Student student) {
        this.courseName = courseName;
        this.student = student;
    }

    public void showCourse() {
        System.out.println("강의명: " + courseName + ", 수강생: " + student.name);
    }
}
```

---

## ✅ **Coding 12 — 접근 제어자**

```java
class Person {
    private String name;

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

/*
Main 클래스에서 다음 코드를 작성하면 오류 발생:
Person p = new Person();
p.name = "홍길동"; // ❌ private 필드는 외부에서 직접 접근 불가
*/
```

---

## ✅ **Coding 13 — Car 클래스 (기본값 확인)**

```java
public class Car {
    String brand;
    int speed;
    String color;

    public void printInfo() {
        System.out.println("brand: " + brand);
        System.out.println("speed: " + speed);
        System.out.println("color: " + color);
    }
}
```

---

## ✅ **Coding 14 — Printer 오버로딩**

```java
public class Printer {
    public void print(String s) {
        System.out.println("출력: 문자열");
        System.out.println(s);
    }

    public void print(int n) {
        System.out.println("출력: 정수");
        System.out.println(n);
    }

    public void print(double d) {
        System.out.println("출력: 실수");
        System.out.println(d);
    }

    public void print(String s, int count) {
        for (int i = 0; i < count; i++) {
            System.out.println(s);
        }
    }
}
```

---

## ✅ **Coding 15 — Box 클래스**

```java
public class Box {
    int width;
    int height;
    int depth;

    public Box(int width, int height, int depth) {
        this.width = width;
        this.height = height;
        this.depth = depth;
        volume();
    }

    public void volume() {
        int v = width * height * depth;
        System.out.println("Box created. Volume = " + v);
    }
}
```

---

## ✅ **Coding 16 — Counter (static)**

```java
public class Counter {
    static int totalCount = 0;
    int id;

    public Counter() {
        totalCount++;
        id = totalCount;
    }

    public void print() {
        System.out.println("객체 번호: " + id + " (전체 생성된 객체 수: " + totalCount + ")");
    }
}
```

---

## ✅ **Coding 17 — super와 this 구분**

```java
class Parent {
    String name;

    public Parent(String name) {
        this.name = name;
    }

    public void print() {
        System.out.println("부모 이름: " + name);
    }
}

class Child extends Parent {
    String name;

    public Child(String parentName, String childName) {
        super(parentName); // 부모 이름 설정
        this.name = childName; // 자식 이름 설정
    }

    public void printAll() {
        super.print(); // 부모 메서드 호출
        System.out.println("자식 이름: " + name);
    }
}
```

---

## ✅ **Coding 18 — Student 배열**

```java
public class Student {
    String name;
    int score;

    public Student(String name, int score) {
        this.name = name;
        this.score = score;
    }

    public void printInfo() {
        System.out.println("이름: " + name + ", 점수: " + score);
    }
}
```

---

## ✅ **Coding 19 — Animal / Dog 오버라이딩**

```java
class Animal {
    public void sound() {
        System.out.println("동물이 소리를 냅니다.");
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("멍멍!");
        super.sound(); // 부모 메서드 호출
    }
}
```

---

## ✅ **Coding 20 — 생성자 오류 수정**

```java
class Parent {
    public Parent(String name) { }
}

class Child extends Parent {
    public Child() {
        super("홍길동"); // 부모 생성자를 명시적으로 호출해야 함
        System.out.println("Child 생성자");
    }
}
```

---

# 📘 **요약**

| 구분    | 핵심 개념                              |
| ----- | ---------------------------------- |
| 1~5   | 클래스 기본 구조, 생성자, 상속, 오버로딩, super    |
| 6~10  | 접근 제어자, 캡슐화, this/super, 오버라이딩     |
| 11~15 | 객체 간 협력, 기본값, 생성자 체이닝, static 변수   |
| 16~20 | 상속 관계의 동작 원리, super/this 구분, 오류 분석 |

---

원하신다면 이 답안들을

* 📗 **“문제 + 정답” PDF 시험지형**
  또는
* 💻 **20문항 실습용 Java 프로젝트(zip)**
  형태로 자동 생성해드릴 수 있습니다.

어떤 형식으로 드릴까요?
예: “정답 포함 PDF로 만들어줘” / “Eclipse용 zip 프로젝트로 만들어줘”
