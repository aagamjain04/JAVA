
## OOPS Overview
- **OOPs** means Object-Oriented Programming.
- Object represents real-world entities like Car, ATM, Bike, etc.

### Procedural vs OOPS
| Procedural Programming            | OOPS                            |
| --------------------------------- | ------------------------------- |
| Program is divided into functions | Program is divided into objects |
| No data hiding                    | Data hiding is possible         |
| Overloading not possible          | Overloading is possible         |
| Inheritance not possible          | Inheritance is possible         |
| No code reusability               | Code reusability is present     |
| Examples: Pascal, C, FORTRAN      | Examples: Java, C#, Python, C++ |

---

## Objects & Classes
- **Object** has two things:
  - Properties / State
  - Behavior / Function

**Examples:**
- Dog → Properties: Age, Color, Breed; Behavior: Bark, Sleep, Eat
- Car → Properties: Color, Type, Brand; Behavior: Drive, Brake, Accelerate

- **Class** is a blueprint/template for objects.
- Multiple objects can be created from a single class.

```java
class Student {

	//properties
    int age;
    String name;
    String address;
	//behavior
    void updateAddress() { ... }
    int getAge() { return age; }
}

Student engStu = new Student();
```

---

## Pillars of OOPS

### 1. Data Abstraction
- Hides internal implementation and shows only essential functionality.
- Achieved through **interfaces** and **abstract classes**.

**Examples:**
- Car brake pedal – we know it reduces speed but not how it works internally.
- Cellphone call – abstracted from the user.

**Advantages:**
- Increases security & confidentiality.

```java
interface Car {
    void applyBrake();
    void incSpeed();
    void handbrake();
}

class CarImp implements Car {
    public void applyBrake() { ... }
    public void incSpeed() { ... }
    public void handbrake() { ... }
}
```

---

### 2. Encapsulation
- Bundling data and methods that operate on that data in a single unit.
- Also known as **data hiding**.

**Steps:**
1. Declare variables as `private`.
2. Provide `public` getters and setters.

**Advantages:**
- Loosely coupled code.
- Better security and access control.

```java
class Dog {
    private String color;

    String getColor() { return this.color; }
    void setColor(String color) { this.color = color; }
}

Dog lab = new Dog();
lab.setColor("Black");
System.out.println(lab.getColor()); // Output: Black
```

---

### 3. Inheritance
- A class can inherit properties and methods from a parent class using `extends`.
- Promotes **code reusability** and enables **polymorphism**.


- #### Types of Inheritance
- **Single Inheritance** → One class inherits from another.
- **Multilevel Inheritance** → A class inherits from another class, which in turn inherits from another.
- **Hierarchical Inheritance** → Multiple classes inherit from the same parent.
- **Multiple Inheritance** → Class inherit from multiple parents. Not directly supported in Java (possible through **interfaces**). (Diamond Problem)


```java
class Vehicle {
    boolean engine;
    boolean getEngine() { return this.engine; }
}

class Car extends Vehicle {
    String type;
    String getCarType() { return this.type; }
}

Car swift = new Car();
System.out.println(swift.getEngine()); // Works
Vehicle v = new Vehicle();
System.out.println(v.getCarType()); // Error
```



## Diamond Problem in Java

- The Diamond Problem arises in languages that support **multiple inheritance of classes** (like C++).
- **Java avoids it** by:
  - Not allowing multiple inheritance with classes.
  - Allowing multiple inheritance with **interfaces**, but enforcing explicit conflict resolution.

### Example

```java
interface A {
    default void show() {
        System.out.println("From A");
    }
}

interface B {
    default void show() {
        System.out.println("From B");
    }
}

// Class implementing both interfaces
class C implements A, B {
    @Override
    public void show() {
        // Explicitly resolve the conflict
        A.super.show(); // or B.super.show()
        System.out.println("Resolved in C");
    }
}

public class Main {
    public static void main(String[] args) {
        C obj = new C();
        obj.show();
    }
}
```



---

### 4. Polymorphism
- **Poly** = Many, **Morphism** = Forms.
- Same method behaves differently in different situations.

**Examples:**
- Person → Father, Husband, Employee.
- Water → Liquid, Solid, Gas.

**Types:**
1. **Compile Time (Static)** → Method Overloading
2. **Runtime (Dynamic)** → Method Overriding

```java
// Overloading
class Sum {
    int doSum(int a, int b) { return a + b; }
    int doSum(int a, int b, int c) { return a + b + c; }
}

// Overriding
class A {
    int getEngine() { return 1; }
}

class B extends A {
    int getEngine() { return 2; }
}

B obj = new B();
System.out.println(obj.getEngine()); // Output: 2
```

---

## Relationships in OOPS

- **IS-A relationship**
  - Achieved through inheritance.
  - Example: Dog IS-A Animal.

- **HAS-A relationship**
  - Achieved through composition/association.
  - Example: Bike HAS-A Engine, School HAS Students.

**Association Types:**
- **Aggregation**: Both objects can exist independently, means ending of one object will not end other object (e.g., Student & School).
- **Composition**: One object’s lifecycle depends on another (e.g., Engine & Car).
