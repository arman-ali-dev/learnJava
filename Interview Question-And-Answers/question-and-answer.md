## 1. What is the difference between "super" and "this" in Core Java?

### this:
this refers to the current instance of the class. It is used to access instance variables, methods, or constructors of the same class.
### super
super refers to the parent (superclass) instance. It is used to access parent class methods, constructors, or hidden variables.

## 2. Explain the usage of "super()" and "this()" calls in constructors in Java.
### ✅ super():
Calls the parent class constructor and must be the first statement in the child class constructor.

### ✅ this():
Calls another constructor of the same class and must be the first statement in the constructor.

## 3. Differentiate between a "static" method and a "static" block in Java.

### ✅ static method:
A method that belongs to the class, not instances, and can be called without creating an object. It is used for utility functions and operates only on static data.

### ✅ static block:
A block that executes automatically when the class is loaded into memory. It is used for initializing static variables or performing setup tasks before the main method runs.

## 4. Describe the components of the JVM architecture, including Classloader, Bytecode Verifier, Memory Area, and Execution Engine.

### ClassLoader:
Loads .class files into memory, verifies, and links them before preparing them for execution.

### Bytecode Verifier:
Checks the loaded bytecode to ensure there are no security issues and that JVM rules are followed.

### Memory Area
The memory management part of the JVM, divided into different sections:

#### Method Area → Stores class-level data like metadata and static variables.
#### Heap → Stores objects and instance variables.
#### Stack → Stores local variables and method calls for execution.
#### PC Register → Tracks the current instruction being executed.
#### Native Method Stack → Manages the execution of native (non-Java) methods.

### Execution Engine:
Converts bytecode into machine code and executes it through the CPU. It consists of an Interpreter (executes code line by line) and a JIT Compiler (optimizes for faster execution). 

## 5. How is Java a platform-independent language?
Java is platform-independent because its code is converted into bytecode, which can run on any operating system using the JVM (Java Virtual Machine).
Its main principle is "Write Once, Run Anywhere."

## 6. What is the difference between JVM, JRE, and JDK?
JVM (Java Virtual Machine) → Runs Java programs by converting bytecode into machine code. It is platform-dependent.
JRE (Java Runtime Environment) → Provides everything needed to run Java programs, including JVM + libraries.
JDK (Java Development Kit) → Contains JRE + development tools (compiler, debugger, etc.) to write and compile Java programs.

<b>👉 JDK is for developers, JRE is for running Java apps, and JVM is the core engine that executes Java code.</b>

## 7. What is the difference between final, finally, and finalize?
final → A keyword that makes a variable constant, prevents method overriding, and stops class inheritance.
finally → A block that always executes after exception handling, whether an exception occurs or not.
finalize() → A method that runs before an object is garbage collected to perform cleanup tasks.

## 8. What is the difference between String, StringBuffer, and StringBuilder?
String → Immutable class, meaning once created, it cannot be changed; any modification creates a new object.
StringBuffer → Mutable class, meaning it can be changed without creating a new object and is thread-safe (synchronized).
StringBuilder → Similar to StringBuffer (mutable), but not thread-safe, making it faster in single-threaded environments.

## 9. How does garbage collection work in Java?
Garbage collection in Java automatically frees memory by removing objects that are no longer reachable. The JVM's garbage collector identifies and deletes unused objects to prevent memory leaks.

## 10. What is the difference between HashMap and HashTable?
## 11. How do multithreading and synchronization work in Java?
## 12. What is the difference between checked and unchecked exceptions?

## 13. What are Java 8 features? How do lambda expressions and streams work?
## 14. How does Dependency Injection work in the Spring Framework?

## 15. What are the main features of Java?
### Platform Independent –
Java code runs on any device with a JVM, no need to rewrite.
### Object-Oriented –
Java follows real-world object-based programming (OOP concepts).
### Simple & Easy to Learn –
Java has clean syntax and no complex features like pointers.
### Secure –
Java has built-in security features to protect from threats.
### Robust & Reliable –
Java handles errors well and manages memory automatically.
### Multithreading Support –
Java can run multiple tasks at the same time.
### High Performance –
Java uses JIT compiler to make execution faster.
### Distributed Computing –
Java supports features to create network-based applications.
### Rich API & Open Source Libraries –
Java provides many built-in tools and frameworks.
### Automatic Memory Management –
Java automatically removes unused objects to free memory. 🚀
