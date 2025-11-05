## 🧩 Java Class Fundamentals Quiz

### 📍 Part 1. 기본 개념 (객관식)

**1.** 다음 중 자바에서 클래스 선언이 올바른 것은? <br>
A. `class myclass {}` <br>
B. `Class MyClass {}` <br>
C. `public class MyClass {}` <br>
D. `public MyClass class {}` <br>

---

**2.** 다음 중 *필드(Field)* 에 대한 설명으로 옳은 것은? <br>
A. 클래스 내에서 선언되며, 객체의 상태를 저장한다. <br>
B. 메서드 내부에서 선언되어야 한다. <br>
C. 반드시 `public` 이어야 한다. <br>
D. static 키워드를 반드시 가져야 한다. <br>

---

**3.** 다음 중 *캡슐화(encapsulation)* 개념을 가장 잘 설명하는 것은? <br>
A. 객체의 내부 데이터를 외부에서 직접 변경하지 못하도록 보호한다. <br>
B. 여러 클래스를 하나로 묶는 것 <br>
C. 상속 관계를 만드는 것 <br>
D. 인터페이스를 구현하는 것 <br>

---

**4.** 다음 중 *생성자(Constructor)* 에 대한 설명으로 옳지 않은 것은? <br>
A. 클래스 이름과 동일하다. <br>
B. 반환 타입이 없다. <br>
C. 반드시 명시적으로 선언해야 한다. <br>
D. 객체 생성 시 자동 호출된다. <br>

---

**5.** 다음 중 올바른 생성자 선언은? <br>
A. `public void Bicycle() {}` <br>
B. `Bicycle(int gear) { this.gear = gear; }` <br>
C. `int Bicycle() {}` <br>
D. `constructor Bicycle() {}` <br>

---

**6.** 다음 중 접근 제어자(Access Modifier)에 대한 설명으로 옳은 것은? <br>
A. `private` 멤버는 다른 클래스에서도 접근 가능하다. <br>
B. `public` 멤버는 모든 클래스에서 접근 가능하다. <br>
C. `protected` 멤버는 외부 클래스에서도 접근 불가하다. <br>
D. `default` 접근자는 항상 같은 패키지 내에서도 접근 불가하다. <br>

---

**7.** 다음 중 *super()* 키워드의 역할로 옳은 것은? <br>
A. 부모 클래스의 메서드를 재정의한다. <br>
B. 부모 클래스의 생성자를 호출한다. <br>
C. 현재 객체를 참조한다. <br>
D. 정적(static) 변수를 초기화한다. <br>

---

**8.** 다음 중 올바른 메서드 오버로딩(Overloading) 예시는? <br>
A. `void run()`, `void run()` <br>
B. `void run(int speed)`, `int run(int speed)` <br>
C. `void run(int speed)`, `void run(double speed)` <br>
D. `void run(int)`, `void run(int)` <br>

---

**9.** 다음 중 *MountainBike* 클래스가 *Bicycle* 클래스를 상속받을 때 올바른 선언은? <br>
A. `class MountainBike : Bicycle {}` <br>
B. `class MountainBike inherits Bicycle {}` <br>
C. `class MountainBike extends Bicycle {}` <br>
D. `class MountainBike implements Bicycle {}` <br>

---

**10.** 다음 중 올바른 문장은? <br>
A. 모든 클래스는 반드시 `extends Object`를 명시해야 한다. <br>
B. 클래스는 여러 개의 슈퍼클래스를 상속할 수 있다. <br>
C. 클래스는 인터페이스를 여러 개 구현할 수 있다. <br>
D. private 클래스는 파일의 최상단에 선언할 수 있다. <br>

---

### 📍 Part 2. 단답형 문제  <br>

**11.** 클래스 이름의 첫 글자는 (   )로 시작하는 것이 자바 명명 규칙이다. <br>
**12.** 메서드 이름은 일반적으로 (   )로 시작하는 동사 형태로 짓는다. <br>
**13.** 자바에서 모든 클래스는 암시적으로 (   ) 클래스를 상속받는다. <br>
**14.** 클래스 내부에 정의된 또 다른 클래스를 (   ) 클래스라고 한다. <br>
**15.** 파라미터가 없는 생성자를 (   ) 생성자라고 한다. <br>

---

### 📍 Part 3. 코드 퀴즈 (코드 완성/출력 예측)

**16. 다음 코드의 출력 결과는?**

```java
class Bicycle {
    int gear = 2;
    Bicycle() {
        System.out.println("Bicycle constructor");
    }
}

class MountainBike extends Bicycle {
    MountainBike() {
        System.out.println("MountainBike constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        MountainBike mb = new MountainBike();
    }
}
```

🟢 예상 출력:

```
________________________
```

---

**17. 다음 코드에서 컴파일 에러가 발생하는 이유를 설명하세요.**

```java
class SuperClass {
    public SuperClass(String msg) {
        System.out.println(msg);
    }
}

class SubClass extends SuperClass { }
```

---

**18. 다음 코드를 완성하세요.**

```java
public class Car {
    private int speed;

    // TODO: speed 값을 초기화하는 생성자를 작성하세요.
}
```

---

**19. 다음 코드의 실행 결과는?**

```java
class DataArtist {
    void draw(int i) { System.out.println("int"); }
    void draw(double d) { System.out.println("double"); }
}

public class Main {
    public static void main(String[] args) {
        DataArtist a = new DataArtist();
        a.draw(3.14f);
    }
}
```

🟢 출력:

```
________________________
```

---

**20. 다음 클래스 선언 중 올바른 것은 모두 고르시오.** <br>
A. `public class Hello {}` <br>
B. `private class Hello {}` <br>
C. `class Hello {}` <br>
D. `protected class Hello {}` <br>

---

## ✅ 보너스 (선택형 추가문항)

**21.** `super()`는 반드시 생성자의 (   ) 줄에 위치해야 한다. <br>
**22.** 기본 생성자를 컴파일러가 자동으로 추가하지 않는 경우는? <br>
**23.** 필드 접근을 제한하면서 외부에서 읽고 쓰게 하는 방법은? (힌트: getter/setter) <br>
**24.** `new Bicycle(30, 0, 8)`의 의미를 간단히 설명하시오. <br>
**25.** 클래스 내 메서드의 시그니처(Signature)는 어떤 두 요소로 구성되는가? <br>


