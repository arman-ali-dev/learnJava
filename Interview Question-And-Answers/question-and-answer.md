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

## 28. Can changes be made to a final or immutable class using reflection in Java?
Using reflection, we can modify even final or immutable classes in Java by accessing and changing their private fields. However, this is not recommended because it can break security and stability.

## 29. What is the garbage collector algorithm used by the JVM, and is it the same for every operating system?
JVM uses different Garbage Collection (GC) algorithms like Serial GC, Parallel GC, CMS GC, G1 GC, and ZGC to automatically manage memory. The default GC depends on the Java version and system configuration. It is not the same for every OS, as performance tuning and implementation may vary. Developers can also manually select a GC algorithm using JVM options.

## 30. When does the Garbage Collector invoke itself in Java?
Java's Garbage Collector (GC) runs automatically when memory is low or an object is no longer needed. You can request it using System.gc(), but Java may not run it immediately.

## 31. What is the purpose of the "rt.jar" file in Java?
The rt.jar file in Java (before Java 9) contained all core classes required by the JVM to run programs. In Java 9+, it was replaced by the modular system (jmods/) for better performance.

## 32. Explain the significance of the Manifest file in Java.
The Manifest file (MANIFEST.MF) in Java stores metadata about a JAR file, like the main class, classpath, and version details. It helps in making JARs executable and managing dependencies.

## 33. Differentiate between method overriding and method overloading in Java.
Method Overriding happens when a subclass provides a new implementation for a method already defined in the parent class (same method name, parameters, and return type).</br>
Method Overloading happens when multiple methods in the same class have the same name but different parameters (number or type of arguments).

## 34. Why might you choose to use an interface over an abstract class in Java? 
You might use an interface instead of an abstract class in Java because:</br>

Multiple Inheritance – A class can use many interfaces, but only one abstract class.</br>
</br>
Full Abstraction – Interfaces only have method declarations, while abstract classes can have both methods and code.</br>
Loose Coupling – Interfaces make code more flexible and less dependent on specific classes.</br>
Default Methods (Java 8+) – Interfaces can have default and static methods for extra features.</br>
</br>
Interfaces are best when you want to define rules without forcing a strict class structure! 

## 35. Can you reassign a value to a final variable in Java?
No, you cannot reassign a value to a final variable in Java after it is initialized. The value remains constant throughout the program.

## 36. What is type inference in Java?
Type inference in Java means the compiler automatically detects a variable's data type based on its assigned value. It was introduced in Java 10 using the var keyword.

## 37. Compare and contrast stateful and stateless programming in Java.

### Stateful vs. Stateless Programming in Java
Stateful Programming means the application remembers past interactions by storing data (state) between method calls or requests. Example: Session-based web apps where user data is stored. </br>
Stateless Programming means each request is independent, and no past data is stored. Example: REST APIs where every request contains all necessary data.</br>
Stateful systems use more memory since they store session data, while stateless systems use less memory and scale better.</br>
Stateful apps are useful for banking systems, shopping carts, etc., while stateless apps are best for cloud-based services and microservices.</br>
Stateless apps are faster since they don’t need to manage past data, but stateful apps are better for personalized experiences. 

## 38. What is a lambda expression, and when was it introduced in Java?
A lambda expression is a short way to write anonymous functions in Java, mainly used for functional programming. It was introduced in Java 8 (2014) to simplify code, especially with functional interfaces.

## 39. What is the difference between a lambda expression and an anonymous class?
A lambda expression is a short and cleaner way to implement a functional interface, while an anonymous class can implement multiple methods and extend classes. Lambda is more readable and efficient, while an anonymous class creates an extra class file.

## 40. Can we use a lambda expression without a functional interface? Why or why not?
No, we cannot use a lambda expression without a functional interface because lambda needs a single abstract method (SAM) to work. Java uses functional interfaces to provide a proper context for lambda execution.

## 41. What is Functional Programming?
Functional programming is a programming style where we write code using pure functions.
