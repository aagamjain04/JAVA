
## What is Java?

**Java** is a high-level, **platform-independent**, **object-oriented** programming language known for its **portability** —  
_"Write Once, Run Anywhere (WORA)"_.

### Key Features:
- **Platform Independent** – Code runs on any system with JVM.
- **Object-Oriented** – Supports OOP concepts (Encapsulation, Inheritance, Polymorphism, Abstraction).
- **Secure** – No explicit pointers, runs inside JVM sandbox.
- **Robust** – Strong memory management, exception handling.
- **Multithreaded** – Built-in thread support.
- **Portable** – Bytecode can run across platforms.

---

## 3 Main Components of Java

| Component | Full Form                | Description                                                                                               |
| --------- | ------------------------ | --------------------------------------------------------------------------------------------------------- |
| **JVM**   | Java Virtual Machine     | Executes bytecode, converts it to machine code using **JIT (Just-In-Time Compiler)**. Platform-dependent. |
| **JRE**   | Java Runtime Environment | Contains **JVM + Class Libraries**. Required to **run** Java programs.                                    |
| **JDK**   | Java Development Kit     | Contains **JRE + Development Tools (Compiler, Debugger, Jar)**. Required to **develop** Java programs.    |

### Relationship:
```
JDK = JRE + Development Tools
JRE = JVM + Libraries
```

### Diagram:
```
[Source Code] --(Compiler)--> [Bytecode] --(JVM)--> [Machine Code]
```

**Platform Independence:**  
Bytecode is the same across OS; only JVM differs per platform.

---

## JVM (Java Virtual Machine)

- Abstract machine (does not physically exist).
- Converts **bytecode → native machine code**.
- Ensures memory management via **Garbage Collection**.
- Has **JIT compiler** for performance optimization.

**Responsibilities:**
- Class loader subsystem
- Bytecode verifier
- Interpreter & JIT compiler
- Memory management
- Security checks

---

## JRE (Java Runtime Environment)

- Provides runtime environment for Java code.
- Contains:
  - **JVM**
  - **Core class libraries**
- Enables execution of already compiled programs.

> Note: You can **run** Java programs with JRE, but not **develop** them.

---

## JDK (Java Development Kit)

- Full Java development environment.
- Includes:
  - Compiler (`javac`)
  - Debugger
  - Documentation tools
  - Jar utility

> Note: You need **JDK** to compile and run Java applications.

---


## How Java Achieves Platform Independence

1. Source code (`.java`) compiled into **bytecode** (`.class`).
2. Bytecode runs on **JVM**, which is platform-dependent.
3. Hence, Java program runs on any OS with its JVM.

```
Write Once → Compile Once → Run Anywhere
```

---

## Compilation Flow

```
.java  --(javac)-->  .class  --(JVM)-->  Machine Code
```

**Steps:**
1. **javac** compiles Java source → bytecode.
2. **java** command runs bytecode via JVM.
3. **JIT compiler** optimizes hot code paths at runtime.

---


## Bonus — JIT Compiler

**JIT (Just-In-Time)** compiler improves performance by:
- Translating frequently executed bytecode sections into native code.
- Reducing interpretation overhead.
- Performing optimizations at runtime.

---

## Quick Summary Table

| Concept | Key Point |
|----------|------------|
| **Java** | Platform-independent OOP language |
| **JVM** | Executes bytecode (platform-dependent) |
| **JRE** | JVM + Libraries (for running) |
| **JDK** | JRE + Compiler + Tools (for development) |
| **Bytecode** | Intermediate form of Java code |
| **JIT Compiler** | Converts bytecode to native code at runtime |
| **WORA** | Write Once, Run Anywhere |

---
