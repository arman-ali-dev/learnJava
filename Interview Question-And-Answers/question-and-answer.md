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

## 42. Explain the concept of Wrapper Classes in Java.
Wrapper classes in Java convert primitive data types (like int, double) into objects (Integer, Double, etc.) and vice versa. They enable autoboxing (primitive to object) and unboxing (object to primitive) and are useful in collections where objects are required.

## 43. Distinguish between primitive and non-primitive data types in Java.
Primitive Data Types: These are basic data types like int, char, and double that store actual values and have a fixed size. They are stored in stack memory and do not have built-in methods.</br>

Non-Primitive Data Types: These are complex types like String, Array, and Class that store references to objects. They are stored in heap memory and come with useful methods.

## 44. What is an Anonymous Object in Java?
An Anonymous Object is an object created without a name (reference variable) and used immediately. It is useful when an object is needed only once, like calling a method directly.

## 45. Is it possible to overload methods in a child class in Java?
Yes, a child class can overload methods by defining multiple methods with the same name but different parameters.

## 46. Can you change the return type of an overloaded method in Java?
Yes, you can change the return type of an overloaded method, but just changing the return type alone doesn’t count as overloading. The method must have different parameters (type or number).

## 47. Can you change the return type of an overriding method in Java?
Yes, you can change the return type in method overriding, but only to a subclass of the parent method’s return type (covariant return type). If the return type is unrelated, it will cause a compilation error.

## 48. Discuss the differences between compile-time binding and runtime binding, as well as compile-time polymorphism and runtime polymorphism.
### Compile-time Binding vs. Runtime Binding
Compile-time Binding: Method or variable is resolved at compile time. Example: method overloading.</br>
Runtime Binding: Method is resolved at runtime using dynamic method dispatch. Example: method overriding.

### Compile-time Polymorphism vs. Runtime Polymorphism
Compile-time Polymorphism: Achieved using method overloading, where multiple methods have the same name but different parameters.</br>
Runtime Polymorphism: Achieved using method overriding, where a child class provides a specific implementation of a method from the parent class.

## 49. what is dynamic method dispatch?
Dynamic Method Dispatch is a process where the method to be called is determined at runtime, based on the actual object type (not the reference type). It enables method overriding and helps achieve runtime polymorphism.

## 50. What is a covariant return type in method overriding, and does it support overloading as well?
### Covariant Return Type in Overriding:
In method overriding, the child class can change the return type of a method, but only to a subclass of the parent’s return type. This is called a covariant return type.

### Does It Support Overloading?
No, method overloading does not support covariant return types because overloading depends only on different parameters, not the return type.

## 51. What are the advantages and disadvantages of using log4j for logging in Java?

### Advantages of Log4j:
Highly Configurable: Supports XML and properties file-based configurations for flexibility.</br>
Multiple Logging Levels: Provides levels like DEBUG, INFO, WARN, ERROR, FATAL to control logging output.</br>
Performance Efficient: Uses asynchronous logging to improve performance.</br>
Multiple Output Destinations: Logs can be written to console, files, databases, sockets, etc.</br>
Filter and Formatting Support: Allows custom log filters and formatters for better readability.</br>

### Disadvantages of Log4j:
Complex Configuration: XML-based configurations can be difficult to manage.</br>
Security Issues: Older versions (Log4j 1.x and 2.x) had vulnerabilities like Log4Shell.</br>
Memory Usage: Improper configuration can cause high memory consumption.</br>
Thread Safety Concerns: In some cases, improper handling may lead to concurrent logging issues.</br>
Alternative Options Available: Modern frameworks like SLF4J with Logback provide better performance and flexibility.</br>

## 52. Explain the concepts of coupling and collision in software engineering.
### Coupling:
Coupling means how much one part of a program depends on another. Less coupling is better because it makes the code easier to change and fix.

### Collision:
Collision happens when two or more parts of a program try to use the same resource at the same time, causing errors or conflicts.

## 53. Which sorting algorithm is considered the best in Java, and why?

## 54. What is the significance of the "java.lang" package in Java?
### Significance of java.lang Package in Java:
Automatically Imported: It is automatically imported in every Java program, so you don’t need to manually import it.</br>
Core Classes: It contains essential classes like String, Math, Object, System, Thread, Exception, etc.</br>
Fundamental Functionality: Provides basic functionalities like string handling, mathematical operations, multi-threading, exception handling, etc.</br>
Wrapper Classes: Includes wrapper classes like Integer, Double, Boolean, which help in converting primitives to objects.</br>

## 55. Describe the purpose and usage of the "final" keyword in Java.
The final keyword in Java is used to restrict modification of variables, methods, and classes. A final variable cannot be reassigned, a final method cannot be overridden, and a final class cannot be inherited. It is useful for security, immutability, and optimization in Java programs.

## 56. Why can private members be accessed through reflection in Java?
In Java, private members can be accessed through Reflection API because it allows modifying access controls at runtime. By using setAccessible(true), Java bypasses access restrictions, enabling access to private variables and methods for debugging, testing, and frameworks like Hibernate and Spring.

## 57. Discuss the different scopes of member variables in Java. 
1. Instance Variables: Declared inside a class but outside methods; belong to an object and exist as long as the object exists.</br>
2. Class Variables (Static): Declared with static inside a class; shared among all objects and exist throughout the program.</br>
3. Local Variables: Declared inside a method; exist only during method execution and must be initialized before use.</br>
4. Block Variables: Declared inside a block ({ }); exist only within that block and are inaccessible outside it.

## 58. What is reflection in Java, and what are its common uses?
Reflection in Java is a runtime mechanism that allows inspecting and modifying classes, methods, and fields dynamically. It is part of the java.lang.reflect package and enables accessing private members, invoking methods, and creating objects dynamically. Reflection is widely used in frameworks like Spring, Hibernate, and JUnit for dependency injection, ORM, and testing. However, it can impact performance and security if not used carefully.

## 59. Is the FileNotFoundException a checked or unchecked exception in Java?
FileNotFoundException is a checked exception in Java that occurs when a specified file is missing or inaccessible.

## 60. What is an inner class in Java?
An inner class in Java is a class defined inside another class. It helps in grouping related logic and can access all members (even private) of the outer class.

## 61. How do you create an object of an inner class in Java?
To create an object of an inner class in Java, first, you need to create an object of the outer class, and then use it to create the inner class object.

## 62. What is the name of the compiled inner class in Java?
The compiled name of an inner class in Java follows the format Outer$Inner.class, where $ separates the outer and inner class names.

### You would use an inner class in Java when:

1. Logical Grouping: When a class is only relevant to its outer class (e.g., Engine inside Car).</br>
2. Encapsulation: To hide helper classes from outside access.</br>
3. Access to Private Members: Inner classes can directly access private members of the outer class.</br>
4. Event Handling in GUI: Used in Swing/AWT for handling button clicks (like ActionListener).

## 63. Explain the difference between a static class and a static inner class in Java.
In Java, a static class does not exist because top-level classes cannot be static. However, a static inner class is a nested class declared with the static keyword inside another class. It does not require an instance of the outer class and cannot access non-static members of the outer class directly.

## 64. What are the access modifiers available in Java?
1. public → Accessible from anywhere in the program.</br>
2. private → Accessible only within the same class.</br>
3. protected → Accessible within the same package and in subclasses.</br>
4. (Default - No modifier) → Accessible only within the same package.

## 65. What is Serialization and Deserialization in Java?
### Serialization:
Serialization is a mechanism to convert state of an object into byte stream.

### Deserialization:
Deserialization is reverse process of serialization.

## 66. How do you implement Serialization in Java?
### Steps to Implement Serialization in Java:
1. Implement Serializable interface in your class.</br>
2. Use ObjectOutputStream to serialize the object.</br>
3. Use ObjectInputStream to deserialize the object.</br>
4. (Optional) Use transient keyword to exclude fields from serialization.

## 67. How does the JVM operate on serialized objects in Java?
The JVM converts an object into a byte stream during serialization using ObjectOutputStream, so it can be saved or sent over a network. During deserialization, ObjectInputStream converts the byte stream back into an object. If the serialVersionUID does not match, an InvalidClassException occurs. Fields marked as transient are not serialized. If a class does not implement Serializable, an exception is thrown.

## 68. Explain the difference between a method and a function in Java.
### Function:
A function is an independent block of code that performs a specific task and can exist outside a class (not applicable in Java).

### Method:
A method is a function that belongs to a class or object in Java and is used to define behavior. 

## 69. What is an Annotation in Java, and how do you create a custom annotation?
### What is an Annotation in Java?
Annotations in Java are metadata that provide information about code but do not affect its execution. They are used for compilation instructions, runtime processing, and code analysis.</br>
</br>
Common examples: @Override, @Deprecated, @FunctionalInterface.

## 70. Can you declare a class as both private and protected in Java?
No, you cannot declare a class as both private and protected in Java.</br>

  -> private class → Only allowed for inner (nested) classes, not for top-level classes.</br>
  -> protected class → Not allowed in Java; only methods, variables, and inner classes can be protected.</br>
If you try to declare a class as both private and protected, it will cause a compilation error.

## 71. What is the purpose of the "transient" keyword in Java?
The transient keyword in Java is used to prevent a field from being serialized. When an object is serialized, transient fields are ignored and set to their default values during deserialization. 

## 72. What is the meaning of the Serial Version UID in Java Serialization?
The Serial Version UID (serialVersionUID) is a unique identifier used in Java serialization to ensure version compatibility of serialized objects.

If a class's serialVersionUID does not match during deserialization, an InvalidClassException occurs.

## 73. Define and differentiate between Static Import, Static Block, Static Method, Static Variable, and Static Class in Java.
Static Import – It allows using static members of another class without specifying the class name.</br>
Static Block – It executes once when the class is loaded, used for initialization.</br>
Static Method – It belongs to the class and can be called without creating an object.</br>
Static Variable – It is a class-level variable shared among all objects of the class.</br>
Static Class – Only nested classes can be static, making them independent of the outer class instance.

## 74. What are the differences between HTTP and HTTPS (HTTP Secure)?
Security – HTTP transmits data in plain text, while HTTPS encrypts it for security.</br>
Port – HTTP uses port 80, whereas HTTPS uses port 443.</br>
SSL/TLS – HTTPS uses SSL/TLS certificates to encrypt data and ensure secure communication.</br>
SEO & Trust – Google prefers HTTPS for better rankings, and users trust secure sites more.</br>
Performance – HTTPS may be slightly slower due to encryption but is much safer.

## 75. What is the JVM (Java Virtual Machine)?
JVM (Java Virtual Machine) is a runtime environment that executes Java bytecode on any platform. It provides features like memory management, garbage collection, and platform independence.

## 76. Explain the concept of platform independence in Java.
Platform independence in Java means that Java code can run on any operating system without modification. This is possible because Java programs are compiled into bytecode, which the JVM (Java Virtual Machine) interprets and executes on any platform that has a compatible JVM.

## 77. Is the JVM platform-independent?
No, the JVM (Java Virtual Machine) is not platform-independent because each operating system has its own specific implementation of the JVM. 

## 78. Who calls the main method in Java?
In Java, the JVM (Java Virtual Machine) calls the main method when a program starts execution. It looks for the public static void main(String[] args) method and runs it as the entry point of the program.

## 79. Differentiate between JDK, JRE, and JVM in Java.
JDK (Java Development Kit) – It includes JRE, compiler, and development tools for writing and compiling Java programs.</br>
JRE (Java Runtime Environment) – It contains JVM and libraries needed to run Java applications.</br>
JVM (Java Virtual Machine) – It executes Java bytecode and provides platform independence.

## 80. What are the different memory areas inside the JVM in Java?
### JVM memory is divided into several areas for efficient execution of Java programs:

Method Area – Stores class metadata, static variables, and method code.</br>
Heap – Stores objects and instance variables; shared among all threads.</br>
Stack – Stores method call frames, local variables, and partial results for each thread.</br>
PC Register – Holds the address of the currently executing instruction.</br>
Native Method Stack – Stores native (non-Java) method calls used via JNI (Java Native Interface).

## 81. Describe the Heap Area in the JVM.
The Heap Area in JVM is where all Java objects and instance variables are stored. It is shared by all threads and managed by the Garbage Collector (GC).</br>

It has two main parts:</br>
Young Generation – Stores new objects, and unused ones are quickly removed.</br>
Old Generation – Stores long-lived objects that survive multiple GC cycles.</br>

From Java 8 onwards, Metaspace is used to store class metadata instead of the old Permanent Generation.

## 82. What happens to the JVM when an error or exception occurs in Java?
### When an error or exception happens in Java, the JVM reacts in different ways:

Handled Exception – If the exception is caught using try-catch, the program continues running normally.</br>
Unhandled Exception – If not handled, the JVM stops execution and prints an error message (stack trace).</br>
Error – Serious issues like OutOfMemoryError or StackOverflowError usually cause the JVM to crash.</br>
If exceptions are handled properly, the program keeps running; otherwise, the JVM may stop.

## 83. Is the String constant pool part of the Heap Area in Java?
Yes, the String Constant Pool is a part of the Heap Area in Java, where string literals are stored to save memory. When a string is created using "", it is stored in the pool, but using new String(), it is stored separately in the heap.

## 84. How does the class loader work in Java?
### In Java, the Class Loader loads Java classes into memory when required. It follows three main steps:
Loading – Finds the .class file and loads it into memory.</br>
Linking – Verifies bytecode, allocates memory for static variables, and prepares the class.</br>
Initialization – Executes static blocks and initializes static variables.</br>

### There are three types of Class Loaders:
Bootstrap ClassLoader – Loads core Java classes (java.lang, java.util).</br>
Extension ClassLoader – Loads classes from ext directory (javax.*).</br>
Application ClassLoader – Loads user-defined classes from the classpath.

## 85. What details are stored inside the Method Area in Java?
The Method Area in Java stores class metadata, static variables, method bytecode, and the runtime constant pool. From Java 8 onwards, it is part of Metaspace, replacing the older PermGen ( Permanent Generation ).

## 86. Explain JIT (Just-in-Time) compilation in Java.
JIT (Just-in-Time) Compiler in Java converts bytecode into native machine code (0s and 1s) at runtime to make execution faster. Instead of interpreting the code line by line, JIT compiles frequently used methods into machine code (0s and 1s), so the CPU can run them directly, improving performance.

## 87. Describe the Garbage Collector in Java.
Garbage Collector (GC) in Java automatically removes unused objects from memory to free up space and prevent memory leaks. It identifies objects that are no longer referenced and deletes them. This helps in efficient memory management without manual cleanup.

## 88. How do you invoke the garbage collector in Java?
In Java, you can request Garbage Collection using System.gc(), but JVM decides whether to run it or not; it's best to let Java handle it automatically.

## 89. Can you guarantee the invocation of the garbage collector in Java?
No, you cannot guarantee the invocation of the Garbage Collector (GC) in Java. Methods like System.gc() or Runtime.getRuntime().gc() only request GC, but JVM decides whether to run it or not based on memory needs.

## 90. What is a .class file in Java?
A .class file in Java is a compiled version of a Java source file (.java), which contains bytecode that the JVM (Java Virtual Machine) can execute. It is generated when you compile a Java program using the javac compiler.

## 91. Can you run a .class file on any JVM on different systems in Java?
Yes, a .class file can run on any JVM on different systems because JVM makes Java platform-independent. The .class file contains bytecode, which the JVM translates into native machine code specific to the operating system.

## 92. What is bytecode in Java?
Bytecode is an intermediate code generated by the javac compiler from a .java file; it is executed by the JVM and is platform-independent.

## 93. How do you increase or decrease the allocated RAM for a runtime JVM in Java?
You can increase or decrease JVM memory allocation using -Xms (initial heap size) and -Xmx (maximum heap size). For example, java -Xms512m -Xmx2g MyApp sets 512MB as the initial memory and 2GB as the maximum memory for the JVM.

## 94. What is an OutOfMemoryError in Java, and how can you solve it?
### What is OutOfMemoryError in Java?
OutOfMemoryError occurs when JVM runs out of memory and cannot allocate more space for objects. This usually happens due to memory leaks, excessive object creation, or insufficient heap size.

### How to Solve It?
Increase Heap Size – Use -Xmx option (e.g., java -Xmx2g MyApp).</br>
Fix Memory Leaks – Identify unused objects and properly release memory.</br>
Use Efficient Data Structures – Avoid unnecessary object creation.</br>
Enable Garbage Collection Logs – Use -XX:+PrintGCDetails to monitor memory usage.</br>
Optimize Code – Reduce large collections, caches, and unnecessary references.

## 95. Differentiate between hashCode() and equals() in Java.
### Difference Between hashCode() and equals() in Java
hashCode() returns an integer (hash value) used for storing objects in hashing-based collections like HashMap and HashSet.</br>
equals() checks if two objects are logically equal (same data).</br>
</br>
If equals() returns true, then hashCode() must be the same. But same hashCode() does not guarantee equals() will be true.

## 96. Describe the real use of interfaces and abstract classes in Java.
### Interface
An interface in Java is a blueprint that defines method signatures without implementation. It allows multiple inheritance and helps in achieving abstraction and polymorphism. Classes that implement an interface must provide implementations for its methods.

### Abstract Class
An abstract class is a class that can have both implemented and unimplemented (abstract) methods. It is used when multiple classes share common behavior but also need their own specific implementations. Objects cannot be created from an abstract class directly.

## 97. What is Marker Interface With Example?
A Marker Interface is an empty interface (without methods or fields) used to indicate or tag a class for special behavior by the JVM or frameworks.
</br>
Example: Serializable in Java.

## 98. How can you achieve multiple inheritance in Java?
Multiple inheritance in Java means inheriting features from more than one source. It is achieved using interfaces, as Java does not support multiple class inheritance to avoid ambiguity.

## 99. Explain all the object-oriented programming concepts in Java.
### Java follows Object-Oriented Programming (OOP) principles, which include the following four main concepts:
#### 1. Encapsulation (Data Hiding)
Encapsulation means wrapping data (variables) and methods into a single unit (class) and restricting direct access to them. It is achieved using private variables and public getter/setter methods.

#### 2. Inheritance (Code Reusability)
Inheritance allows a class (child) to acquire properties and methods from another class (parent), promoting code reuse and reducing redundancy.

#### 3. Polymorphism (One Name, Many Forms)
Polymorphism allows one method to be used for multiple functionalities. It is of two types:</br>
✔ Compile-time Polymorphism (Method Overloading)
✔ Runtime Polymorphism (Method Overriding)

#### 4. Abstraction (Hiding Implementation)
Abstraction means hiding implementation details and showing only necessary information. It can be achieved using abstract classes and interfaces.

## 100. Differentiate between Encapsulation and Abstraction in Java.
✔ Encapsulation: It hides data by making variables private and allows controlled access through getter/setter methods. It ensures data security and prevents unauthorized modification.</br></br>

✔ Abstraction: It hides the implementation details and only shows the necessary functionality using abstract classes or interfaces. It helps in reducing complexity and improving code maintainability.

## 101. Discuss the significance of object-oriented programming in Java.
OOP in Java makes code modular, reusable, and secure by using encapsulation, inheritance, polymorphism, and abstraction. It helps in reducing redundancy, improving scalability, and simplifying complex systems. By modeling real-world entities using classes and objects, OOP enhances code organization and maintainability. 

## 102. Is it possible to create an object of an abstract class inside the same abstract class in Java?
No, you cannot create an object of an abstract class directly in Java because abstract classes are incomplete (they may have abstract methods without implementation). However, you can create an object inside the same abstract class using an anonymous inner class.

## 103. What does OOP (Object-Oriented Programming) refer to?
Object-Oriented Programming (OOP) is a programming paradigm that organizes code using objects and classes to model real-world entities. It follows four key principles: Encapsulation, Inheritance, Polymorphism, and Abstraction, making code reusable, modular, and maintainable.

## 104. Define the concept of a Class in object-oriented programming.
A class in Object-Oriented Programming is a blueprint or template for creating objects. It defines variables (attributes) and methods (behaviors) that objects of that class will have. In Java, a class is created using the class keyword.

## 105. Define the concept of an Object in object-oriented programming.
An object in Object-Oriented Programming is an instance of a class that contains state (variables) and behavior (methods). It represents a real-world entity and is created using the new keyword in Java. 

## 106. Explain the concept of Encapsulation in object-oriented programming.
Encapsulation in Object-Oriented Programming is the concept of hiding data by making class variables private and providing access through public getter and setter methods. This ensures data security, controlled access, and better maintainability.

## 107. Explain the concept of Abstraction in object-oriented programming.
Abstraction in Object-Oriented Programming means hiding implementation details and only showing the essential functionality. It is achieved using abstract classes and interfaces in Java, helping to reduce complexity and improve code maintainability.

## 108. What is Inheritance in object-oriented programming?
Inheritance in Object-Oriented Programming is the concept where a child class (subclass) acquires the properties and behaviors of a parent class (superclass).

## 109. Explain the concept of Polymorphism in object-oriented programming.
Polymorphism in Object-Oriented Programming means one method or function behaving differently based on the object or input. It allows code flexibility and reusability and is of two types:</br>
</br>
Method Overloading (Compile-time Polymorphism) – Same method name with different parameters.</br>
Method Overriding (Runtime Polymorphism) – Subclass provides a specific implementation of a method from the parent class.

## 110. What is Overriding and Overloading in Java, and what is the difference between them?
✔ Method Overriding: When a subclass provides a new implementation of a method inherited from the parent class. It is used for runtime polymorphism and requires inheritance.
</br>
</br>
✔ Method Overloading: When multiple methods in the same class have the same name but different parameters. It is used for compile-time polymorphism and does not require inheritance.

## 111. Explain the rules for access modifiers when overriding methods in Java.
If the parent method is public, the child method must also be public.</br>
If the parent method is protected, the child method can be protected or public, but not private.</br>
Private methods cannot be overridden because they are only accessible within the same class.</br>
Default (no modifier) methods can only be overridden within the same package.

## 112. What is a Covariant Type in Java?
A Covariant Return Type in Java allows an overridden method in a subclass to return a subtype (child class) of the return type declared in the parent class.

## 113. Explain the concepts of IS-A and HAS-A relationships in Java.
IS-A Relationship: It represents inheritance where one class is a subtype of another (e.g., Dog is an Animal).</br>
HAS-A Relationship: It represents a relationship where one class contains an instance of another (e.g., Car has an Engine).

## 114. What are Association, Composition, and Aggregation in Java?
#### 1. Association
It is a general relationship between two classes where both can exist independently. Example: Student and Teacher—a student can have multiple teachers, and a teacher can have multiple students.

#### 2. Composition (Strong HAS-A Relationship)
It is a relationship where one class contains another, and the contained class cannot exist independently. Example: Car and Engine—if the Car is destroyed, the Engine is also destroyed.

#### 3. Aggregation (Weak HAS-A Relationship)
It is a relationship where one class contains another, but the contained class can exist independently. Example: Library and Books—if the Library is destroyed, the Books can still exist elsewhere.

## 115. Define multi-level and multiple level inheritance in Java.
### Multi-Level Inheritance:
When a class inherits from another class, which itself is inherited from another class. Example: Grandparent → Parent → Child.

### Multiple Inheritance:
Java does not support multiple inheritance with classes but allows it using interfaces. Example: class C implements A, B.

## 116. What is the diamond problem in object-oriented programming, and how is it resolved?
Diamond Problem occurs when a class inherits from two parent classes that both inherit from the same base class, causing confusion about which method to inherit.
</br>
In Java, this issue is avoided because multiple inheritance with classes is not allowed. However, with interfaces, it can be resolved using default methods and method overriding.

## 117. Explain the protected access specifier in the context of inheritance in Java.
The protected access specifier allows a member to be accessed within the same package and by subclasses in other packages. When a child class inherits a parent class, it can directly access protected methods and variables. It is more accessible than private but less than public. It helps in code reusability and maintaining encapsulation in inheritance.

## 118. Define Data Hiding in the context of inheritance in Java.
Data Hiding in inheritance means restricting direct access to a class's data members by using private access modifiers. It ensures that subclasses cannot directly access private fields of the parent class and must use getter/setter methods for controlled access.

## 119. What does it mean for a class to be immutable, and how can you make a class immutable in Java?

#### What is an Immutable Class?
An immutable class is a class whose objects cannot be modified after they are created. Any change results in a new object instead of modifying the existing one.

#### How to Make a Class Immutable in Java?

1. Declare the class as final so it cannot be extended.</br>
2. Make all fields private and final to prevent modification after object creation.</br>
3. Do not provide setter methods, so field values cannot be changed.</br>
4. Initialize fields via a constructor and assign values only once.

## 120. Its state cannot change after creation.
#### An immutable object in Java has the following properties:

1. Its state cannot change after creation.</br>
2. All fields are private and final to prevent modification.</br>
3. No setter methods are provided.</br>
4. Any mutable fields return a copy instead of a direct reference.

## 121. Explain the differences between String literals and String objects in Java.
String literals are stored in the String Pool and reused if already present. String objects created using new are stored in Heap Memory and always create a new object. Literals are memory-efficient, while objects offer flexibility but use more memory.

## 122. Describe the concept of the String pool in Java.
The String Pool in Java is a special memory area inside the heap where String literals are stored. If a new String literal is created and already exists in the pool, Java reuses the existing object instead of creating a new one. This helps in saving memory and improving performance. However, new String("Hello") always creates a new object in the heap, not in the pool.

## 123. What happens when you compare "==" and ".equals" for String and new String objects in Java?
### Comparison of == vs .equals() for Strings in Java
== (Reference Comparison)

#### == (Reference Comparison)
1. Compares memory addresses (references), not actual content.
2. Works for String literals (same reference in String Pool).
3. Fails for new String() because it creates a new object in Heap.

#### .equals() (Content Comparison)
1. Compares the actual content (characters) of the String.
2. Works correctly for both literals and new String() objects.

## 124. What are the results of comparing "==" and ".equals" for String and StringBuffer objects in Java?
== always returns false for String and StringBuffer because they are different classes and have different memory references. .equals() also returns false because StringBuffer does not override .equals(), so it behaves like == (compares references). To compare content, convert StringBuffer to String using .toString() before using .equals().

## 125. Explain the output of the expression "A"+"B"+"C"+"D" in Java.
In Java, "A" + "B" + "C" + "D" performs String concatenation, resulting in "ABCD". Since all are String literals, Java optimizes and directly replaces the expression with "ABCD" at compile time.

## 126. Why are StringBuilder and StringBuffer classes declared as "final" in Java?
StringBuilder and StringBuffer are declared final to prevent inheritance, ensuring performance optimization and data integrity. This avoids method overriding, which could affect efficiency (StringBuilder) or thread safety (StringBuffer).

## Why is String immutable in Java, whereas StringBuilder and StringBuffer are not?
String is immutable to enable String Pooling, security, and thread safety, ensuring safe reuse and preventing unintended modifications. If String were mutable, changing one reference would affect all others. StringBuilder and StringBuffer are mutable, designed for better performance when modifying strings frequently, avoiding unnecessary object creation.

## 127. How can you perform a Deep copy in the case of String objects in Java?
In Java, String is immutable, so a deep copy happens automatically when assigning or copying it. Using new String(original) creates a new object in Heap memory, ensuring the copy is independent of the original.

## 128. What is the purpose of the "ensureCapacity" method in Java?
The ensureCapacity() method in StringBuilder and StringBuffer reserves extra space in memory to avoid frequent resizing. This helps in faster string operations when adding more characters.

## 129. What is the primary use of constructors in Java?
In Java, constructors are used to initialize objects when they are created. They set initial values for object attributes and ensure proper setup. A constructor has the same name as the class and is called automatically when an object is instantiated.

## 130. Explain the concept of a default constructor in Java.
A default constructor in Java is a no-argument constructor that initializes objects with default values. If no constructor is defined, Java provides one automatically.

## 131. What is a parameterized constructor in Java, and can you explain its properties?
A parameterized constructor in Java is a constructor that accepts arguments to initialize an object with specific values. It allows setting custom values at the time of object creation, enabling better flexibility and control.

#### Properties:

1. Takes parameters to assign values to instance variables.</br>
2. Eliminates the need for setter methods to initialize objects.</br>
3. Can be overloaded by defining multiple constructors with different parameters.

## 132. How does your code behave when both a default constructor and a parameterized constructor are present in a Java class?
When both a default constructor and a parameterized constructor are present in a Java class, the constructor that gets executed depends on how the object is instantiated.
</br>
</br>
-> If an object is created without arguments, the default constructor is called.</br>
-> If an object is created with arguments, the parameterized constructor is called.

## 133. Define constructor overloading, constructor overriding, and constructor chaining in Java.
### 1. Constructor Overloading
Having multiple constructors in a class with different parameter lists. Java calls the appropriate constructor based on the arguments passed.

### 2. Constructor Overriding (Not Possible)
Constructors cannot be overridden as they are not inherited, but a subclass can call the parent constructor using super().

### 3. Constructor Chaining
One constructor calls another within the same class (this()) or a parent class (super()) to improve code reusability.

## 134. Why are "this" and "super" used in constructors in Java? What access modifiers can be used with constructors?
### Why are this and super used in constructors?
this() → Calls another constructor in the same class, avoiding code duplication.</br>
super() → Calls the parent class's constructor, ensuring proper initialization in inheritance.

#### Access Modifiers for Constructors
1. public → Accessible from anywhere.</br>
2. private → Prevents object creation outside the class (used in Singleton).</br>
3. protected → Accessible within the same package and subclasses.</br>
4. default (no modifier) → Accessible within the same package only.

## 135. Is it possible to give a constructor a different name other than the class name in Java?
No, in Java, a constructor must have the same name as the class. If you try to give it a different name, it will be treated as a regular method, not a constructor.

## 136. What is a parameterized constructor in Java, and how is object creation related to constructors?
A parameterized constructor in Java takes arguments to initialize an object with specific values at the time of creation. When an object is created using new, the corresponding constructor is automatically called to allocate memory and set initial values.

## 137. Explain the logical flow of constructors in the context of inheritance in Java. Is there a return type for constructors?
### Logical Flow of Constructors in Inheritance
#### In Java inheritance, when a subclass object is created:

1. The parent class constructor is called first using super(), even if not explicitly written (Java adds it automatically).
2. Then, the child class constructor executes.

### Is There a Return Type for Constructors?
No, constructors do not have a return type, not even void. They automatically return the instance of the class. If a return type is specified, it becomes a regular method, not a constructor.

## 138. What is a private constructor, a static constructor, and a final constructor in Java?
### 1. Private Constructor
A private constructor restricts object creation from outside the class, mainly used in Singleton patterns or utility classes.

### 2. Static Constructor (Not in Java)
Java does not support static constructors, but a static block can be used to initialize static variables.

### 3. Final Constructor (Not Allowed in Java)
Java does not allow final constructors because constructors cannot be inherited or overridden. Using final with a constructor will cause a compilation error.

## 139. Can you have an abstract constructor, and can constructors exist within interfaces in Java?
### Can You Have an Abstract Constructor in Java?
No, Java does not allow abstract constructors because constructors are meant to initialize objects, while abstract indicates that a method must be implemented by subclasses. Since constructors cannot be inherited, making them abstract is meaningless.

### Can Constructors Exist Within Interfaces in Java?
#### No, constructors cannot exist in interfaces because:
1. Interfaces cannot have instances—they are meant to be implemented by classes.</br>
2. Constructors belong to classes, whereas interfaces do not have direct object creation.

## 140. Is it possible to have both "this" and "super" in the same constructor in Java?
No, it is not possible to use both this() and super() in the same constructor in Java because:</br>

1. this() → Calls another constructor of the same class.</br>
2. super() → Calls the parent class's constructor.</br>
3. Both must be the first statement in a constructor, and since Java allows only one first statement, using both together causes a compilation error.

## 141. Can you call a subclass constructor from a superclass constructor in Java? Can an abstract class in Java have a constructor?
### Can You Call a Subclass Constructor from a Superclass Constructor?
No, you cannot call a subclass constructor from a superclass constructor directly because Java enforces a top-down execution order in inheritance. The superclass constructor always executes first, ensuring that the parent class is properly initialized before the child class.

### Can an Abstract Class Have a Constructor?
Yes, an abstract class can have a constructor because it is still a class and may need to initialize common fields for subclasses. However, it cannot be instantiated directly—only its subclasses can call the constructor using super().

## 142. How are exceptions handled in constructors in Java?
Handling Exceptions in Constructors in Java
In Java, exceptions in constructors can be handled using try-catch blocks or by declaring throws to propagate exceptions.

## 143. Explain the different types of constructors available in Java.
### 1. Default Constructor
A constructor with no parameters, provided by Java if no constructor is defined. It initializes objects with default values.
### 2. Parameterized Constructor
A constructor that takes arguments to initialize an object with specific values during creation.
### 3. Private Constructor
Restricts object creation from outside the class, mainly used in Singleton patterns or utility classes.
### 4. Copy Constructor (Not Built-in in Java)
Manually created to copy values from one object to another by passing an object as a parameter.
### 5. Static Constructor (Not Supported in Java)
Java does not support static constructors, but static blocks can be used for static initialization.

## 144. Is it possible to have a constructor inside an abstract class in Java?
Yes, an Abstract Class Can Have a Constructor in Java!
Even though an abstract class cannot be instantiated, it can have a constructor. This constructor is used to initialize common properties for subclasses.

## 145. Explain the concept of constructor chaining in Java.
Constructor chaining means calling one constructor from another constructor within the same class or from a parent class. This helps in code reuse and reducing redundancy.

## 146. Explain the concepts of try-catch, try with multiple catch blocks, and try with resources in Java.
### 1. try-catch Block
The try-catch block is used to handle exceptions in Java. The code that might throw an exception is placed inside the try block, and the corresponding handling logic is written in the catch block.
### 2. try with Multiple catch Blocks
A try block can have multiple catch blocks to handle different types of exceptions separately.
### 3. try with Resources (try-with-resources)
The try-with-resources statement is used to automatically close resources (like files, sockets, or database connections) after the try block completes. This feature was introduced in Java 7.

## 147. Describe the hierarchy of exceptions in Java.
### 1. Throwable (Root Class)
#### The Throwable class is the root of the exception hierarchy. It has two main subclasses:
1. Exception
2. Error

### 2. Exception (Recoverable)
#### The Exception class represents conditions that a program can catch and handle.

### Types of Exceptions:

#### Checked Exceptions:
1. Must be handled using try-catch or declared using throws.</br>
2. Occur during compile-time.
#### Examples:
1. IOException</br>
2. SQLException</br>
3. FileNotFoundException

#### Unchecked Exceptions (Runtime Exceptions):

1. Do not need to be handled explicitly.</br>
2. Occur during runtime.

#### Examples:

1. NullPointerException</br>
2. ArrayIndexOutOfBoundsException
3. ArithmeticException


