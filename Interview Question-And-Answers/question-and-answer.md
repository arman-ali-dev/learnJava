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
JVM (Java Virtual Machine) → Runs Java programs by converting bytecode into machine code. It is platform-dependent.</br>
JRE (Java Runtime Environment) → Provides everything needed to run Java programs, including JVM + libraries.</br>
JDK (Java Development Kit) → Contains JRE + development tools (compiler, debugger, etc.) to write and compile Java programs.</br>

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

## 10. What is the difference between checked and unchecked exceptions?
### Checked Exception –
These are checked at compile-time, and you must handle them using try-catch or throws. (e.g., IOException, SQLException).

### Unchecked Exception –
These occur at runtime, and the compiler does not force you to handle them. (e.g., NullPointerException, ArrayIndexOutOfBoundsException).

## 11. What are the main features of Java?
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
Java automatically removes unused objects to free memory. 

## 12. What is the difference between == and .equals() in Java?
### == (Reference Comparison) –
It checks if two variables point to the same memory location.

### .equals() (Content Comparison) – 
It checks if the values inside the objects are the same (if overridden). 

## 13. What is a constructor in Java? Can we have multiple constructors in a class?
A constructor in Java is a special method used to initialize objects when they are created. It has the same name as the class and no return type.

Yes, we can have multiple constructors in a class using constructor overloading, where each constructor has different parameters.

## 14. What is diffrence between Error and Exception?
### Error –
Big problems in the program that cannot be fixed or handled, like system crashes. (e.g., OutOfMemoryError).

### Exception –
Small issues in the program that can be fixed using try-catch, like wrong inputs. (e.g., NullPointerException). 

## 15. What is dependency injection in Spring Boot? How does it work?

### What is Dependency Injection in Spring Boot?
Dependency Injection (DI) is a design pattern in Spring Boot that automatically provides required objects (dependencies) to a class instead of creating them manually. It makes the code more flexible and easier to maintain. Spring handles object creation and management, so we don’t need to use the new keyword. DI is implemented using annotations like @Autowired, @Service, and @Component.

### How Does Dependency Injection Work?
1️. Spring creates and manages objects (Beans) automatically.</br>
2️. It injects these objects where needed, instead of us manually creating them.</br>
3️. @Autowired tells Spring to inject the required dependency.</br>
4️. This improves code reusability, testability, and maintainability.</br>

## 16. What is Wrapper Class?
Wrapper classes in Java are used to convert primitive data types into objects. They allow primitives to be used in collections like ArrayList and provide useful utility methods.

## 17. What is Autoboxing and Unboxing?
<b>Autoboxing:</b>
Autoboxing is the automatic conversion of a primitive type into its corresponding wrapper class object. For example, int automatically converts to Integer.

<b>Unboxing:</b>
Unboxing is the automatic conversion of a wrapper class object back into its corresponding primitive type. For example, Integer automatically converts to int.

## 18. What is a throw vs. throws?
<b>throw:</b>
The throw keyword is used to manually generate (throw) an exception inside a method. It is followed by an exception object, like throw new ArithmeticException("Error");.

<b>throws:</b>
The throws keyword is used in a method declaration to indicate that the method might throw one or more exceptions. It tells the caller to handle the exception, like void readFile() throws IOException {}.

## 19. What is Lambda Expression?
A lambda expression is a short way to write anonymous functions in Java, allowing you to pass behavior as an argument. It is mainly used with functional interfaces to make code shorter and more readable.

## 20. What is Functional Intreface?
A functional interface is an interface with only one abstract method, mainly used with lambda expressions. It makes code shorter and cleaner by allowing us to pass function logic as a parameter.

## 21. Can the "main()" method be overridden in Java?
In Java, the main() method cannot be overridden because it is static, meaning it belongs to the class, not an object. However, a subclass can define its own main() method, but this is called method hiding, not overriding.

## 22. Is it possible to overload the "main()" method in Java?
Yes, main() method can be overloaded in Java by defining multiple main() methods with different parameters. However, JVM only calls main(String[] args) as the entry point, and other overloaded versions must be called manually.

## 23. Can the "main" method be declared as "final" in Java?
Yes, the main() method can be declared as final in Java, but it has no special effect. Since main() is static, it cannot be overridden anyway, and the program will run normally.

## 24. Explain the concept of object cloning in Java.
Object Cloning in Java means creating an exact copy of an object using the clone() method of the Object class. The class must implement Cloneable and override clone() to avoid errors. By default, cloning creates a shallow copy.

## 25. Differentiate between deep copy and shallow copy in Java.
<strong>Shallow Copy:</strong> Shallow copy copies object references instead of creating new objects. If one object changes, the other also gets affected.</br>
<strong>Deep Copy:</strong>: creates a completely new object with its own copies of data. Changes in one object don’t affect the other.

## 26. Highlight the importance of using a singleton object in Java.
A Singleton object ensures that only one object of a class is created and used everywhere. This saves memory, avoids duplicate objects, and is useful for logging, databases, and caching.

## 27. Is it possible to override a private method in a class if the class itself is declared as final?
A private method cannot be overridden because it is not inherited by subclasses. A final class cannot be extended, so no methods (including public or protected ones) can be overridden.
