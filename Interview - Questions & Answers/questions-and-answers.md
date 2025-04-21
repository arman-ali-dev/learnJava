### 1. What is the difference between "super" and "this" in Core Java?

- `this` refers to the **current object** of the class.
- `super` refers to the **parent (superclass) object**.

**Usage:**
- Use `this` to access current class variables, methods, or constructors.
- Use `super` to access parent class variables, methods, or constructors.

---

### 2. Explain the usage of "super()" and "this()" calls in constructors in Java.

- `this()` is used to call **another constructor** in the same class.
- `super()` is used to call the **parent class constructor**.

**Important:**
- Both `this()` and `super()` must be the **first statement** in the constructor.
- You **cannot use both** in the same constructor directly.

---

### 3. Differentiate between a "static" method and a "static" block in Java.

| Feature         | Static Method                              | Static Block                                 |
|----------------|--------------------------------------------|----------------------------------------------|
| Purpose        | Define logic that belongs to the class     | Initialize static variables or configuration |
| When runs      | When method is called                      | Automatically runs when class is loaded      |
| Called by      | Using ClassName.methodName()               | No need to call, runs once during load time  |

---

### 4. Describe the components of the JVM architecture

The major components of JVM are:

1. **ClassLoader**  
   - Loads `.class` files into memory.

2. **Bytecode Verifier**  
   - Checks the code for security and correctness before running.

3. **Memory Area**  
   - Stores class definitions, objects, methods, etc.
   - Divided into: Method Area, Heap, Stack, Program Counter, and Native Method Stack.

4. **Execution Engine**  
   - Executes the bytecode.
   - Includes interpreter, JIT compiler, and garbage collector.

---

### 5. What are the drawbacks of using System.out.println() for output in Java?

- It is **not efficient** for large or formatted output.
- It cannot be redirected easily.
- Not suitable for **professional logging**.
- Slower than other output methods like `BufferedWriter`.

Instead, use `Logger` or `PrintWriter` for better control and performance.

### 6. List the key features introduced in Java 7, Java 8, and Java 9.

**Java 7:**
- Diamond operator (`<>`)
- try-with-resources statement
- String in switch case
- Improved exception handling (multi-catch)
- Binary literals (e.g., 0b1010)
- Underscores in numeric literals (e.g., 1_000_000)

**Java 8:**
- Lambda Expressions
- Functional Interfaces
- Stream API
- Default and static methods in interfaces
- Method references
- New Date and Time API (`java.time`)
- Optional class

**Java 9:**
- Module System (Project Jigsaw)
- JShell (interactive Java REPL)
- Stream API improvements
- Private methods in interfaces
- Compact Strings

---

### 7. Discuss the concept of garbage collection in Java, including its uses and working principles.

**Garbage Collection (GC)** is the process by which Java automatically removes unused objects from memory.

**Why it's useful:**
- Prevents memory leaks
- Frees up space for new objects
- Makes Java memory-efficient and easier to manage

**How it works:**
- JVM identifies objects that are no longer used or referenced.
- These objects are marked and deleted.
- The memory is then reclaimed and reused.

The most common GC algorithm is **Mark and Sweep**.

---

### 8. How is memory management handled in the Java programming language?

Java handles memory management using:

- **Heap Memory:** Stores objects and classes
- **Stack Memory:** Stores method calls and local variables
- **Garbage Collector:** Automatically clears unused memory
- **Class Loader:** Loads classes into memory
- **JVM Memory Areas:** Like Method Area, Heap, Stack, etc.

Developers don’t need to manually free memory — JVM does it automatically.

---

### 9. Can the "main()" method be overridden in Java?

**No**, the `main()` method cannot be overridden because:

- It is `static`, and static methods **cannot be overridden**.
- Overriding happens with instance methods only (non-static).

---

### 10. Is it possible to overload the "main()" method in Java?

**Yes**, you can overload the `main()` method by changing the parameter list.

```java
public class Test {
    public static void main(String[] args) {
        System.out.println("Main with String[]");
        main(10);  // calling overloaded main
    }

    public static void main(int x) {
        System.out.println("Overloaded main: " + x);
    }
}
```

## 11. Can the "main" method be declared as "final" in Java?

Yes, the `main` method can be declared as `final`.  
It means the method can't be overridden, but it will still work and run normally.

---

## 12. What is object cloning in Java?

Object cloning means making a copy of an object using the `clone()` method.  
It creates a new object with the same values as the original.

---

## 13. Difference between Deep Copy and Shallow Copy

- **Shallow Copy**: Only copies the main object. Inner objects still refer to the same memory.
- **Deep Copy**: Copies the main object and all inner objects too (separate memory).

---

## 14. Why implement `equals()` when `compareTo()` is already implemented?

Because:
- `compareTo()` is used for sorting (like in `TreeSet`, `Collections.sort()`).
- `equals()` is used to check if two objects are exactly equal (like in `HashSet`, `HashMap`).
They work differently and both may be needed.

---

## 15. Importance of Singleton Object in Java

Singleton ensures that only one object of a class is created during the whole program.  
It is useful when you need a single point of access, like for database connections or logging.

### Example Code:

```java
public class Singleton {

    // Step 1: Create a private static instance of the class
    private static Singleton instance;

    // Step 2: Make the constructor private so that new objects can't be created
    private Singleton() {
        // private constructor
    }

    // Step 3: Create a public static method to return the instance
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }

    // Example method
    public void showMessage() {
        System.out.println("I am a Singleton object!");
    }
}
```

## 16. Why would you use a final class when its methods cannot be overridden?

A `final` class is used when you want to stop other classes from inheriting it.  
It adds security and avoids unexpected changes in behavior.  
Example: Java’s `String` class is final.

---

## 17. Is it possible to override a private method in a class if the class itself is declared as final?

No, private methods cannot be overridden — they are not accessible outside the class.  
Also, a `final` class can't be extended, so overriding is not possible in any way.

---

## 18. Can changes be made to a final or immutable class using reflection in Java?

Yes, changes can be made using **reflection**, even to private or final fields.  
But it breaks immutability and should be avoided unless absolutely necessary.

---

## 19. What is the garbage collector algorithm used by the JVM, and is it the same for every operating system?

JVM uses algorithms like:
- **Mark and Sweep**
- **Generational GC**
- **G1 (Garbage First) GC**

These algorithms depend on the **JVM**, not the operating system. So they can vary.

---

## 20. When does the Garbage Collector invoke itself in Java?

Garbage Collector runs automatically when:
- JVM decides memory is low.
- Objects are no longer reachable.
You can also suggest it using `System.gc()`, but it's not guaranteed to run immediately.

---

## 21. What is the purpose of the "rt.jar" file in Java?

`rt.jar` (runtime JAR) file contains all core Java class files like `java.lang`, `java.util`, etc.  
It is used by the JVM to run Java programs.  
Note: It was used till Java 8. Newer Java versions don't use it.

---

## 22. Explain the significance of the Manifest file in Java.

The `MANIFEST.MF` file gives metadata about a JAR file.  
Example: It can define the main class to run using `Main-Class:` entry.  
It is stored in `META-INF` folder inside the JAR.

---

## 23. Differentiate between method overriding and method overloading in Java.

- **Overriding**: Same method name and signature in subclass. Used for runtime polymorphism.  
- **Overloading**: Same method name but different parameters in the same class. Used for flexibility.

---

## 24. Why might you choose to use an interface over an abstract class in Java?

Use an interface when you want to define a contract for multiple classes.  
Interfaces support multiple inheritance; abstract classes don’t.  
They are best for defining behavior without implementation.

---

## 25. Can you reassign a value to a final variable in Java?

No, once a `final` variable is assigned a value, it cannot be changed.  
It becomes constant.

---

## 26. How can you iterate through a List using Lambda Expressions in Java?

You can use `forEach()` method with a lambda like this:

```java
List<String> names = Arrays.asList("Maan", "Ali", "Coder");
names.forEach(name -> System.out.println(name));
```

## 27. Explain the concept of Wrapper Classes in Java.

Wrapper classes convert primitive types into objects.  
Example: `int` → `Integer`, `char` → `Character`  
Useful for collections like `ArrayList` that work with objects.

---

## 28. Distinguish between primitive and non-primitive data types in Java.

- **Primitive**: Basic types like `int`, `char`, `float`. Store simple values.  
- **Non-Primitive**: Objects like `String`, `Array`, `Class`. They store references.

---

## 29. What is an Anonymous Object in Java?

An object created without a reference variable.  
Example:

```java
new MyClass().show();
```

## 30. Is it possible to overload methods in a child class in Java?

Yes, a child class can overload methods from the parent class.  
It can define methods with the same name but different parameter lists.  
This is called **method overloading**, and it works across parent and child classes.

**Example:**

```java
class Parent {
    void show() {
        System.out.println("Parent show()");
    }
}

class Child extends Parent {
    void show(String name) {
        System.out.println("Child show(String)");
    }
}
```

## 31. Can you change the return type of an overloaded method in Java?

Yes, return type can be different in overloaded methods,  
but parameter list must also be different.

---

## 32. Can you change the return type of an overriding method in Java?

Yes, but only if the new return type is a **subclass** of the original return type.  
This is called **covariant return type**.

---

## 33. Differences between compile-time binding vs runtime binding and compile-time vs runtime polymorphism

- **Compile-time binding/polymorphism**: Done at compile time. Example: method overloading.  
- **Runtime binding/polymorphism**: Done at runtime. Example: method overriding.

---

## 34. Explain Static Binding and Dynamic Binding in Java

- **Static Binding**: Linked at compile time. Example: overloaded methods, static methods.  
- **Dynamic Binding**: Linked at runtime. Example: overridden methods using objects.

### Polymorphism:
- **Overloading** → Compile-time polymorphism (static binding)  
- **Overriding** → Runtime polymorphism (dynamic binding)

---

## 35. What is a covariant return type in method overriding?

When a subclass overrides a method and changes the return type to a subclass of the original type.  
Yes, it is supported in **overriding**, but **not related to overloading**.

---
## 36. What are the advantages and disadvantages of using log4j for logging in Java?

### Advantages:
- Easy to configure and use.
- Supports multiple output formats and log levels.
- Can write logs to files, consoles, databases, etc.

### Disadvantages:
- Can slow down performance if not configured properly.
- Log4j 1.x had security issues (like Log4Shell).
- Requires proper maintenance in large apps.

---

## 37. Explain the concepts of coupling and collision in software engineering.

- **Coupling**: It means how much one module depends on another.  
  Low coupling is better as it makes code easier to change and test.

- **Collision**: Happens when two parts of code (like variables, functions, or threads) try to use the same resource in a conflicting way.  
  Example: Thread collision on shared data.

---

## 38. Which sorting algorithm is considered the best in Java, and why?

Java uses **TimSort** in `Arrays.sort()` for objects.  
It’s a mix of **Merge Sort** and **Insertion Sort**.  
TimSort is fast for real-world data and stable in performance.

---

## 39. What is the significance of the "java.lang" package in Java?

`java.lang` is automatically imported in every Java program.  
It contains core classes like `String`, `Object`, `System`, `Math`, and exceptions.

---

## 40. Describe the purpose and usage of the "final" keyword in Java.

- `final` **variable**: Can’t be changed once assigned.  
- `final` **method**: Can’t be overridden.  
- `final` **class**: Can’t be inherited.

Used for constants, security, and preventing modification.

---

## 41. Why can private members be accessed through reflection in Java?

Reflection allows Java code to **bypass access rules**.  
It can access private fields or methods for testing, frameworks, or debugging.  
But it should be used carefully as it breaks encapsulation.

---

## 42. Discuss the different scopes of member variables in Java

In Java, member variables can have the following scopes:

| Scope        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| Instance     | Belongs to each object of the class. Accessible through object reference.   |
| Static       | Belongs to the class. Shared by all objects. Accessible using class name.   |
| Local        | Declared inside methods or blocks. Only accessible within that method/block.|
| Parameter    | Variables passed to methods or constructors. Accessible only inside them.   |

---

## 43. What is reflection in Java, and what are its common uses?

**Reflection** in Java is a powerful feature that allows you to inspect and manipulate classes, methods, fields, and constructors at runtime.

### Common Uses of Reflection:
- Accessing private fields and methods (used in frameworks like Spring, Hibernate)
- Creating instances dynamically
- Calling methods dynamically
- Inspecting classes for annotations and metadata
- Useful for **debugging**, **testing**, and **framework development**

---

## 44. Is the FileNotFoundException a checked or unchecked exception in Java?

**`FileNotFoundException` is a checked exception** in Java.

- It must be either caught using `try-catch` or declared with `throws` in the method signature.
- It occurs when an attempt to open the file denoted by a pathname has failed.

---

## 45. How can you reverse an array of integers in Java with optimization?

You can reverse the array using two-pointer technique (swapping first and last element, then moving inwards):

```java
public class ReverseArray {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};

        int start = 0, end = arr.length - 1;
        while (start < end) {
            // Swap elements
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;

            start++;
            end--;
        }

        // Print reversed array
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

## 46. Provide a Java program for binary search

Binary Search is an efficient searching algorithm for **sorted arrays**. It works on the divide and conquer principle.

Here’s the optimized implementation using a `while` loop:

```java
public class BinarySearchExample {
    public static int binarySearch(int[] arr, int target) {
        int left = 0, right = arr.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (arr[mid] == target)
                return mid; // Target found
            else if (arr[mid] < target)
                left = mid + 1; // Search in right half
            else
                right = mid - 1; // Search in left half
        }

        return -1; // Target not found
    }

    public static void main(String[] args) {
        int[] arr = {2, 4, 6, 8, 10, 12, 14};
        int target = 10;

        int result = binarySearch(arr, target);
        if (result != -1)
            System.out.println("Element found at index: " + result);
        else
            System.out.println("Element not found.");
    }
}
```

## 47. What is an inner class in Java?

An **inner class** is a class defined inside another class in Java.  
It can access all members (even private) of the outer class.

Java has 4 types of inner classes:
1. **Non-static inner class (regular)**
2. **Static nested class**
3. **Local inner class** (defined inside a method)
4. **Anonymous inner class**

---

## 48. How do you create an object of an inner class in Java?

To create an object of a **non-static inner class**, you must first create an object of the outer class:

```java
Outer outer = new Outer();
Outer.Inner inner = outer.new Inner();
```

## 49. What is the name of the compiled inner class in Java?

When an inner class is compiled in Java, the generated `.class` file is named using the format:


## 50. In what situations would you use an inner class in Java?

You might use an inner class in the following situations:

- When the inner class logically **belongs** to the outer class.
- When you need to **access private members** of the outer class.
- To **encapsulate helper classes** that should not be used outside the outer class.
- To **improve code organization** and **readability**.
- When the inner class is **not useful outside** the outer class context.

---

## 51. Explain the difference between a static class and a static inner class in Java.

Java does **not allow top-level static classes**. However, you can declare a **static inner class** inside another class.

| Feature                     | Static Class         | Static Inner Class            |
|----------------------------|----------------------|-------------------------------|
| Allowed in Java            | ❌ Not allowed        | ✅ Yes                         |
| Belongs to                 | N/A                  | Outer class                   |
| Can access outer members   | N/A                  | Only static members of outer  |
| Requires outer object?     | N/A                  | ❌ No                          |
| Example usage              | N/A                  | `Outer.Inner obj = new Outer.Inner();` |

---

## 52. What are the access modifiers available in Java?

Java provides four types of access modifiers:

| Modifier      | Scope                                                                 |
|---------------|-----------------------------------------------------------------------|
| `private`     | Accessible only within the same class                                 |
| (default)     | Accessible within the same package (no keyword specified)             |
| `protected`   | Accessible in the same package and by subclasses                      |
| `public`      | Accessible from anywhere                                              |

---

## 53. How do access modifiers behave in the context of inheritance and method overriding in Java?

- A **subclass** can override a method only if it is `public`, `protected`, or has package-private access (default) and both classes are in the same package.
- The **access level cannot be more restrictive** in the overridden method.
- You **can widen** access but **not narrow** it.

### Example:

```java
class A {
    protected void display() {}
}

class B extends A {
    @Override
    public void display() {} // Allowed: protected → public
}
```

## 54. What is Serialization and Deserialization in Java?

- **Serialization** is the process of converting a Java object into a byte stream so it can be saved to a file or sent over a network.
- **Deserialization** is the process of reconstructing the object from that byte stream.

### Use Cases:
- Storing object data permanently.
- Transmitting objects over a network (e.g., RMI, sockets).
- Deep cloning of objects.

---

## 55. How do you implement Serialization in Java?

To make a class serializable:

1. **Implement** the `java.io.Serializable` interface (marker interface – no methods to implement).
2. Use `ObjectOutputStream` to write the object to a file.
3. Use `ObjectInputStream` to read the object back.

### Example:

```java
import java.io.*;

class Student implements Serializable {
    int id;
    String name;

    Student(int id, String name) {
        this.id = id;
        this.name = name;
    }
}

public class SerializationExample {
    public static void main(String[] args) throws Exception {
        Student s1 = new Student(101, "Maan");

        // Serialization
        FileOutputStream fos = new FileOutputStream("student.ser");
        ObjectOutputStream oos = new ObjectOutputStream(fos);
        oos.writeObject(s1);
        oos.close();
        fos.close();

        // Deserialization
        FileInputStream fis = new FileInputStream("student.ser");
        ObjectInputStream ois = new ObjectInputStream(fis);
        Student s2 = (Student) ois.readObject();
        ois.close();
        fis.close();

        System.out.println("Deserialized Student: " + s2.id + " " + s2.name);
    }
}
```

## 56. How does the JVM operate on serialized objects in Java?

When working with serialized objects, the **JVM** follows these steps during **deserialization**:

1. **Class Metadata**:
   - The JVM uses metadata from the byte stream to identify the class of the serialized object.
   - It ensures that the class definition is available and compatible (checks `serialVersionUID` if defined).

2. **Object Creation Without Constructor**:
   - The JVM does **not** call the constructor of the class during deserialization.
   - Instead, it uses low-level operations to create the object in memory.

3. **Field Population**:
   - Fields are populated directly from the byte stream.
   - Only fields that are **not marked transient** or **static** are restored.

4. **ObjectInputStream**:
   - The class `ObjectInputStream` is responsible for reading the object from the byte stream and reconstructing it.

### Important Notes:
- If the class structure changes after serialization (e.g., fields added/removed), deserialization can fail unless handled using `serialVersionUID`.
- The deserialization process may throw exceptions like `InvalidClassException` if versions don't match or the class isn't found.

### Example:
```java
Student s = (Student) ois.readObject();
```

## 57. Can you declare a class as both private and protected in Java?

No, you cannot declare a class as both `private` and `protected` in Java.

- **Top-level classes** can only be:
  - `public`
  - *default* (no modifier)

- **Inner classes** can be `private`, `protected`, `public`, or default.
- `private protected` is invalid and will throw a compile-time error.

---

## 58. What is the purpose of the "transient" keyword in Java?

The `transient` keyword prevents a field from being serialized.

```java
class User implements Serializable {
    String username;
    transient String password; // won't be saved during serialization
}
```

## 59. Explain the difference between a method and a function in Java

In Java, the terms **method** and **function** are often used interchangeably, but technically:

- **Method**: A block of code that is associated with an object/class. It is always defined inside a class.
- **Function**: A general term for a block of reusable code that performs a specific task. Languages like C, Python allow functions outside of classes, but **Java does not**.

### Example:

```java
public class Calculator {
    public int add(int a, int b) { // This is a method
        return a + b;
    }
}
```

## 60. What is an Annotation in Java, and how do you create a custom annotation?

### ✅ What is an Annotation?

Annotations in Java are metadata (data about data) that provide information to the compiler or runtime. They do **not** change the actual execution of the code but can be used by tools, libraries, or frameworks (like Spring, Hibernate) for configuration or behavior control.

### 🔹 Common Built-in Annotations:
- `@Override` – Tells compiler that the method overrides a superclass method.
- `@Deprecated` – Marks method/class as deprecated.
- `@SuppressWarnings` – Instructs compiler to suppress specific warnings.

---

### 🛠️ How to Create a Custom Annotation:

```java
import java.lang.annotation.*;

@Retention(RetentionPolicy.RUNTIME) // Makes annotation available at runtime
@Target(ElementType.METHOD) // Specifies that annotation is applicable on methods
public @interface MyAnnotation {
    String value(); // Annotation element
}
```

## 61. What is the meaning of the Serial Version UID in Java Serialization?

### 🔹 What is SerialVersionUID?

`SerialVersionUID` is a unique identifier used during the **serialization and deserialization** process in Java. It ensures that a **serialized object** corresponds exactly to the version of the class used to deserialize it.

---

### 🔹 Why is it important?

When a class is serialized, its structure is saved along with the data. If you make changes to the class (like adding/removing fields), the JVM compares the `SerialVersionUID` of the serialized object with the current class.  
- ✅ If it matches, deserialization is successful.  
- ❌ If it doesn't, a `java.io.InvalidClassException` is thrown.

---

### 🔹 How to define it?

```java
private static final long serialVersionUID = 1L;
```

## 62. Explain the difference between the "path" and "classpath" variables in Java.

### 🔹 1. `PATH` Variable:

The `PATH` environment variable tells the operating system **where to find executable files** like `java`, `javac`, etc.

#### ✅ Purpose:
So that you can run Java tools from **any location in the terminal**.

#### 🧠 Example:
If `javac.exe` is in `C:\Program Files\Java\jdk1.8.0_241\bin`, then add this to `PATH`.

#### 🔍 Set Example (Windows):
```bash
set PATH=C:\Program Files\Java\jdk1.8.0_241\bin;%PATH%
```

## 63. Define and differentiate between Static Import, Static Block, Static Method, Static Variable, and Static Class in Java.

1. Static Import – Allows you to use static members (like sqrt()) without writing the class name (Math).
2. Static Block – Runs only once when the class loads, usually to initialize static variables.
3. Static Method – Belongs to the class, can be called without making an object.
4. Static Variable – A variable shared by all objects of the class.
5. Static Class – A nested class that can’t access non-static members of the outer class.

## 64. What are the differences between HTTP and HTTPS (HTTP Secure)?

- **HTTP** stands for HyperText Transfer Protocol.
- **HTTPS** stands for HyperText Transfer Protocol Secure.

- **HTTP** does not encrypt the data sent between browser and server.
- **HTTPS** encrypts the data using SSL/TLS, making it secure.

- **HTTP** uses port **80** by default.
- **HTTPS** uses port **443** by default.

- **HTTP** URLs start with `http://`.
- **HTTPS** URLs start with `https://`.

- **HTTP** is not secure for sensitive data like passwords or payments.
- **HTTPS** is secure and preferred for online transactions.

- **HTTP** is faster but less secure.
- **HTTPS** is slightly slower due to encryption but much safer.

## 65. What is the JVM (Java Virtual Machine)?

- **JVM (Java Virtual Machine)** is a part of Java Runtime Environment (JRE) that runs Java bytecode and makes Java programs platform-independent.
- It converts **.class** (bytecode) files into **machine code** for the underlying operating system.
- JVM handles **memory management, garbage collection, security, and exception handling** at runtime.

## 66. Explain the concept of platform independence in Java.
- Platform independence means Java code can run on any operating system without changing the code.
- Java compiler converts code into bytecode (.class file), not directly into machine code.
- This bytecode is executed by the JVM, which is available for all major platforms (Windows, Linux, Mac).
- So, "write once, run anywhere" is possible because of bytecode and JVM.

## 67. Is the JVM platform-independent?
- No, the JVM itself is not platform-independent.
- Each operating system has its own version of the JVM.
- But Java programs are platform-independent because JVM runs the same bytecode on any OS.
- So, Java achieves platform independence through JVM, even though the JVM is platform-dependent.

## 68. Who calls the main method in Java?
- The main method in Java is called by the **Java Virtual Machine (JVM)**.
- When a Java program starts, the JVM looks for the `public static void main(String[] args)` method and calls it to begin execution.

## 69. Differentiate between JDK, JRE, and JVM in Java.
- **JDK (Java Development Kit)** is a software package that includes tools to write, compile, and run Java programs (includes JRE + compiler + tools).
- **JRE (Java Runtime Environment)** is used to run Java programs; it contains JVM and libraries but not development tools like compiler.
- **JVM (Java Virtual Machine)** runs the Java bytecode and provides platform independence; it's part of the JRE.
- JDK is for **developers**, JRE is for **users**, and JVM is the **engine** that actually runs the code.

## 70. What are the different memory areas inside the JVM in Java?
- **Method Area**: Stores class-level data like static variables, method info, and runtime constant pool.
- **Heap**: Stores all the objects and their instance variables. It's the main area for dynamic memory allocation.
- **Stack**: Stores method calls, local variables, and partial results. Each thread has its own stack.
- **Program Counter (PC) Register**: Keeps track of the address of the currently executing instruction for a thread.
- **Native Method Stack**: Used to support native (non-Java) method calls, like methods written in C/C++.

## 71. Describe the Heap Area in the JVM.
- The Heap Area in JVM is used to store all Java objects and their instance variables at runtime.
- It is shared among all threads and is the main area for dynamic memory allocation.
- Objects in the heap are created using the `new` keyword.
- The Garbage Collector works in the heap to remove unused objects and free up memory.

## 72. What happens to the JVM when an error or exception occurs in Java?
- When an exception occurs, the JVM looks for a matching `catch` block to handle it.
- If the exception is not handled, the JVM prints an error message and terminates the program.

- When an error occurs (like `OutOfMemoryError`), it usually indicates a serious problem.
- Errors are not meant to be caught or handled normally, and JVM may stop the program immediately.

## 73. Is the String constant pool part of the Heap Area in Java?
- Yes, the String constant pool is part of the Heap Area in Java.
- It is a special memory region inside the heap that stores unique string literals.
- When you create a string using double quotes (`"Java"`), it goes into the string pool.
- If the same string already exists in the pool, Java reuses it to save memory.

## 74. Why was the String constant pool introduced when we have the Heap Area in Java? What are Native Method Stacks?
- The String constant pool was introduced to save memory and improve performance.
- Since strings are used very frequently in Java, storing duplicate string objects in the heap would waste memory.
- The string pool ensures that identical string literals are stored only once and reused when needed.

- Native Method Stacks are memory areas in JVM that store information for native (non-Java) method calls.
- These methods are written in languages like C or C++ and interact with Java using the Java Native Interface (JNI).
- Each thread has its own native method stack, just like the regular Java stack.

## 75. How does the class loader work in Java
- The class loader in Java is responsible for loading `.class` files into the JVM at runtime.
- It reads the bytecode of a class and brings it into memory when needed.
- Java uses a hierarchical class loading mechanism with three main class loaders:

  - **Bootstrap ClassLoader**: Loads core Java classes from the `rt.jar` (like `java.lang`).
  - **Extension ClassLoader**: Loads classes from the `ext` directory (`lib/ext`).
  - **Application ClassLoader**: Loads classes from the application's classpath (your project files).

- The class loader follows a **parent delegation model**, where it asks the parent loader first before loading a class itself.

## 76. What details are stored inside the Method Area in Java?
- The Method Area stores class-level data shared among all instances of a class.

- It contains:
  - Class names and fully qualified names.
  - Runtime Constant Pool (literals, symbolic references).
  - Static variables.
  - Field and method information (like names, return types, modifiers).
  - Code for methods and constructors.

- It is a shared memory area, used by all threads in the JVM.

## 77. Explain JIT (Just-in-Time) compilation in Java.
- JIT (Just-in-Time) compiler is a part of the JVM that improves the performance of Java programs.

- It converts frequently used bytecode into native machine code at runtime.

- This reduces the need to interpret the same code again and again, making execution faster.

- JIT compilation happens only for hot code (repeatedly executed code).

- It helps Java achieve performance close to native languages like C/C++.

## 78. Describe the Garbage Collector in Java.
- The Garbage Collector in Java automatically removes unused objects from the heap to free up memory.

- It runs in the background and identifies objects that are no longer reachable by any references.

- This helps prevent memory leaks and improves application performance.

- Java programmers don’t need to manually delete objects; the Garbage Collector handles it.

- Common algorithms used include Mark and Sweep, Generational GC, and G1 GC.

## 79. How do you invoke the garbage collector in Java?
- You can request the Garbage Collector in Java using:

```java
  System.gc();
```

## 80. Can you guarantee the invocation of the garbage collector in Java?
- No, you cannot guarantee the invocation of the garbage collector in Java.

- Calling `System.gc()` only **requests** the JVM to run the garbage collector.

- The JVM decides **whether to run it or not**, based on memory usage and other factors.

- So, garbage collection is **not under the programmer’s direct control**.

## 81. What is a .class file in Java?
- A `.class` file in Java is the **compiled version** of a `.java` source file.

- It contains **bytecode**, which is platform-independent code understood by the JVM.

- The Java compiler (`javac`) generates the `.class` file from the `.java` file.

- The JVM reads and executes this `.class` file at runtime.

## 82. Can you run a .class file on any JVM on different systems in Java?
- Yes, you can run a `.class` file on any JVM on different systems.

- This is possible because the `.class` file contains **platform-independent bytecode**.

- As long as a system has a **compatible JVM**, it can execute the `.class` file regardless of the operating system.

- This is what makes Java **platform-independent** — "write once, run anywhere".

## 83. What is bytecode in Java?
- Bytecode in Java is the intermediate code generated by the Java compiler from source code (`.java` file).

- It is stored in a `.class` file and is **not specific to any operating system**.

- The JVM reads and executes this bytecode on any platform.

- Bytecode makes Java **platform-independent** and secure, as it runs inside the JVM.

## 84. How do you increase or decrease the allocated RAM for a runtime JVM in Java?
- You can increase or decrease the allocated RAM for JVM using command-line options when running a Java program.

- Use these flags:
  - `-Xms` to set the **initial heap size**.
  - `-Xmx` to set the **maximum heap size**.

- Example:
```bash
  java -Xms256m -Xmx1024m MyProgram
```

## 85. What is an OutOfMemoryError in Java, and how can you solve it?
- `OutOfMemoryError` in Java occurs when the JVM runs out of memory and cannot allocate more objects.

- It usually happens due to:
  - Too many objects created without being garbage collected.
  - Memory leaks (objects are still referenced but not used).
  - Insufficient heap size settings.

- Solutions:
  - Increase heap size using `-Xmx` flag (e.g., `-Xmx1024m`).
  - Optimize code to remove unnecessary object creation.
  - Use memory analysis tools (like VisualVM or Eclipse MAT) to detect memory leaks.
  - Make sure unused objects are eligible for garbage collection by removing references.
 
## 86. What is a Heap Dump in Java?
- A Heap Dump in Java is a snapshot of the memory (heap) at a specific point in time.

- It contains all the objects that are in memory, their classes, fields, references, and sizes.

- Heap dumps are useful for analyzing memory leaks, high memory usage, and `OutOfMemoryError`.

- You can generate a heap dump using tools like `jmap`, VisualVM, or by configuring the JVM with:
```bash
  -XX:+HeapDumpOnOutOfMemoryError
```

## 87. Explain a few ways to fix memory issues in Java.
- **Increase Heap Size**: Use `-Xmx` to increase the maximum heap size if the application needs more memory.

- **Remove Unused Objects**: Set object references to `null` when they're no longer needed to help garbage collection.

- **Avoid Memory Leaks**: Don’t keep long-lived references to temporary objects (e.g., static collections).

- **Use Efficient Data Structures**: Choose memory-friendly collections like `ArrayList` instead of `LinkedList` when possible.

- **Optimize Loops & Object Creation**: Avoid creating objects inside frequently running loops unless necessary.

- **Analyze with Tools**: Use tools like **VisualVM**, **Eclipse MAT**, or **jconsole** to detect memory leaks and large object retention.

- **Use Weak References**: For cache-like structures, use `WeakReference` or `SoftReference` to allow garbage collection.

## 88. Differentiate between hashCode() and equals() in Java.
- `equals()` is used to compare two objects for **logical equality** (do they mean the same thing?).

- `hashCode()` returns an integer that represents the **memory bucket** for the object (used in hashing structures like HashMap).

- If two objects are **equal using `equals()`**, they **must have the same `hashCode()`**.

- But if two objects have the same `hashCode()`, they **may or may not be equal**.

- `equals()` is defined in `Object` class and often overridden for custom comparison.

- `hashCode()` is also in `Object` class and should be overridden when `equals()` is overridden.

## 89. Describe the real use of interfaces and abstract classes in Java.
- **Interface** is used to define a contract for what a class can do, **without saying how** it does it.

- It is best when you want to achieve **multiple inheritance** or create **pluggable architecture** (like `Runnable`, `Comparable`).

- **Abstract class** is used when you want to provide a **common base** with some shared code and some methods to be implemented by child classes.

- Use abstract class when classes share **common behavior** and **state**, but should also have their own specific implementations.

- Interfaces are for **"what to do"**, abstract classes are for **"what to do + partially how to do"**.

## 90. What is pluggable architecture?
- Pluggable architecture means designing your code in a way that lets you **easily plug in or swap out components** without changing the core system.

- It’s like having sockets — you can connect different devices (plugins) as long as they follow the same rules (interface).

- In Java, you can use **interfaces** to define common behavior, and then provide multiple implementations that can be plugged in at runtime.

- Example: JDBC API — Java defines interfaces for database access, and different vendors (like MySQL, Oracle) provide their own drivers (plugins).

- This makes the code more **flexible**, **maintainable**, and easy to **extend**.

## 91. Provide an example of a Marker Interface in Java.
- A Marker Interface is an interface with **no methods** or fields. It is used to **mark** a class for special behavior.

- Java’s built-in example: `Serializable` interface.

- When a class implements `Serializable`, it tells the JVM that this class’s objects can be converted to a byte stream.

Example:

```java
import java.io.Serializable;

public class Student implements Serializable {
    int id;
    String name;

    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }
}
```

## 92. Explain the real use of Marker Interfaces in Java.
- Marker Interfaces are used to **tag or mark** a class so that JVM or frameworks give it special treatment.

- They don’t have any methods — their purpose is only to **convey metadata**.

- JVM or libraries check if a class implements a marker interface and then **perform actions based on that tag**.

Real Use Cases:

- **Serializable** → Tells JVM that objects of this class can be serialized.
- **Cloneable** → Tells JVM that this class supports cloning using `clone()` method.
- **Remote** → Used in RMI to mark classes for remote method invocation.
- **ThreadSafe** (custom example) → You can create your own marker interface to tag safe-to-use classes in multithreading.

Why it’s useful:

- Makes the code more readable and organized.
- Adds metadata to a class **without annotations**.
- Helps frameworks (like Spring, Hibernate) decide behavior based on implemented markers.

Example:

```java
public interface MyMarker {}

public class TestClass implements MyMarker {
    // Now some framework or custom logic can check:
    // if (obj instanceof MyMarker) { do something special }
}
```

## 93. If we have an abstract method in an interface, can the same method be declared in an abstract class? In this case, why choose an interface over an abstract class in Java?
- Yes, if an interface has an abstract method, you **can declare the same method in an abstract class** too.

- But both serve different purposes:

Why choose an **interface** over an abstract class:

- **Multiple Inheritance**: Java doesn’t allow extending multiple classes, but a class can implement **multiple interfaces**.
- **Pure abstraction**: Interface is best when you want to define only the **structure** (what to do), not behavior.
- **Loose coupling**: Interfaces promote loose design — they don't force the class into any hierarchy.
- **Flexibility**: If your method is just a contract and may vary completely across classes, use an interface.

When to use an **abstract class** instead:

- When you want to provide **some default implementation**.
- When classes share **common state (fields)** or code.

Example:

```java
interface A {
    void show(); // abstract method
}

abstract class B {
    abstract void show(); // same method can exist here too
}
```

## 94. How can you achieve multiple inheritance in Java?
- Java **doesn’t support multiple inheritance with classes** (you can’t extend two classes).

- But Java allows **multiple inheritance through interfaces**.

- A class can implement **multiple interfaces** at the same time.

Example:

```java
interface A {
    void show();
}

interface B {
    void display();
}

class C implements A, B {
    public void show() {
        System.out.println("Showing A");
    }

    public void display() {
        System.out.println("Displaying B");
    }
}
```

## 95. Explain all the object-oriented programming concepts in Java.
- **1. Class**  
  A blueprint or template to create objects. It defines properties (variables) and behaviors (methods).  
  Example: `class Car { int speed; void drive() {} }`

- **2. Object**  
  An instance of a class. It holds actual values and can use class methods.  
  Example: `Car c = new Car();`

- **3. Inheritance**  
  Allows a class to inherit properties and methods from another class using `extends`.  
  Example: `class Bike extends Vehicle {}`

- **4. Polymorphism**  
  Means "many forms". Same method name can behave differently based on context.  
  - **Compile-time (Method Overloading)**  
    Example: `add(int, int)` and `add(double, double)`  
  - **Runtime (Method Overriding)**  
    Example: Subclass overrides parent class method.

- **5. Encapsulation**  
  Wrapping data and methods into a single unit (class) and hiding internal details using `private`.  
  Example: Private variables + public getters/setters.

- **6. Abstraction**  
  Hiding complex implementation and showing only essential details.  
  Achieved using **abstract classes** or **interfaces**.  
  Example: `abstract void startEngine();`

- **7. Association**  
  A general connection between two classes.  
  Example: A teacher can be associated with multiple students.

- **8. Aggregation**  
  "Has-a" relationship, but the contained object can exist independently.  
  Example: A department has teachers, but teachers can exist without department.

- **9. Composition**  
  Stronger "has-a" relationship. Contained object cannot exist without container.  
  Example: A house has rooms. If house is gone, rooms don’t exist.

## 96. Differentiate between Encapsulation and Abstraction in Java.
- **Encapsulation** means hiding data inside a class and restricting direct access using private fields and public methods.

- **Abstraction** means hiding complex logic and showing only the necessary features to the user.

- **Encapsulation** is implemented using **classes**, **getters/setters**, and **access modifiers**.

- **Abstraction** is implemented using **abstract classes** and **interfaces**.

- **Encapsulation** protects the internal state of an object.

- **Abstraction** focuses on hiding implementation details and exposing only essential functionality.

## 97. Discuss the significance of object-oriented programming in Java.
- Java is a purely object-oriented language (except for primitive types), so OOP is the foundation of Java programming.

- OOP makes code **modular** — code is organized into reusable objects.

- It improves **code readability** and **maintainability**.

- OOP allows for **reusability** through inheritance — no need to rewrite code.

- With **encapsulation**, data is protected and secure from unauthorized access.

- **Polymorphism** allows one interface to be used for different data types or actions — increases flexibility.

- **Abstraction** hides complexity and helps in building scalable applications.

- OOP helps in building **real-world models** — classes and objects represent real-world entities.

- OOP makes Java programs **easier to debug, test, and modify**, which is great for large projects.

## 98. How are polymorphism and abstraction related in object-oriented programming?
- **Abstraction** hides implementation details and shows only what is necessary.

- **Polymorphism** allows one interface (method name) to behave differently based on the object.

- They are related because **abstraction defines what to do**, and **polymorphism decides how to do it differently in different classes**.

- Abstraction is like saying: “Drive the vehicle” — you don’t care **how** it works.

- Polymorphism is like: Car, Bike, or Truck — sabka `drive()` method hai, but **sab alag tareeke se kaam karte hain**.

- So, **abstraction provides the structure**, and **polymorphism adds dynamic behavior** to that structure.

## 99. Is it possible to create an object of an abstract class inside the same abstract class in Java?
- **No**, you cannot directly create an object of an abstract class, **even inside the same abstract class**.

- Abstract class is incomplete — it may have unimplemented (abstract) methods, so Java doesn't allow creating its object.

- But you **can create an object of an anonymous subclass** of that abstract class inside itself.

Example:

```java
abstract class Test {
    abstract void show();

    public static void main(String[] args) {
        Test obj = new Test() {
            void show() {
                System.out.println("Inside anonymous class");
            }
        };
        obj.show();
    }
}
```

## 100. What does OOP (Object-Oriented Programming) refer to?
- OOP (Object-Oriented Programming) is a programming style that organizes code using **objects**, which are instances of **classes**.

- It helps in modeling real-world things using concepts like **class**, **object**, **inheritance**, **polymorphism**, **encapsulation**, and **abstraction**.

- Java follows OOP to make code more **modular**, **reusable**, **secure**, and **easier to manage**.

## 101. Define the concept of a Class in object-oriented programming.
- A **class** is a blueprint or template in object-oriented programming that defines the structure and behavior (variables and methods) of objects.

- It does not hold data itself, but is used to create objects that do.

- Example: `class Car { int speed; void drive() {} }`  
  - Here, `Car` is a class. You can create multiple `Car` objects from it.

## 102. Define the concept of an Object in object-oriented programming.
- An **object** is a real instance of a class that holds actual values and can perform actions defined by the class.

- It has **state (variables)** and **behavior (methods)**.

- Example: `Car c = new Car();`  
  - Here, `c` is an object of the `Car` class.

## 103. Explain the concept of Encapsulation in object-oriented programming.
- **Encapsulation** means wrapping data (variables) and code (methods) together inside a class.

- It also means **hiding the internal details** of how an object works and exposing only what is necessary.

- This is achieved by using **private variables** and providing **public getters/setters** to access them.

- It helps in **data protection**, **security**, and **maintainability**.

Example:

```java
class Student {
    private int marks;

    public void setMarks(int m) {
        marks = m;
    }

    public int getMarks() {
        return marks;
    }
}
```

## 104. Explain the concept of Abstraction in object-oriented programming.
- **Abstraction** means hiding the complex internal logic and showing only the important features to the user.

- It helps in focusing on **what an object does**, not **how it does it**.

- Achieved using **abstract classes** and **interfaces** in Java.

- It improves **code simplicity**, **security**, and **flexibility**.

Example:

```java
abstract class Animal {
    abstract void makeSound();
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}
```

## 105. What is Inheritance in object-oriented programming?
- **Inheritance** is the concept where one class (child) can **reuse** the properties and methods of another class (parent).

- It promotes **code reusability** and supports **hierarchical classification**.

- In Java, inheritance is done using the `extends` keyword.

Example:

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

## 106. Explain the concept of Polymorphism in object-oriented programming.
- **Polymorphism** means "many forms" — same method name can behave differently based on context.

- It allows **one interface** to be used for **different implementations**.

- There are two types in Java:
  1. **Compile-time Polymorphism** (Method Overloading)
  2. **Runtime Polymorphism** (Method Overriding)

Example of Overloading (Compile-time):

```java
class Math {
    int add(int a, int b) {
        return a + b;
    }
    double add(double a, double b) {
        return a + b;
    }
}
```

## 107. Can you provide real-life examples illustrating all the concepts of object-oriented programming?
- **1. Class**  
  - Blueprint of something.  
  - *Example:* "Car" is a class — it defines properties like color, speed, and behaviors like drive(), brake().

- **2. Object**  
  - Real instance of a class.  
  - *Example:* MyCar = new Car(); → MyCar is an object of class Car.

- **3. Inheritance**  
  - Child inherits features of parent.  
  - *Example:* "Dog" class extends "Animal" class. Dog can eat() (from Animal) and also bark().

- **4. Polymorphism**  
  - Same method, different behavior.  
  - *Example:* A remote control can operate TV, AC, Music System — same button, different devices.  
  - In Java: same method name, different class or input.

- **5. Encapsulation**  
  - Wrapping data and logic inside a single unit.  
  - *Example:* ATM machine — you insert card and enter PIN (you don’t see internal process).  
  - In Java: private data + public getter/setter.

- **6. Abstraction**  
  - Hiding complex internal logic and showing only what's needed.  
  - *Example:* Driving a car — you only use steering, brakes, and accelerator; you don’t need to know how engine works.

- **7. Association**  
  - Two classes connected.  
  - *Example:* A teacher teaches many students.

- **8. Aggregation**  
  - "Has-a" relationship (weaker).  
  - *Example:* A department has teachers, but teachers can exist without department.

- **9. Composition**  
  - Strong "has-a" relationship.  
  - *Example:* A house has rooms — if house is destroyed, rooms are gone too.

## 108. Discuss the differences between Inheritance and Polymorphism in object-oriented programming.
- **Inheritance** means acquiring properties and behaviors from a parent class.

- **Polymorphism** means having the same method behave differently depending on the object.

- Inheritance focuses on **code reusability**.

- Polymorphism focuses on **flexibility and dynamic behavior**.

- Inheritance is implemented using the `extends` keyword in Java.

- Polymorphism is implemented using **method overloading** (compile-time) and **method overriding** (runtime).

- Inheritance creates a **parent-child relationship** between classes.

- Polymorphism allows **one interface, multiple implementations**.

- Example of Inheritance: `class Dog extends Animal`

- Example of Polymorphism: `animal.sound()` gives different outputs for Dog, Cat, etc.

## 109. What is Overriding and Overloading in Java, and what is the difference between them?
- **Method Overloading** means having multiple methods with the **same name but different parameters** in the **same class**.

- **Method Overriding** means redefining a method of the **parent class** in the **child class** with the **same name and parameters**.

- **Overloading** is an example of **compile-time polymorphism**.

- **Overriding** is an example of **runtime polymorphism**.

- **Overloading** does not require inheritance.

- **Overriding** always requires inheritance.

Example of Overloading:
```java
class Math {
    int add(int a, int b) {
        return a + b;
    }
    double add(double a, double b) {
        return a + b;
    }
}
```

Example of Overriding:
```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}
class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}
```

## 110. Explain the rules for access modifiers when overriding methods in Java.
- When overriding a method, the **access level cannot be more restrictive** than the original method.

- You **can increase** the visibility, but **cannot decrease** it.

Rules:

- `public` method → must be overridden as `public`.

- `protected` method → can be `protected` or `public` in child class.

- `default` (no modifier) method → can be `default`, `protected`, or `public`, but **not private**.

- `private` methods → **cannot be overridden**, because they are not visible to subclasses.

## 111. What is a Covariant Type in Java?
- **Covariant Type** in Java means when an overridden method in the child class **returns a more specific type** than the method in the parent class.

- Java allows this from Java 5 onwards.

Example:
```java
class Animal {}
class Dog extends Animal {}

class Parent {
    Animal getAnimal() {
        return new Animal();
    }
}

class Child extends Parent {
    Dog getAnimal() { // Covariant return type
        return new Dog();
    }
}
```

## 112. Explain the concepts of IS-A and HAS-A relationships in Java.
- **IS-A** relationship means **inheritance** — one class is a subtype of another.

- It is used when a class **extends** another class or **implements** an interface.

- *Example:*  
  `class Dog extends Animal` → Dog **is an** Animal.

---

- **HAS-A** relationship means **association or composition** — one class contains a reference to another class.

- It is used to show that one class **uses or owns** another class.

- *Example:*  
  `class Car { Engine e = new Engine(); }` → Car **has an** Engine.

---

- **IS-A** focuses on **"kind of"**, while **HAS-A** focuses on **"part of"** or **"uses a"**.

- IS-A → inheritance (code reusability)  
- HAS-A → composition/aggregation (code flexibility and modularity)

## 113. What are Association, Composition, and Aggregation in Java?
- **Association** is a general relationship between two classes.

- It shows that **objects are connected**, but don’t depend on each other.

- *Example:* A teacher teaches students — both can exist independently.

---

- **Aggregation** is a **weaker form of HAS-A** relationship.

- The child can **exist independently** of the parent.

- *Example:* A department has teachers, but teachers can still exist if department is deleted.

- Represented by a **hollow diamond** in UML.

---

- **Composition** is a **stronger form of HAS-A** relationship.

- The child **cannot exist without** the parent.

- *Example:* A house has rooms — if house is destroyed, rooms are also gone.

- Represented by a **filled diamond** in UML.

---

Summary:

- Association → simple link (any direction)  
- Aggregation → weak ownership  
- Composition → strong ownership (lifespan tied)

## 114. Explain the usage and significance of the "super" and "this" keywords in Java.
- **`this` keyword** refers to the **current object** of the class.

- It is used to:
  - Access current class variables.
  - Call current class methods or constructors.
  - Pass current object as an argument.

Example:
```java
class Car {
    String color;
    Car(String color) {
        this.color = color; // 'this' refers to current object's color
    }
}
```

- `super` is used to refer to the **parent class** in Java.

- You can use `super` to:

1. **Call parent class constructor**  
   - Use `super()` inside the child class constructor to run the parent class constructor first.

2. **Call parent class method**  
   - If the child class has overridden a method, you can use `super.methodName()` to run the parent’s version.

3. **Access parent class variable**  
   - If both parent and child have the same variable name, `super.variableName` accesses the parent’s variable.

Example:
```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    void sound() {
        super.sound(); // Calls Animal's sound()
        System.out.println("Dog barks");
    }
}
```

## 115. What is an interface in Java, and can you instantiate an interface?
- An **interface** in Java is a **blueprint** of a class that only contains **abstract methods** (by default) and **constants**.

- It tells **what to do**, but **not how to do** — actual implementation is done in the class that implements it.

- You **cannot create an object (instantiate)** of an interface directly.

- But you can use an interface as a **reference type**, and assign it an object of a class that implements it.

Example:
```java
interface Animal {
    void makeSound();
}

class Dog implements Animal {
    public void makeSound() {
        System.out.println("Dog barks");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal a = new Dog(); // Interface reference, Dog object
        a.makeSound(); // Output: Dog barks
    }
}
```

## 116. Define multi-level and multiple level inheritance in Java.
- **Multi-level Inheritance** means a class inherits from a class, and another class inherits from that class.

- Example:
```java
class A {}
class B extends A {}
class C extends B {} // This is multi-level inheritance
```
- **Multiple Inheritance** = When one class tries to inherit from more than one class.

- Java does not support multiple inheritance with classes (to avoid confusion).

- But Java supports multiple inheritance using interfaces.

Example:
```java
interface A {}
interface B {}
class C implements A, B {}
```

## 117. What is the diamond problem in object-oriented programming, and how is it resolved?
- The **Diamond Problem** happens in **multiple inheritance** when a class inherits from two classes that both inherit from the same base class.

- It causes **confusion** about which method or variable to inherit from the top class.

Example in languages that support multiple class inheritance:
```java
class A {
    void show() { System.out.println("A"); }
}

class B extends A {
    void show() { System.out.println("B"); }
}

class C extends A {
    void show() { System.out.println("C"); }
}

// class D extends B, C { } // This would create a diamond problem!
```

#### How Java solves it:
- Java uses interfaces instead of multiple class inheritance.
- Even if two interfaces have the same method, you have to override it in your class — so there's no confusion.

```java
interface A {
    void show();
}

interface B {
    void show();
}

class C implements A, B {
    public void show() {
        System.out.println("Resolved by overriding");
    }
}
```

## 118. Explain the protected access specifier in the context of inheritance in Java.
- `protected` means the variable or method is:

  ✔️ Accessible **within the same class**  
  ✔️ Accessible **within the same package**  
  ✔️ Accessible in **subclasses (child classes)** even if they are in **different packages**

## 119. How is Exception Handling implemented in inheritance in Java, and what are the rules associated with it?

### ✅ Basic Rule:
- If a method in the **parent class** throws a **checked exception**, the **overridden method** in the **child class**:
  - Can throw the **same exception**,
  - Or a **subclass** of that exception,
  - Or **no exception at all**.

### ❌ But:
- The child class **cannot** throw a **broader exception** than the parent.

### ✅ For unchecked exceptions (like RuntimeException):
- No restriction. Can throw anything.

### ✅ Example:

```java
class Parent {
    void show() throws IOException { }
}

class Child extends Parent {
    void show() throws FileNotFoundException { } // ✅ Allowed (subclass of IOException)
}
```

## 120. Define Data Hiding in the context of inheritance in Java.
Data Hiding means restricting access to class members using access modifiers like `private`. In inheritance, private members of the parent class are not accessible in the child class. Access is given through public methods like getters and setters.

Example:
```java
class Parent {
    private int age = 30;

    public int getAge() {
        return age;
    }
}

class Child extends Parent {
    // cannot access 'age' directly
}
```

## 121. Compare and contrast String, StringBuilder, and StringBuffer in Java.
String is immutable (cannot be changed).  
StringBuilder is mutable and faster but not thread-safe.  
StringBuffer is mutable and thread-safe (synchronized), but slower than StringBuilder.

Example:
```java
String s = "Hello";
s = s + " World"; // new object created

StringBuilder sb = new StringBuilder("Hello");
sb.append(" World"); // modifies same object

StringBuffer sf = new StringBuffer("Hello");
sf.append(" World"); // thread-safe modification
```

## 122. What does it mean for a class to be immutable, and how can you make a class immutable in Java?
Immutable class means its objects cannot be changed once created.  
To make a class immutable:

1. Make class `final`
2. Make all fields `private` and `final`
3. No setters
4. Initialize fields via constructor
5. Return copies of mutable fields (if any)

Example:
```java
final class Person {
    private final String name;

    public Person(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}
```

## 123. What are the properties of an Immutable object in Java?
1. Its state cannot change after creation.  
2. All fields are `final` and `private`.  
3. No setters are provided.  
4. Class is often marked as `final` to prevent subclassing.  
5. It is thread-safe by default.  
6. Only getters are used to access data.

Example:
```java
final class Point {
    private final int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public int getX() { return x; }
    public int getY() { return y; }
}
```

## 124. Explain the differences between String literals and String objects in Java.
String literal is stored in the String pool.  
String object (created with `new`) is stored in the heap.

- Literals reuse memory if value is same.  
- Objects always create a new memory space.

Example:
```java
String s1 = "Hello";       // String literal
String s2 = "Hello";       // refers to same object as s1

String s3 = new String("Hello"); // new object in heap

System.out.println(s1 == s2); // true (same reference)
System.out.println(s1 == s3); // false (different reference)
```

## 125. Describe the concept of the String pool in Java.
String pool is a special memory area in Java where String literals are stored.  
If a new String literal is created and the same value exists in the pool,  
Java reuses the existing object to save memory.

Example:
```java
String s1 = "Java";
String s2 = "Java";

System.out.println(s1 == s2); // true (same pool reference)
```

## 126. What happens when you compare "==" and ".equals" for String and new String objects in Java?
`==` compares references (memory location).  
`.equals()` compares actual string content.

Example:
```java
String s1 = "Hello";
String s2 = "Hello";
String s3 = new String("Hello");

System.out.println(s1 == s2);      // true (same reference)
System.out.println(s1 == s3);      // false (different object)
System.out.println(s1.equals(s3)); // true (same content)
```

## 127. What are the results of comparing "==" and ".equals" for String and StringBuffer objects in Java?
`==` compares references.  
`.equals()` in StringBuffer does **not** compare content like String.

Example:
```java
String s = "Java";
StringBuffer sb = new StringBuffer("Java");

System.out.println(s == sb);         // false (different types)
System.out.println(s.equals(sb));    // false (String doesn't equal StringBuffer)
System.out.println(sb.equals(s));    // false (StringBuffer uses Object's equals)
```

## 128. Explain the output of the expression "A"+"B"+"C"+"D" in Java.
The expression `"A" + "B" + "C" + "D"` uses String concatenation.

Java combines them left to right:
→ "A" + "B" = "AB"  
→ "AB" + "C" = "ABC"  
→ "ABC" + "D" = "ABCD"

So, the output is:
```java
System.out.println("A" + "B" + "C" + "D"); // ABCD
```

## 129. Why are StringBuilder and StringBuffer classes declared as "final" in Java?
StringBuilder and StringBuffer are declared as `final` to prevent inheritance.  
This ensures their internal behavior (like thread safety in StringBuffer)  
is not changed or broken by subclassing.

It keeps them reliable, fast, and secure for string manipulation.

## 130. Why is String immutable in Java, whereas StringBuilder and StringBuffer are not?
String is immutable to ensure:

- Security (used in URLs, passwords)
- Thread safety (no need to sync)
- String pool optimization (memory reuse)
- Safe hashing (used in HashMap keys)

StringBuilder and StringBuffer are mutable for performance:  
they allow in-place changes without creating new objects.

## 131. How can you perform a Deep copy in the case of String objects in Java?
To perform a deep copy of a String, create a **new String object**.

Example:
```java
String original = "Hello";
String copy = new String(original);
```

## 131. What is the primary use of constructors in Java?
Constructors are used to **initialize objects** in Java.  
They set initial values for object fields when an object is created.

Example:
```java
class Person {
    String name;

    Person(String n) {
        name = n;
    }
}
```

## 132. Explain the concept of a default constructor in Java.
A default constructor is a **no-argument constructor** automatically provided by Java  
if no constructor is defined in the class.

It initializes object with default values (like 0, null).

Example:
```java
class Car {
    int speed;
}

// Java adds: Car() { }
Car c = new Car(); // uses default constructor
```

## 133. What is a parameterized constructor in Java, and can you explain its properties?
A parameterized constructor accepts **arguments** to initialize object fields.

Properties:
- Used to set custom values at object creation.
- If any constructor is defined, Java won't add a default one.

Example:
```java
class Student {
    String name;
    int age;

    Student(String n, int a) {
        name = n;
        age = a;
    }
}

Student s = new Student("Alice", 20);
```

## 134. What is a BitSet in Java, and what is its purpose?
BitSet is a class in Java used to store bits (0 or 1) efficiently.

Purpose:
- It handles large sets of boolean values.
- Saves memory compared to using boolean arrays.

Example:
```java
BitSet bs = new BitSet();
bs.set(0); // sets bit at index 0 to true
bs.set(3);

System.out.println(bs); // {0, 3}
```

## 135. How does your code behave when both a default constructor and a parameterized constructor are present in a Java class?
If both constructors are present, you can choose which one to use when creating an object.

Example:
```java
class Book {
    String title;

    Book() {
        title = "Unknown";
    }

    Book(String t) {
        title = t;
    }
}

Book b1 = new Book();          // uses default constructor
Book b2 = new Book("Java");    // uses parameterized constructor
```

## 136. Define constructor overloading, constructor overriding, and constructor chaining in Java.

1. **Constructor Overloading**:  
   - Same class, multiple constructors with different parameters.
   ```java
   class A {
       A() {}
       A(int x) {}
   }
   ```

2. **Constructor Overriding**:
   -  Not possible in Java. Constructors are not inherited, so they can't be overridden.
  
3. **Constructor Chaining**:
   - One constructor calls another using this() (same class) or super() (parent class).
   ```java
   class A {
    A() {
        this(10); // calls A(int)
    }
    A(int x) {
        System.out.println(x);
    }
   ```

## 137. Why are "this" and "super" used in constructors in Java? What access modifiers can be used with constructors?
**this** is used to:
- Call another constructor in the same class (`this(...)`)
- Refer to current object

**super** is used to:
- Call parent class constructor (`super(...)`)
- Must be the first statement in constructor

**Access modifiers** for constructors:
- `public`: object can be created from anywhere  
- `protected`: object can be created within package or subclasses  
- `default` (no modifier): object can be created within same package  
- `private`: object creation restricted (e.g., Singleton)

## 138. Is it possible to give a constructor a different name other than the class name in Java? Explain what a default constructor is.
❌ No, a constructor must have the **same name as the class**.  
If not, it's treated as a regular method.

**Default Constructor**:
- A no-argument constructor added by Java **if no constructor is defined**.
- It initializes object with default values.

Example:
```java
class Dog {
    int age;
}

// Java adds: Dog() { }

Dog d = new Dog(); // uses default constructor
System.out.println(d.age); // 0
```

## 139. What is a parameterized constructor in Java, and how is object creation related to constructors?
A parameterized constructor takes arguments to initialize object fields.

Example:
```java
class Car {
    String model;

    Car(String m) {
        model = m;
    }
}

Car c = new Car("BMW"); // object created using parameterized constructor
```

## 140. Explain the logical flow of constructors in the context of inheritance in Java. Is there a return type for constructors?
In inheritance, when a child object is created:

1. Parent class constructor runs first (`super()` is called automatically).
2. Then child class constructor runs.

Example:
```java
class A {
    A() {
        System.out.println("Parent");
    }
}

class B extends A {
    B() {
        System.out.println("Child");
    }
}

B obj = new B(); // Output: Parent → Child
```

## 141. What is a private constructor, a static constructor, and a final constructor in Java?
### 1. Private Constructor
- Restricts object creation from outside the class.
- Used in Singleton or Utility classes.

```java
class MyClass {
    private MyClass() { }
}
```

### 2. Static Constructor in Java

❌ Java does **not support static constructors** (unlike C#).

### Why?
- In Java, class-level initialization is handled using **static blocks**, not static constructors.

### Use static block instead:
```java
class Demo {
    static {
        System.out.println("Static block runs once when class is loaded");
    }

    public static void main(String[] args) {
        Demo d = new Demo(); // static block runs before this
    }
}
```


### 3. Final Constructor in Java

❌ Java does **not allow final constructors**.

### Why?
- `final` means "cannot be overridden."
- But constructors **cannot be inherited or overridden** in Java anyway.
- So making a constructor `final` has no meaning.

### If you try this:
```java
class Test {
    final Test() {
        // Error: modifier final not allowed here
    }
}
```

## 142. Can you have an abstract constructor, and can constructors exist within interfaces in Java?
## Abstract Constructor and Constructors in Interfaces (Java)

### 1. Abstract Constructor
❌ Not allowed in Java.

**Why?**
- Constructors are used to create objects.
- Abstract classes **cannot be instantiated**, so having a constructor in them makes no sense.

```java
abstract class A {
    // ❌ abstract A(); // Not allowed
}
```

#### ✅ But abstract classes can have regular constructors to help subclasses initialize fields.

```java
abstract class A {
    A() {
        System.out.println("Abstract class constructor");
    }
}
```

### Can Constructors Exist Within Interfaces in Java?

❌ **No**, constructors cannot exist in interfaces.

### Why?
- Interfaces **cannot be instantiated** directly.
- Constructors are used to **create objects**, so they don't make sense in interfaces.

### Example (Invalid):
```java
interface MyInterface {
    MyInterface() { } // ❌ Error: constructors not allowed
}
```

## 143. Is it possible to have both "this" and "super" in the same constructor in Java?

❌ **No**, you cannot use both `this()` and `super()` in the same constructor.

### Why?
- Both must be the **first statement** in a constructor.
- You can only call **one constructor** (either from same class or parent) as the first line.

### Example (Invalid):
```java
class A {
    A() { }
}

class B extends A {
    B() {
        this(10);     // ❌ Error if used with super()
        super();      // ❌ Only one allowed
    }

    B(int x) { }
}

// Use only one of them as the first statement:
class B extends A {
    B() {
        super();  // OK
    }
}
```

## 144. Can you call a subclass constructor from a superclass constructor in Java? 

❌ **No**, you cannot call a subclass constructor from a superclass constructor.

### Why?
- The subclass is **not yet created** when the superclass constructor runs.
- Java always creates the **superclass first**, then the subclass.

### Java Flow:
- When you create a subclass object, the superclass constructor runs **first** (via `super()`).
- Subclass constructors can call the superclass constructor using `super()`, but **not the other way around**.

### Example:
```java
class A {
    A() {
        System.out.println("A constructor");
        // super() allowed here only if A extends another class
        // Cannot call subclass constructor like B();
    }
}

class B extends A {
    B() {
        System.out.println("B constructor");
    }
}
```

## 145. How are exceptions handled in constructors in Java?

### Can constructors throw exceptions?
✅ Yes, constructors can throw **checked or unchecked exceptions**.

### How to handle them?

1. **Declare the exception** in constructor using `throws`.
2. **Handle** it using `try-catch` when creating the object.

### Example:
```java
class Test {
    Test() throws Exception {
        throw new Exception("Error in constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        try {
            Test t = new Test();
        } catch (Exception e) {
            System.out.println(e.getMessage()); // Output: Error in constructor
        }
    }
}
```

## 146. Explain the different types of constructors available in Java.
### Types of Constructors in Java

#### 1. Default Constructor
- No arguments.
- Added by Java if no constructor is written.
- Initializes object with default values.

```java
class A {
    // Java provides: A() { }
}
A obj = new A();
```

#### 2. Parameterized Constructor
   - Takes arguments to set field values during object creation.
   ```java
   class A {
    A(int x) {
        System.out.println(x);
    }
}

A obj = new A(10);
```

#### 3. Copy Constructor (Custom in Java)
   - Copies values from one object to another.
   - Not built-in like C++, but you can define your own.
```java
class A {
    int x;
    A(int x) { this.x = x; }

    A(A obj) {
        this.x = obj.x;
    }
}
```

#### 4. Private Constructor
   - Used to restrict object creation.
   - Common in Singleton or Utility classes.
```java
class A {
    private A() { }
}
```

## 147. Is it possible to have a constructor inside an abstract class in Java?
## Can You Have a Constructor Inside an Abstract Class in Java?

✅ **Yes**, abstract classes **can have constructors**.

### Why?
- Even though abstract classes **can't be instantiated directly**, their constructors are called when a **subclass** is instantiated.
- Used to **initialize common fields** or logic for all subclasses.

### Example:
```java
abstract class Animal {
    Animal() {
        System.out.println("Animal constructor");
    }
}

class Dog extends Animal {
    Dog() {
        System.out.println("Dog constructor");
    }
}

Dog d = new Dog();
// Output:
// Animal constructor
// Dog constructor
```

## 148. Explain the concept of constructor chaining in Java.

Constructor chaining in Java means calling one constructor from another constructor.  
It helps in reusing constructor logic either within the same class using `this()` or from the parent class using `super()`.

## 149. Explain the concepts of try-catch, try with multiple catch blocks, and try with resources in Java.
### try-catch
Used to handle exceptions. Code in `try` is monitored for errors, and `catch` handles them.

```java
try {
    int x = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}
```

### try with Multiple catch Blocks (Definition)

It allows handling **different types of exceptions** separately using multiple `catch` blocks after a single `try`.

Each `catch` block handles a specific exception type.

### Example:
```java
try {
    int[] arr = new int[2];
    arr[5] = 10;
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array index error");
} catch (Exception e) {
    System.out.println("General exception");
}
```

### try with Resources (Definition)

It is a try block that automatically **closes resources** (like files, streams) after use.  
The resources must implement the `AutoCloseable` interface.

### Example:
```java
try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
    System.out.println(br.readLine());
} catch (IOException e) {
    System.out.println("File error");
}
```

## 150. Describe the hierarchy of exceptions in Java.
### Exception Hierarchy in Java

- All exceptions are part of the `Throwable` class.

### Hierarchy:
Object └── Throwable ├── Error (serious issues, not handled by programs) └── Exception (problems that can be handled) ├── CheckedException (must be handled using try-catch or throws) │ ├── IOException │ └── SQLException └── UncheckedException (runtime errors, optional to handle) ├── NullPointerException └── ArithmeticException


### Summary:
- `Error`: Serious issues (e.g., OutOfMemoryError)
- `Exception`: Issues programs can handle
  - **Checked**: Must handle
  - **Unchecked**: Optional to handle

## 151. Differentiate between an exception and an error in Java.
## Difference Between Exception and Error in Java

- **Exception** is a condition that a program can handle using try-catch.  
- **Error** is a serious issue that cannot be handled by the program.  
- Exceptions belong to `java.lang.Exception`, errors to `java.lang.Error`.  
- Examples of exceptions: `NullPointerException`, `IOException`.  
- Examples of errors: `OutOfMemoryError`, `StackOverflowError`.

## 152. What is the difference between a runtime exception and a compile-time (CE) exception in Java?

   - **Runtime Exception** occurs during program execution.  
   - **Compile-Time Exception** (Checked Exception) is checked by the compiler.  
   - Runtime exceptions belong to `java.lang.RuntimeException`.  
   - Compile-time exceptions must be handled using try-catch or `throws`.  
   - Example (Runtime): `NullPointerException`, `ArithmeticException`.  
   - Example (Compile-Time): `IOException`, `SQLException`.

## 153. Explain the differences between checked exceptions and unchecked exceptions in Java.
   - **Checked Exceptions** are checked at compile-time.  
   - **Unchecked Exceptions** occur at runtime.  
   - Checked exceptions must be handled using try-catch or `throws`.  
   - Unchecked exceptions do not require handling.  
   - Checked: Subclasses of `Exception` (excluding `RuntimeException`).  
   - Unchecked: Subclasses of `RuntimeException`.  
   - Example (Checked): `IOException`, `SQLException`.  
   - Example (Unchecked): `NullPointerException`, `ArrayIndexOutOfBoundsException`.

## 154. Which exceptions are children of checked exceptions in Java?
#### Children of Checked Exceptions in Java

These are exceptions that must be handled during compilation.

#### Common Checked Exceptions:
- `IOException`
- `FileNotFoundException`
- `SQLException`
- `ClassNotFoundException`
- `InterruptedException`
- `ParseException`
- `InvocationTargetException`
- `NoSuchMethodException`

These all extend from the `Exception` class (excluding `RuntimeException`).

## 155. Describe the usage and purpose of try-catch-finally blocks in Java.
## try-catch-finally in Java

- **try**: Block of code that might throw an exception.  
- **catch**: Handles the exception thrown by try block.  
- **finally**: Executes code **always**, whether exception occurs or not (used for cleanup).

### Example:
```java
try {
    int x = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
} finally {
    System.out.println("This block always runs");
}
```

## 156. Provide examples of errors in Java.
- `OutOfMemoryError` – when JVM runs out of memory  
- `StackOverflowError` – infinite recursion  
- `VirtualMachineError` – JVM internal error  
- `AssertionError` – failed assertion  
- `LinkageError` – class file changes incompatibly  
- `NoClassDefFoundError` – class not found at runtime

## 157. Can you control errors in Java, and how would you do so?
❌ No, errors in Java are generally **not meant to be controlled**.

### Why?
- Errors represent **serious problems** (e.g., memory issues, JVM failures).
- Handling them may not make the program stable or safe.

### What You Can Do:
- **Avoid** errors through good design (e.g., avoid deep recursion to prevent `StackOverflowError`).
- **Log** errors for debugging if caught accidentally.
- **Do not** rely on catching or recovering from errors in code.

## 158. Explain the usage of "throw" and "throws" in Java for exception handling.
#### throw vs throws in Java

- **throw**: Used to explicitly **throw an exception** from code.
- **throws**: Declares that a method **might throw an exception**.

## 159. Can you use "try" without a "catch" block in Java?
## Can You Use try Without catch in Java?

✅ Yes, you can use `try` without `catch` **if you use `finally`**.

### Syntax:
```java
try {
    // risky code
} finally {
    // cleanup code
}
```

## 160. Explain the concept of "try with resources" in Java.
## try with Resources in Java

It is a special `try` block used to **automatically close resources** like files, streams, etc.

### Requirements:
- The resource must implement `AutoCloseable` interface.

### Example:
```java
try (BufferedReader br = new BufferedReader(new FileReader("data.txt"))) {
    System.out.println(br.readLine());
} catch (IOException e) {
    System.out.println("File error");
}
```

## 161. What types of resources can be used in a "try with resources" block in Java?
Any resource that implements the **`AutoCloseable`** interface can be used.

### Common Examples:
- `FileInputStream`
- `FileOutputStream`
- `BufferedReader`
- `BufferedWriter`
- `PrintWriter`
- `Scanner`
- `Connection` (from JDBC)
- `Statement` and `ResultSet` (from JDBC)

These resources are automatically closed after the try block completes.

## 162. How can you create custom exceptions in Java?
## Creating Custom Exceptions in Java

You can create custom exceptions by **extending the `Exception` or `RuntimeException` class**.

### Checked Custom Exception:
```java
class MyException extends Exception {
    MyException(String message) {
        super(message);
    }
}
```

### Unchecked Custom Exception:
```java
class MyRuntimeException extends RuntimeException {
    MyRuntimeException(String message) {
        super(message);
    }
}
```

### Usage:
```java
throw new MyException("This is a custom checked exception");
```

## 163. Describe the process of throwing an exception in Java.
## Throwing an Exception in Java

To throw an exception, use the **`throw`** keyword followed by an exception object.

### Syntax:
```java
throw new ExceptionType("Error message");
```

### Example:
```java
if (age < 18) {
    throw new IllegalArgumentException("Age must be 18 or above");
}
```

## 164. Explain the concept of checked and unchecked exceptions in the context of method overriding in Java.
## Checked and Unchecked Exceptions in Method Overriding (Java)

### Checked Exceptions:
- If a **parent class method** throws a checked exception, the **child class method** can:
  - Throw the **same** exception.
  - Throw a **subclass** of that exception.
  - Or **not throw** any exception.
- Child method **cannot throw a broader checked exception**.

### Unchecked Exceptions:
- There are **no restrictions** on throwing unchecked exceptions.
- Child class can throw any **RuntimeException**.

### Example:
```java
class Parent {
    void show() throws IOException { }
}

class Child extends Parent {
    void show() throws FileNotFoundException { } // OK (subclass of IOException)
}
```

## 165. What would happen if an unchecked exception is not handled properly in Java?
## If Unchecked Exception Is Not Handled in Java

- The program will **compile successfully**.
- At **runtime**, the exception will occur and **terminate the program** abnormally.
- The **JVM prints the stack trace**, showing where the error happened.

### Example:
```java
public class Test {
    public static void main(String[] args) {
        int x = 10 / 0; // Unchecked exception (ArithmeticException)
    }
}
```

### Output:
```java
Exception in thread "main" java.lang.ArithmeticException: / by zero
	at Test.main(Test.java:3)
```

## 166. What is Exception Propagation, and how does it work in Java?
## Exception Propagation in Java

Exception Propagation means **passing an exception up the call stack** until it is handled.

### How it works:
- If a method throws an exception and doesn't handle it,  
  the exception moves to the **caller method**.
- This continues until it's either caught or reaches the JVM.

### Example:
```java
void method1() {
    int x = 10 / 0; // ArithmeticException
}

void method2() {
    method1(); // exception propagates here
}

public static void main(String[] args) {
    try {
        method2(); // handled here
    } catch (ArithmeticException e) {
        System.out.println("Handled in main");
    }
}
```

## 167. What is multithreading in Java?  
**Multithreading **is a feature in Java that allows multiple threads to run concurrently, enabling efficient CPU usage and faster task execution.

## 168. How is multithreading different from multiprocessing?  
Multithreading uses multiple threads within a single process, sharing the same memory space. Multiprocessing uses multiple processes, each with its own memory space. Multithreading is lightweight and faster, while multiprocessing provides better fault isolation.

## 169. What are the benefits of multithreading?  
- Better CPU utilization by running tasks in parallel.  
- Faster program execution.  
- Efficient resource sharing among threads.  
- Improved application responsiveness.  
- Useful for real-time and interactive applications.

## 170. How do you create a thread in Java?  
You can create a thread in Java in two ways:  
1. By extending the `Thread` class and overriding the `run()` method.  
2. By implementing the `Runnable` interface and passing it to a `Thread` object.

## 171. What is the difference between `Thread` and `Runnable` interface?  
`Thread` is a class; `Runnable` is an interface.  
Extending `Thread` means you can’t extend any other class.  
Using `Runnable` is more flexible and preferred for sharing the same task across multiple threads.

## 172. What is the lifecycle of a thread in Java?  
A thread in Java goes through these stages:  
1. **New** – Thread is created.  
2. **Runnable** – Thread is ready to run.  
3. **Running** – Thread is executing.  
4. **Blocked/Waiting** – Thread is waiting for a resource or signal.  
5. **Terminated** – Thread has finished execution.

## 173. What are different states of a thread?  
- New: Thread is created but not started.  
- Runnable: Thread is ready to run.  
- Running: Thread is currently executing.  
- Blocked: Thread is waiting to access a locked resource.  
- Waiting: Thread is waiting indefinitely for another thread.  
- Timed Waiting: Thread is waiting for a specific time.  
- Terminated: Thread has completed or exited.

## 174. What is the use of the `start()` and `run()` methods?  
`start()` creates a new thread and calls the `run()` method in that thread.  
`run()` contains the code that executes when the thread runs, but calling it directly doesn't create a new thread.

## 175. Can we call `run()` method directly? What happens if we do?  
Yes, we can call `run()` directly, but it won’t create a new thread.  
It will execute like a normal method in the current thread.

## 176. What is the difference between `sleep()` and `wait()` in Java?  
`sleep()` pauses the current thread for a specific time and doesn’t release the lock.  
`wait()` pauses the thread until it's notified and it releases the lock during the wait.

## 177. What is thread priority and how is it set?  
Thread priority decides the order in which threads are scheduled for execution.  
It can be set using `setPriority(int)` method, with values from 1 (MIN) to 10 (MAX). Default is 5 (NORM).

## 178. What is thread synchronization?  
Thread synchronization is the process of controlling access to shared resources to prevent data inconsistency when multiple threads access them at the same time.

## 179. What is the difference between synchronized method and synchronized block?  
A synchronized method locks the whole method for a thread, while a synchronized block locks only a specific part of the code.  
Synchronized blocks give more control and are more efficient.

## 180. What is a daemon thread? How do you create one?
A daemon thread runs in the background and supports user threads. It ends when all user threads finish.  
You can create one using `setDaemon(true)` before calling `start()`.

## 181. What is the difference between user thread and daemon thread?
User threads perform main tasks and keep the program running.  
Daemon threads run in the background and stop automatically when all user threads finish.

## 182. What is thread deadlock and how to avoid it?  
Thread deadlock happens when two or more threads wait forever for each other to release resources.  

To avoid it:
- Lock resources in the same order.  
- Use timeout with locks.  
- Avoid nested locks when possible.

## 183. What is race condition and how to handle it?  
A race condition happens when multiple threads access and modify shared data at the same time, leading to unexpected results.  

To handle it:
- Use synchronization.  
- Use atomic variables or thread-safe classes.  
- Avoid shared mutable data when possible.

## 184. How does `join()` method work in threads?  
The `join()` method makes the current thread wait until the specified thread completes its execution.  
It ensures one thread finishes before another starts.

## 185. Can a thread be restarted once it is stopped?  
No, once a thread is stopped or completed, it cannot be restarted.  
You need to create a new thread object to run the code again.

## 186. What is the use of `yield()` method in threads?
The `yield()` method pauses the current thread and gives a chance to other threads of the same or higher priority to execute.  
It doesn’t guarantee that the current thread will stop running.

## 187. What are `wait()`, `notify()`, and `notifyAll()` methods?  
`wait()` makes a thread pause and release the lock until it is notified.  
`notify()` wakes up one waiting thread.  
`notifyAll()` wakes up all waiting threads on the same object.

## 188. What is the use of `ThreadGroup` in Java? 
`ThreadGroup` is used to group multiple threads into a single object so they can be managed together, like setting priority or interrupting all threads in the group.

## 189. What is the Executor framework in Java?  
The Executor framework provides a way to manage and control thread execution using a pool of threads, instead of creating new threads manually. It helps in better resource management.

## 190. What are `Callable` and `Future` interfaces?  
`Callable` is like `Runnable` but it can return a result and throw exceptions.  
`Future` is used to retrieve the result of a `Callable` task and check its status.

## 191. How is `synchronized` keyword different from `ReentrantLock`? 
`synchronized` is a keyword that automatically handles locking and unlocking.  
`ReentrantLock` is a class that gives more control, like trying to lock, timed lock, and manually unlocking.

## 192. What is the difference between `sleep()` and `yield()`?  
`sleep()` pauses the thread for a specific time and always gives up the CPU.  
`yield()` only hints to the scheduler to pause the thread, but it may continue if no other thread is ready.

## 193. How do you handle uncaught exceptions in threads?  
Uncaught exceptions in threads can be handled using `Thread.setDefaultUncaughtExceptionHandler()` or by overriding `ThreadGroup.uncaughtException()` method.

## 194. What is a thread pool and why is it used?  
A thread pool is a collection of pre-created worker threads.  
It is used to manage and reuse threads efficiently, reduce overhead of thread creation, and improve performance.

## 195. What is the difference between `synchronized` block and `Lock` interface? 
`synchronized` block is simpler and built-in, but has less flexibility.  
`Lock` (from `java.util.concurrent.locks`) provides more control, like try-lock, timed lock, and interruptible lock.

## 196. What is Legacy Code and Legacy Class?

## Legacy Code:
**Legacy code** refers to code that is still in use but was written using older practices or technologies that are no longer considered the best approach. It can be difficult to maintain or extend and often lacks proper documentation.

## Legacy Class:
A **legacy class** is an outdated class that was part of an earlier version of a programming language or framework, now replaced by more efficient or modern alternatives. They are still functional but are not recommended for new development.

## 197. What is Hash Collision?
A hash collision happens when two different objects produce the same hash code. This can cause problems in hash-based data structures like `HashSet` or `HashMap`.

## 198. What is diffrence between `Comparable` and `Comparator`?

**Comparable** and **Comparator** are both used to sort objects in Java, but they work differently.

### Comparable:
- It is in `java.lang` package.
- It has a method `compareTo(Object o)`.
- Used for **default or natural sorting**.
- Logic is written **inside the class**.
- Example:
```java
class Student implements Comparable<Student> {
    int marks;
    public int compareTo(Student s) {
        return this.marks - s.marks;
    }
}
```

### Comparator:
 - It is in java.util package.
 - It has a method compare(Object o1, Object o2).
 - Used for custom sorting.
 - Logic is written outside the class.
 - Example:
```java
class MarksComparator implements Comparator<Student> {
    public int compare(Student s1, Student s2) {
        return s1.marks - s2.marks;
    }
}
```

## 199. What is the default size of collection classes like ArrayList and Vector in Java?
Both `ArrayList` and `Vector` have a default size of **10**. ArrayList grows by 50%, while Vector doubles its size when full.

## 200. Explain the dynamic size increment in ArrayList and provide details about how it works.
ArrayList grows by **50%** of its current size when full, using `Arrays.copyOf()` to create a new larger array and copy elements.

## 201. What is the significance of the Load Factor in Java Collections, and can you provide an example?
The **load factor** determines when a HashMap will resize. It is the ratio between the number of elements and capacity. Default is `0.75`, meaning HashMap will resize when it is 75% full.

#### Example:
- **Capacity** = 16  
- **Load factor** = 0.75  
- HashMap will resize after adding **12 elements** (16 × 0.75).

## 202. Explain the concepts of Hashing and Rehashing in the context of collections.
#### **Hashing:**
- **Hashing** is a process used to map data (like keys) to an index (or bucket) in an array (hash table).
- Hashing uses a function (called a **hash function**) to calculate the index where a key-value pair should be stored.
- In Java collections like **HashMap**, the key's hash code is computed and used to decide the index in the array.

#### **Example of Hashing:**
  - Key: `"apple"`
  - Hash function calculates a hash value and maps `"apple"` to a specific index (bucket) in the array.
  
#### **Rehashing:**
- **Rehashing** happens when the current array (or hash table) is full or nearly full.
- When the **load factor** is exceeded (like 75% in HashMap), the collection resizes by creating a new, larger array and rehashes all the elements to new indices based on their hash values.
- This is done to reduce the chances of **collisions** (when multiple elements get mapped to the same index).

#### **Example of Rehashing:**
- Initially, a HashMap with capacity 16 is created, and once 12 elements are added (75% of 16), it resizes to double the size (32) and rehashes all the existing elements to the new array.

## 203. What is the load factor of Vector, and what is the default size of a Vector in Java?
#### **Default Size:**
- The default size of a `Vector` in Java is **10**. When a `Vector` is created without specifying an initial size, it starts with a size of 10.

#### **Load Factor:**
- The default **load factor** of a `Vector` is **2**. This means that when the `Vector` exceeds its capacity, it will **double its size** to accommodate more elements.

#### Example:
- Initial capacity = 10  
- Load factor = 2  
- After adding 10 elements, the `Vector` will resize to a capacity of 20.

## 204. Differentiate between Hashtable and HashMap in Java.

1. **Synchronized:**
   - **Hashtable** is synchronized and thread-safe.
   - **HashMap** is not synchronized and not thread-safe.

2. **Null Keys/Values:**
   - **Hashtable** does not allow **null** keys or values.
   - **HashMap** allows **one null key** and **multiple null values**.

3. **Performance:**
   - **Hashtable** is slower due to synchronization overhead.
   - **HashMap** is faster since it does not have synchronization.

4. **Inheritance:**
   - **Hashtable** is inherited from the **Dictionary** class (legacy).
   - **HashMap** is part of the **AbstractMap** class.
  
## 205. Compare and contrast Vector and ArrayList in Java.

1. **Synchronization:**
   - **Vector** is synchronized and thread-safe.
   - **ArrayList** is not synchronized and not thread-safe.

2. **Growth Factor:**
   - **Vector** grows by **doubling its size** when it reaches capacity.
   - **ArrayList** grows by **50% of its current size** when it reaches capacity.

3. **Performance:**
   - **Vector** is slower due to synchronization.
   - **ArrayList** is faster as it doesn’t have synchronization overhead.

4. **Null Elements:**
   - Both **Vector** and **ArrayList** allow **null** elements.

5. **Legacy:**
   - **Vector** is a legacy class, part of the **Vector** class in Java since **JDK 1.0**.
   - **ArrayList** is part of the **Collections Framework**, introduced in **JDK 1.2**.
  
## 205. Can the hash codes of two objects be the same or different in Java?
Yes, the hash codes of two objects can be **the same** (a hash collision) or **different** depending on the hash function and object properties.

## 206. What is Hashcode Collision, and how is it handled in Java?
A **hashcode collision** occurs when two objects have the same hashcode. In Java, it’s handled by using **linked lists** or **trees** (in case of `HashMap`), where objects with the same hashcode are stored in the same bucket but differentiated by **equals()**.

## 207. Explain the internal working of a HashMap in Java.
## Overview

`HashMap` in Java is a part of the `java.util` package and is used to store key-value pairs. It allows **one null key** and **multiple null values**, and it **does not maintain any order**.

---

## How it Works Internally

#### 1. **Hashing**
- When you insert a key-value pair in a HashMap, the key’s `hashCode()` method is called.
- This hash code is then converted into a **bucket index** using an internal function.
  
#### 2. **Buckets**
- Internally, HashMap has an array of **Node<K, V>** (also called buckets).
- Each bucket is like a **LinkedList** (or a **tree**, in some cases).

#### 3. **Storing Elements**
- If the bucket index is empty, the key-value pair is stored directly.
- If the bucket already has a value:
  - HashMap checks if the new key is **equal** to an existing key using `.equals()`.
  - If it is equal, the value is **updated**.
  - Otherwise, the new key-value pair is added to the bucket (chaining).

#### 4. **Handling Collisions**
- When two keys have the same bucket index, it's called a **collision**.
- Java handles this using:
  - **Chaining** with a LinkedList (Java 7 and below).
  - If more than 8 entries in a single bucket (Java 8+), LinkedList is replaced with a **Balanced Tree (Red-Black Tree)**.

#### 5. **Load Factor and Rehashing**
- HashMap has a **default load factor of 0.75**.
- When the map reaches 75% of its capacity, it **resizes** (doubles in size) and rehashes all the keys.

---

### Example Flow

```java
Map<String, String> map = new HashMap<>();
map.put("apple", "red");
```

- `"apple".hashCode()` is calculated.
- That hash is converted to an index.
- Value `"red"` is stored at that index in the bucket.
  
---

### Summary

- Uses array + LinkedList/tree for storage.
- Uses `hashCode()` and `equals()` for keys.
- Handles collisions with chaining or trees.
- Resizes automatically when load factor is exceeded.

---

### Java 8 Enhancements

- Bucket structure changes to Red-Black Tree when bucket size > 8.
- Improves performance in cases of heavy collisions.

## 208. Compare the usage of "for each" loops and Iterators in Java.
# For-each vs Iterator in Java

## For-each Loop
- Simple and readable.
- Used for **reading only**.
- Cannot remove/modify elements.
- Works on arrays and collections.

```java
for (String item : list) {
    System.out.println(item);
}
```

## Iterator
- Allows **removal** during iteration.
- More control (e.g., `hasNext()`, `remove()`).
- Slightly more code.

```java
Iterator<String> it = list.iterator();
while (it.hasNext()) {
    if (it.next().equals("x")) it.remove();
}
```

## Summary

| Feature        | For-each | Iterator |
|----------------|----------|----------|
| Simple         | ✅        | ❌        |
| Can remove     | ❌        | ✅        |
| Arrays support | ✅        | ❌        |
| Modify list    | ❌        | ✅        |

## 209. Differentiate between Iterator and ListIterator in Java.
# Iterator vs ListIterator in Java

## Iterator
- Used with **all collections**.
- **Forward** direction only.
- Can **remove()** elements.
- No index access.

```java
Iterator<String> it = list.iterator();
while (it.hasNext()) {
    it.next();
}
```

## ListIterator
- Used with **List only**.
- **Forward & backward** both.
- Can **add(), remove(), set()**.
- Has index info (`nextIndex()`, `previousIndex()`).

```java
ListIterator<String> it = list.listIterator();
while (it.hasNext()) {
    it.next();
}
while (it.hasPrevious()) {
    it.previous();
}
```

## Summary

| Feature             | Iterator | ListIterator |
|---------------------|----------|--------------|
| Direction           | Forward  | Both         |
| Applicable on       | All      | List only    |
| Add/Set support     | ❌        | ✅            |
| Index info          | ❌        | ✅            |

## 210. Explain the concepts of Comparable and Comparator in Java.
# Comparable vs Comparator in Java

## Comparable (java.lang.Comparable)
- Used to define **natural sorting**.
- Class implements it and overrides `compareTo()`.
- Can sort by **one field only**.

```java
class Student implements Comparable<Student> {
    int marks;
    public int compareTo(Student s) {
        return this.marks - s.marks;
    }
}
```

## Comparator (java.util.Comparator)
- Used for **custom sorting**.
- Create separate class or use lambda.
- Can sort by **multiple fields**.

```java
class SortByName implements Comparator<Student> {
    public int compare(Student a, Student b) {
        return a.name.compareTo(b.name);
    }
}
```

## Using Lambda with Comparator
```java
list.sort((a, b) -> a.name.compareTo(b.name));
```

## Summary

| Feature         | Comparable | Comparator         |
|-----------------|------------|--------------------|
| Package         | java.lang  | java.util          |
| Method          | compareTo()| compare()          |
| Sorting Type    | Natural    | Custom             |
| Multiple Fields | ❌          | ✅                  |
| Used by         | TreeSet, Collections.sort() | Collections.sort(), custom logic |

## 211. Provide Java code to sort employee objects using employee ID.
```java
import java.util.ArrayList;
import java.util.Collections;

class Employee implements Comparable<Employee> {
    private int id;
    private String name;

    public Employee(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public int compareTo(Employee o) {
        return this.id - o.id;
    }

    @Override
    public String toString() {
        return "Employee{" +
                "id=" + id +
                ", name='" + name + '\'' +
                '}';
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();

        employees.add(new Employee(34, "Armaan"));
        employees.add(new Employee(25, "Farman"));
        employees.add(new Employee(30, "Jagir"));

        Collections.sort(employees);

        employees.forEach(System.out::println);
    }
}
```

## 212. Provide Java code to sort employee objects using both employee ID and employee name.
```java
class Employee {
    private int id;
    private String name;

    public Employee(int id, String name) {
        this.id = id;
        this.name = name;
    }

    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    @Override
    public String toString() {
        return "Employee{" +
                "id=" + id +
                ", name='" + name + '\'' +
                '}';
    }
}

class EmployeeComparator implements Comparator<Employee> {
    @Override
    public int compare(Employee o1, Employee o2) {
        int idComparasion = Integer.compare(o1.getId(), o2.getId());
        if(idComparasion != 0) return  idComparasion;


        return o1.getName().compareTo(o2.getName());
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();

        employees.add(new Employee(30, "Armaan"));
        employees.add(new Employee(25, "Farman"));
        employees.add(new Employee(30, "Jagir"));

        employees.sort(new EmployeeComparator());

        employees.forEach(System.out::println);
    }
}
```

## 213. Why is the Iterable interface located in the java.lang package in Java?
### Explanation
- `Iterable` interface is in the `java.lang` package because it is a **core part of the Java Collection Framework**.
- It provides the **foundation for enhanced for-loops** (`for-each` loop).
- Being in `java.lang`, it is available **globally** without needing additional imports, making it easier to use with any collection.

```java
List<String> list = new ArrayList<>();
for (String item : list) {
    System.out.println(item);
}
```

### Summary
- Located in `java.lang` for **ease of use**.
- Ensures all collections are **iterable** using `for-each` loop.

## 214. Discuss the uses of the Arrays and Collections classes in Java.
The `Arrays` class provides utility methods like `sort()`, `binarySearch()`, and `copyOf()`. It's used for fixed-size arrays and primitive types, offering faster performance and lower memory usage.

```java
Arrays.sort(arr);
```

The `Collections` class offers methods like `sort()`, `reverse()`, and `shuffle()` for working with dynamic collections such as `ArrayList`. It supports objects and more complex operations.

```java
Collections.sort(list);
```

## 215. Explain why the Map interface is not part of the Collection interface hierarchy in Java.
The `Map` interface is not part of the `Collection` hierarchy because it represents a **different kind of data structure**. While `Collection` deals with single elements (like lists, sets), `Map` is designed to store **key-value pairs**, where each key is unique.

- `Collection` is used for storing **individual objects**.
- `Map` stores **key-value pairs** and does not extend `Collection`, since a `Map` contains no direct elements (only keys and values).

```java
Map<Integer, String> map = new HashMap<>();
map.put(1, "One");
map.put(2, "Two");
```

## 216. Can collections in Java contain null values, and what about concurrent collections?
Yes, regular collections in Java like `ArrayList`, `HashSet`, and `HashMap` can contain `null` values. However, some collections have limitations:
- **Lists**: Can contain `null` values.
- **Sets**: Can contain one `null` value (except `TreeSet`, which doesn't allow `null`).
- **Maps**: Can have `null` as both key and value, except `Hashtable` and `ConcurrentHashMap`.

For concurrent collections like `ConcurrentHashMap`:
- It does **not allow `null` keys or values** to avoid ambiguity and ensure thread safety.
  
```java
Map<Integer, String> map = new HashMap<>();
map.put(1, null);  // Allowed

ConcurrentMap<Integer, String> concurrentMap = new ConcurrentHashMap<>();
concurrentMap.put(1, null);  // Throws NullPointerException
```

## 217. Which collection types in Java can have null values?
In Java, the following collection types can contain `null` values:

- **Lists**: Can contain multiple `null` values (e.g., `ArrayList`, `LinkedList`).
- **Sets**: Can contain one `null` value (e.g., `HashSet`, `LinkedHashSet`). `TreeSet` does not allow `null`.
- **Maps**: Can have `null` as values (e.g., `HashMap`, `LinkedHashMap`), but only `HashMap` allows `null` keys. `TreeMap` does not allow `null` keys.
- **Queues**: Can contain `null` (e.g., `LinkedList`, `PriorityQueue`), but some queue implementations like `BlockingQueue` do not allow `null`.

```java
List<String> list = new ArrayList<>();
list.add(null);  // Allowed
```

## 218. Name some synchronized and non-synchronized collection classes in Java.
# Synchronized and Non-Synchronized Collection Classes in Java

## Synchronized Collection Classes:
- `Vector`
- `Hashtable`
- `Stack`
- `ConcurrentHashMap` (thread-safe, but not fully synchronized)

## Non-Synchronized Collection Classes:
- `ArrayList`
- `HashMap`
- `HashSet`
- `LinkedList`
- `TreeMap`
- `TreeSet`

To make non-synchronized collections thread-safe:
- `Collections.synchronizedList()`
- `Collections.synchronizedMap()`
- `Collections.synchronizedSet()`
- Or use concurrent collections like `CopyOnWriteArrayList`

## 219. What is Generics in Java?
Generics in Java allow you to write code that works with different data types while providing **type safety** at compile time.

It helps avoid `ClassCastException` and eliminates the need for casting.

For example, instead of using `Object`, you specify a type like `String` or `Integer`.

```java
List<String> list = new ArrayList<>();
```

Benefits:
- Compile-time type checking
- Code reusability
- Eliminates explicit type casting

## 220. Why were Generics introduced in Java?
Generics were introduced in Java to provide **type safety** and **eliminate the need for explicit type casting**.

Before generics, collections used `Object` type, which led to runtime errors.

With generics:
- Type errors are caught at compile-time.
- Code becomes more readable and reusable.
- No need for manual casting.

```java
List<String> list = new ArrayList<>();
String name = list.get(0); // No casting needed
```

## 221. Why is the Comparable interface implemented in classes when the hashCode method is present to compare objects?
The `Comparable` interface is used to **define the natural ordering** of objects, like sorting in ascending or descending order.

The `hashCode()` method is used in **hash-based collections** (like `HashMap`, `HashSet`) to efficiently locate objects, not for sorting.

So:
- `Comparable` → used for **ordering/sorting**.
- `hashCode()` → used for **hashing/lookup**.

Both serve different purposes and are **not interchangeable**.

## 222. What implementations are required for an object to be used as a key in a TreeMap in Java?
To use an object as a key in a `TreeMap`, it must:

- Implement the `Comparable` interface  
**or**
- Be used with a `Comparator` provided during `TreeMap` creation

This is because `TreeMap` stores keys in **sorted order**.

Also, the key class should have a consistent `equals()` and `compareTo()` logic to avoid unexpected behavior.

## 223. Explain different ways to iterate through a map in Java.
Different ways to iterate through a `Map` in Java:

1. **Using entrySet() with for-each loop**  
Access both key and value:
```java
for (Map.Entry<K, V> entry : map.entrySet()) {
    K key = entry.getKey();
    V value = entry.getValue();
}
```

2. **Using keySet()**  
Access only keys, then get values:
```java
for (K key : map.keySet()) {
    V value = map.get(key);
}
```

3. **Using values()**  
To iterate only over values:
```java
for (V value : map.values()) {
    // use value
}
```

4. **Using Iterator**  
For more control or removal during iteration:
```java
Iterator<Map.Entry<K, V>> it = map.entrySet().iterator();
while (it.hasNext()) {
    Map.Entry<K, V> entry = it.next();
}
```

5. **Using forEach() (Java 8+)**
```java
map.forEach((key, value) -> {
    // use key and value
});
```

## 224. What does the "Iterator.next()" method return in Java?
The `Iterator.next()` method returns the **next element** in the iteration.

It moves the cursor forward and gives the current element.

If no elements are left, it throws `NoSuchElementException`.

```java
Iterator<String> it = list.iterator();
String value = it.next(); // returns next element
```

## 225. How can you make any collection immutable in Java, ensuring that it cannot be modified (no add/remove/update actions allowed)?
To make a collection immutable in Java (no add/remove/update allowed), use:

### 1. `Collections.unmodifiableXXX()` methods:
```java
List<String> list = Collections.unmodifiableList(new ArrayList<>());
Set<String> set = Collections.unmodifiableSet(new HashSet<>());
Map<String, String> map = Collections.unmodifiableMap(new HashMap<>());
```

### 2. Java 9+ factory methods:
```java
List<String> list = List.of("a", "b");
Set<String> set = Set.of("x", "y");
Map<String, String> map = Map.of("key1", "val1", "key2", "val2");
```

These return **truly immutable** collections.

## 226. What is the use of a question mark (?) in collections and generics in Java?
The question mark `?` is a **wildcard** in Java Generics. It represents an **unknown type**.

### Uses:
- To write **flexible and reusable** code.
- Useful in methods that work with different types of collections.

### Types:
- `<?>` → Unbounded wildcard (any type)
- `<? extends T>` → Upper bounded (T or its subclass)
- `<? super T>` → Lower bounded (T or its superclass)

Example:
```java
List<?> list;               // accepts any type
List<? extends Number> n;   // accepts Integer, Double, etc.
List<? super Integer> i;    // accepts Integer, Number, Object
```

## 227. With which collection types do we use Comparable or Comparator in Java?
We use `Comparable` or `Comparator` with **sorted collection types** in Java:

### Collections that use them:
- `TreeSet` → for sorting elements
- `TreeMap` → for sorting keys
- `PriorityQueue` → for ordering elements
- `Collections.sort(List)` → for sorting lists

### Purpose:
- `Comparable` → natural ordering (implements `compareTo`)
- `Comparator` → custom ordering (passed to constructor or sort method)

## 228. What is the difference between Hashtable and ConcurrentMap in Java?
### Difference between `Hashtable` and `ConcurrentMap`:

- **Thread Safety**:
  - `Hashtable`: Synchronized, locks entire table.
  - `ConcurrentMap`: Thread-safe, uses finer-grained locking.

- **Performance**:
  - `Hashtable`: Slower due to full locking.
  - `ConcurrentMap`: Faster in multithreaded scenarios.

- **Null Keys/Values**:
  - `Hashtable`: No null key or value allowed.
  - `ConcurrentMap`: No null key or value allowed (same as `Hashtable`).

- **Modern Usage**:
  - `ConcurrentMap` (like `ConcurrentHashMap`) is preferred in concurrent apps.

## 229. Explain the hierarchy of the Collection interface, from Iterable to various interfaces and classes in Java.
### Hierarchy of the `Collection` Interface in Java:

1. **`Iterable`**  
   - The root interface for all collections, provides the `iterator()` method to iterate over elements.
   
2. **`Collection`**  
   - Extends `Iterable`. It represents a group of objects and provides basic collection operations like `add()`, `remove()`, `size()`, etc.

3. **`List`**  
   - Extends `Collection`, ordered collection with index-based access (e.g., `ArrayList`, `LinkedList`).

4. **`Set`**  
   - Extends `Collection`, unordered collection without duplicates (e.g., `HashSet`, `TreeSet`).

5. **`Queue`**  
   - Extends `Collection`, for handling elements in a FIFO (First In, First Out) order (e.g., `LinkedList`, `PriorityQueue`).

6. **`Map`**  
   - Not a direct descendant of `Collection`, but part of the Java Collections Framework. Stores key-value pairs (e.g., `HashMap`, `TreeMap`).

### Key Classes Implementing the Interfaces:
- **`ArrayList`** implements `List`
- **`HashSet`** implements `Set`
- **`PriorityQueue`** implements `Queue`
- **`HashMap`** implements `Map`

## 230. When should you implement the hashCode() and equals() methods in your class in Java?
You should implement `hashCode()` and `equals()` methods in your class when the class is used as a key in hash-based collections like `HashMap`, `HashSet`, or `Hashtable`.

### Why implement them:
1. **Consistency**: These methods ensure that the objects behave correctly in hash-based collections.
2. **Equality**: `equals()` defines object equality based on business logic.
3. **Hashing**: `hashCode()` ensures efficient lookup and retrieval in hash-based collections.

### General Rule:
- If `equals()` is overridden, `hashCode()` must also be overridden.
- Objects that are considered equal by `equals()` must have the same `hashCode()`.

Example:
```java
@Override
public boolean equals(Object obj) {
    // custom equality logic
}

@Override
public int hashCode() {
    // custom hash code logic
}
```

## 231. How can you allow duplicate values in hashCode in Java?
In Java, **duplicate values** can exist in a collection like `HashSet` or `HashMap` even if the objects have the same `hashCode()`. This is because `hashCode()` only determines the bucket in which objects are stored, but the **`equals()`** method determines whether two objects are considered the same.

To allow duplicate values in collections:

- **Override `hashCode()` and `equals()`** carefully to allow objects with the same `hashCode()` but different `equals()` to be treated as duplicates in your collection logic.

However, **duplicate keys** are not allowed in `HashMap`. But **duplicate values** can exist in a map, since values don’t need to be unique, only keys.

```java
Map<String, String> map = new HashMap<>();
map.put("key1", "value1");
map.put("key2", "value1"); // Duplicate value, allowed
```

### Key Takeaway:
- You can have duplicate **values** in a `HashMap`, but not duplicate **keys**.
- `hashCode()` should be consistent, but `equals()` may allow duplicates based on business logic.

## 232. How does ConcurrentHashMap work in a multithreaded environment in Java?
`ConcurrentHashMap` is a thread-safe implementation of `Map` in Java, designed to handle concurrency in a multithreaded environment efficiently.

### Key Features:
1. **Segmented Locking**: 
   - Divides the map into segments (buckets) and locks only the segment that needs to be modified. This allows multiple threads to access different segments concurrently.
   
2. **Fine-Grained Locking**:
   - Uses **locks at the bucket level**, so threads can perform operations (like `put`, `get`) on different entries simultaneously without interfering with each other.

3. **Atomic Operations**: 
   - Methods like `putIfAbsent()`, `remove()`, and `replace()` are atomic, ensuring thread-safety without requiring additional synchronization.

4. **No Global Lock**:
   - Unlike `Hashtable` or `synchronizedMap()`, `ConcurrentHashMap` does not lock the entire map for every operation, resulting in better performance in highly concurrent environments.

5. **Non-Blocking Reads**:
   - `get()` operations do not require locking and can be performed without blocking other threads.

### Example:
```java
ConcurrentHashMap<String, Integer> map = new ConcurrentHashMap<>();
map.put("key1", 10);
map.putIfAbsent("key2", 20);
```

### Conclusion:
`ConcurrentHashMap` is ideal for multithreaded applications where frequent read and write operations are needed without a significant performance penalty.

## 233. What is a Multivalue Map in Java?
A **Multivalue Map** in Java is a map where each key can be associated with **multiple values**.

### Common Implementations:
- **`MultiValueMap`** is typically used in libraries like **Spring**, where it extends `Map<K, List<V>>`.
- It allows a **single key to map to multiple values**, which is useful when dealing with scenarios like HTTP headers or form parameters.

### Key Characteristics:
1. **Multiple values per key**: Each key is associated with a collection (like `List`, `Set`, etc.) of values.
2. **Common Operations**: You can add multiple values for the same key and retrieve them as a collection.

### Example:
```java
MultiValueMap<String, String> map = new LinkedMultiValueMap<>();
map.add("key1", "value1");
map.add("key1", "value2");

System.out.println(map.get("key1"));  // Output: [value1, value2]
```

### Use Case:
- Common in scenarios like handling multiple query parameters or headers in HTTP requests.

## 234. How do you sort an array with and without using the Arrays or Collections classes in Java?
### Sorting an Array in Java:

1. **Using `Arrays.sort()`**:
   - Sorts the array in ascending order (natural order for primitive types or `Comparable` objects).
   ```java
   int[] arr = {3, 1, 4, 1, 5};
   Arrays.sort(arr);  // Sorts the array
   ```

2. **Without `Arrays.sort()` or `Collections.sort()`**:
   - **Using Bubble Sort (manual sorting)**:
   ```java
   int[] arr = {3, 1, 4, 1, 5};
   for (int i = 0; i < arr.length - 1; i++) {
       for (int j = 0; j < arr.length - i - 1; j++) {
           if (arr[j] > arr[j + 1]) {
               int temp = arr[j];
               arr[j] = arr[j + 1];
               arr[j + 1] = temp;
           }
       }
   }
   ```

   - **Using Selection Sort (manual sorting)**:
   ```java
   int[] arr = {3, 1, 4, 1, 5};
   for (int i = 0; i < arr.length - 1; i++) {
       int minIndex = i;
       for (int j = i + 1; j < arr.length; j++) {
           if (arr[j] < arr[minIndex]) {
               minIndex = j;
           }
       }
       int temp = arr[minIndex];
       arr[minIndex] = arr[i];
       arr[i] = temp;
   }
   ```

These are two common manual sorting algorithms you can use without relying on built-in classes.

## 235. What is a Priority Queue in Java?
A **Priority Queue** in Java is a data structure that stores elements in a way that allows efficient retrieval of the **highest or lowest priority element**.

### Key Features:
1. **Ordering**: 
   - Elements are ordered based on their priority (default is **natural ordering**, but you can define custom priority using `Comparator`).
   
2. **No Indexing**: 
   - Unlike arrays or lists, the elements in a priority queue are not accessible by index.

3. **Heap-Based Implementation**:
   - By default, Java's `PriorityQueue` is backed by a **min-heap** (smallest element has the highest priority). You can use a `Comparator` to create a max-heap.

### Example:
```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
pq.add(10);
pq.add(5);
pq.add(15);

System.out.println(pq.poll());  // Output: 5 (the smallest element)
```

### Use Cases:
- **Task Scheduling**: Prioritize tasks based on urgency.
- **Dijkstra’s Algorithm**: For finding the shortest path in graphs.

### Key Methods:
- `add(E e)`: Inserts an element.
- `poll()`: Removes and returns the highest priority element.
- `peek()`: Returns the highest priority element without removing it.

## 236. What is a Blocking Priority Queue in Java?
A **Blocking Priority Queue** in Java is a thread-safe variation of the `PriorityQueue` that supports blocking operations when the queue is empty or full.

### Key Features:
1. **Thread-Safety**:
   - It ensures that elements can be safely added and removed by multiple threads concurrently.

2. **Blocking Operations**:
   - **Blocking** means that if the queue is empty, threads trying to **remove** an element will wait until an element becomes available.
   - Similarly, if the queue is full, threads trying to **add** elements will wait until space is available.

3. **Used in Producer-Consumer Model**:
   - Commonly used in multi-threaded applications like **task scheduling** where threads wait for tasks to become available.

### Implemented in:
- `BlockingQueue` interface (extends `Queue`), and one of the most commonly used implementations is `PriorityBlockingQueue`.

### Example:
```java
BlockingQueue<Integer> queue = new PriorityBlockingQueue<>();
queue.put(10);   // Will block if the queue is full
int element = queue.take();  // Will block if the queue is empty
```

### Key Methods:
- `put(E e)`: Adds an element, blocking if the queue is full.
- `take()`: Removes and returns an element, blocking if the queue is empty.
- `offer(E e)`: Attempts to add an element, without blocking.

## 237. Is it possible to create an object of an interface in Java?
No, it is not possible to create an object of an **interface** in Java directly because an interface cannot have concrete implementations. It only defines method signatures without providing the actual behavior.

### Why?
- An **interface** is meant to be implemented by a class, and a class can then provide the concrete implementation for the methods defined in the interface.

### Solution:
- To create an object, a class must **implement the interface** and provide implementations for its methods.

### Example:
```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Bark");
    }
}

// Creating an object of the class implementing the interface
Animal dog = new Dog();
dog.sound();  // Output: Bark
```

### Alternative (Anonymous Classes):
You can use **anonymous classes** to create an object of an interface implementation in a single statement:
```java
Animal cat = new Animal() {
    public void sound() {
        System.out.println("Meow");
    }
};
cat.sound();  // Output: Meow
```

## 238. What is a Functional Interface in Java?
A **Functional Interface** in Java is an interface that has **exactly one abstract method**. These interfaces can have multiple **default** or **static** methods, but only one abstract method.

### Key Features:
1. **Single Abstract Method**: 
   - It must contain only one abstract method.
   
2. **Used with Lambda Expressions**: 
   - Functional interfaces are primarily used with **lambda expressions** and method references, enabling a functional programming style.

3. **`@FunctionalInterface` Annotation** (Optional):
   - This annotation is used to indicate that the interface is intended to be a functional interface. The compiler will give an error if it has more than one abstract method.
   
### Example:
```java
@FunctionalInterface
interface Greet {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        Greet greet = () -> System.out.println("Hello, World!");
        greet.sayHello();  // Output: Hello, World!
    }
}
```

### Common Functional Interfaces in Java:
- `Runnable`
- `Callable`
- `Comparator`
- `Function`
- `Predicate`
- `Consumer`

## 239. Can you declare variables in an interface in Java?
Yes, you can declare variables in an interface in Java, but with some restrictions:

### Key Points:
1. **Implicitly `public`, `static`, and `final`**:
   - All variables declared in an interface are **implicitly** `public`, `static`, and `final`. This means the variables are **constant** and can’t be changed.

2. **Initialization Required**:
   - Since the variables are `final`, they must be **initialized** when declared, and you cannot assign a new value to them after initialization.

### Example:
```java
interface MyInterface {
    int CONSTANT_VALUE = 100;  // Implicitly public, static, final
}

public class Main {
    public static void main(String[] args) {
        System.out.println(MyInterface.CONSTANT_VALUE);  // Output: 100
    }
}
```

### Conclusion:
- While you can declare variables in an interface, they are constants and cannot be modified.

## 240. List and differentiate between different types of cursors in Java.
In Java, cursors are used to iterate over data structures like collections. The different types of cursors in Java are:

### 1. **Iterator**:
   - **Purpose**: Used to iterate over the elements of a collection.
   - **Modification**: Supports removal of elements during iteration (`remove()` method).
   - **Example**: 
   ```java
   Iterator<String> iterator = list.iterator();
   while (iterator.hasNext()) {
       System.out.println(iterator.next());
   }
   ```

### 2. **ListIterator**:
   - **Purpose**: A specialized version of `Iterator` for **lists** (like `ArrayList` or `LinkedList`).
   - **Modification**: Allows **both forward and backward iteration** and modification of elements (using `add()`, `set()` methods).
   - **Example**:
   ```java
   ListIterator<String> listIterator = list.listIterator();
   while (listIterator.hasNext()) {
       System.out.println(listIterator.next());
   }
   ```

### 3. **Enumeration**:
   - **Purpose**: Legacy interface for iterating over collections (replaced by `Iterator`).
   - **Modification**: **No modification** of elements is allowed. Only **reading** is supported.
   - **Example**:
   ```java
   Enumeration<String> enumeration = vector.elements();
   while (enumeration.hasMoreElements()) {
       System.out.println(enumeration.nextElement());
   }
   ```

### Key Differences:
| Feature            | Iterator        | ListIterator     | Enumeration   |
|--------------------|-----------------|------------------|---------------|
| **Collection Type** | Any collection  | List (e.g., ArrayList) | Legacy Collections (e.g., Vector) |
| **Forward/Backward** | Forward only    | Forward & Backward | Forward only |
| **Modification**    | Remove only     | Add, Remove, Set | No modification |
| **Legacy**          | No              | No               | Yes           |

### Conclusion:
- `Iterator` and `ListIterator` are more commonly used in modern Java, while `Enumeration` is considered outdated.

## 241. What is Enumeration in Java?
**Enumeration** in Java is an interface that was part of the original version of Java. It is used to iterate over the elements in **legacy collections** such as `Vector`, `Stack`, and `Properties`.

### Key Features:
1. **Legacy Interface**:
   - It was replaced by `Iterator` in the **Java Collections Framework** but is still used in older classes.

2. **No Modifications**:
   - You cannot modify the collection during iteration (no `remove()` method).

3. **Simple Iteration**:
   - It only supports forward iteration, without the ability to traverse in reverse or modify the collection.

### Key Methods:
- `boolean hasMoreElements()`: Returns `true` if there are more elements to iterate over.
- `E nextElement()`: Returns the next element in the iteration.

### Example:
```java
Enumeration<String> enumeration = vector.elements();
while (enumeration.hasMoreElements()) {
    System.out.println(enumeration.nextElement());
}
```

### Difference from `Iterator`:
- **Enumeration** is more limited compared to `Iterator` (no modification allowed, only forward iteration).
- **Iterator** is more modern and flexible.

## 242. What is an Iterator in Java?
An **Iterator** in Java is an interface that provides a way to iterate over a collection of objects (such as a `List`, `Set`, or `Map`). It allows you to access each element of the collection sequentially without exposing the underlying structure.

### Key Features:
1. **Forward Iteration**:
   - Can only move **forward** through the collection, one element at a time.

2. **Modification**:
   - Allows **removal** of elements from the collection during iteration using the `remove()` method.

3. **Universal**:
   - Can be used on any collection that implements the `Iterable` interface.

### Key Methods:
- `boolean hasNext()`: Returns `true` if there are more elements to iterate.
- `E next()`: Returns the next element in the iteration.
- `void remove()`: Removes the last element returned by `next()` (optional).

### Example:
```java
Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    System.out.println(iterator.next());
}
```

### Difference from `Enumeration`:
- `Iterator` has additional methods like `remove()` and is more powerful than `Enumeration`, which only supports reading elements.

## 243. What is a ListIterator in Java?
A **ListIterator** in Java is an interface that extends the `Iterator` interface. It is specifically used to iterate over **list collections** (like `ArrayList` and `LinkedList`), allowing both **forward and backward** traversal.

### Key Features:
1. **Bidirectional Iteration**:
   - Allows iteration both **forward** and **backward** through the list.

2. **Modification**:
   - Supports adding, removing, and modifying elements during iteration (`add()`, `remove()`, `set()` methods).

3. **Indexed Iteration**:
   - Provides methods to get the index of the current element using `nextIndex()` and `previousIndex()`.

### Key Methods:
- `boolean hasNext()`: Returns `true` if there are more elements in the list (forward iteration).
- `E next()`: Returns the next element in the list.
- `boolean hasPrevious()`: Returns `true` if there are previous elements (backward iteration).
- `E previous()`: Returns the previous element.
- `void add(E e)`: Adds an element to the list.
- `void set(E e)`: Modifies the last element returned by `next()` or `previous()`.

### Example:
```java
ListIterator<String> listIterator = list.listIterator();
while (listIterator.hasNext()) {
    System.out.println(listIterator.next());
}
while (listIterator.hasPrevious()) {
    System.out.println(listIterator.previous());
}
```

### Difference from `Iterator`:
- `ListIterator` is more powerful than `Iterator` as it allows both forward and backward traversal and element modification.

## 244. Explain the differences between Enumeration and Iterator in Java.
**Enumeration** and **Iterator** are both used to iterate over collections, but they have key differences:

- **Enumeration** is part of legacy collections (like `Vector` and `Stack`) and only supports forward iteration. It has no `remove()` method, meaning you cannot modify the collection while iterating.

- **Iterator** is part of modern collections (like `ArrayList`, `HashSet`) and allows forward iteration with the ability to remove elements using the `remove()` method.

### Key Differences:
- **Enumeration** is older and limited to forward iteration, while **Iterator** provides more flexibility with element removal and supports modern collections.

## 245. Explain the differences between Enumeration and ListIterator in Java.
**Enumeration** and **ListIterator** are both interfaces used to iterate over collections, but they have significant differences:

- **Enumeration** is an older interface used in legacy collections (e.g., `Vector`, `Stack`). It only supports **forward iteration** and does not allow modifications during iteration.

- **ListIterator** is a more advanced interface used for **list collections** (e.g., `ArrayList`, `LinkedList`). It supports **bidirectional iteration** (both forward and backward) and allows modifications of the collection (adding, removing, or setting elements).

### Key Differences:
- **Forward/Backward Iteration**: `Enumeration` supports only forward iteration, while `ListIterator` supports both forward and backward.
- **Modification**: `ListIterator` allows modifying the list (using `add()`, `remove()`, and `set()`), while `Enumeration` does not support modifications.
- **Collection Types**: `Enumeration` is used in legacy collections; `ListIterator` is used in lists (e.g., `ArrayList`, `LinkedList`).

### Conclusion:
`ListIterator` is more powerful and flexible than `Enumeration`, making it suitable for modern collections and scenarios where both forward and backward iteration is needed.

## 246. Explain the differences between ListIterator and Iterator in Java.
**ListIterator** and **Iterator** are both interfaces for iterating over collections, but they have key differences:

- **Iterator** is used for **general collections** like `Set`, `List`, and `Queue`, and supports **forward iteration only**.
- **ListIterator** is a more specialized version of `Iterator` used for **lists** (e.g., `ArrayList`, `LinkedList`) and allows **both forward and backward iteration**.

### Key Differences:
- **Forward/Backward Iteration**: `Iterator` supports only forward iteration, while `ListIterator` supports both forward and backward.
- **Modification**: `ListIterator` allows adding, removing, and updating elements during iteration, whereas `Iterator` only supports element removal.
- **Collection Type**: `Iterator` works with any collection, while `ListIterator` works specifically with lists.
- **Additional Methods**: `ListIterator` provides methods like `previous()`, `nextIndex()`, and `previousIndex()` for more control over iteration.

### Conclusion:
`ListIterator` is more powerful than `Iterator` because it allows both directions of iteration and modification, making it ideal for working with lists.

## 247. Describe scenarios in which you would use Enumeration, Iterator, or ListIterator in Java.
### **Enumeration**:
- Used when working with **legacy collections** like `Vector`, `Stack`, or `Properties`.
- Ideal when you only need **forward iteration** and don't need to modify the collection during iteration.
- Example: Iterating through a `Vector` or `Stack` (older APIs).

### **Iterator**:
- Used for **modern collections** (e.g., `ArrayList`, `HashSet`, `HashMap`).
- Ideal when you need **forward iteration** and may want to **remove** elements during iteration.
- Example: Iterating through a `HashSet` and removing elements if necessary.

### **ListIterator**:
- Used specifically with **lists** like `ArrayList`, `LinkedList`, or `Vector`.
- Ideal when you need **bidirectional iteration** (both forward and backward).
- Useful if you need to **add**, **remove**, or **modify** elements during iteration.
- Example: Iterating through a `LinkedList` and needing to traverse in both directions or modify the list during iteration.

### Conclusion:
- Use `Enumeration` for legacy collections and simple forward iteration.
- Use `Iterator` for modern collections and forward iteration with removal capability.
- Use `ListIterator` when working with lists and requiring bidirectional iteration or modification during iteration.

## 248. List a few methods commonly used with Enumeration, Iterator, and ListIterator in Java.
### **Methods in Enumeration**:
- `boolean hasMoreElements()`: Checks if there are more elements.
- `E nextElement()`: Returns the next element.

### **Methods in Iterator**:
- `boolean hasNext()`: Checks if there are more elements.
- `E next()`: Returns the next element.
- `void remove()`: Removes the last element returned by `next()`.

### **Methods in ListIterator**:
- `boolean hasNext()`: Checks if there are more elements (forward iteration).
- `E next()`: Returns the next element (forward iteration).
- `boolean hasPrevious()`: Checks if there are previous elements (backward iteration).
- `E previous()`: Returns the previous element (backward iteration).
- `void add(E e)`: Adds an element during iteration.
- `void set(E e)`: Modifies the last element returned.
- `int nextIndex()`: Returns the index of the next element.
- `int previousIndex()`: Returns the index of the previous element.

### Conclusion:
- `Enumeration` provides basic iteration, while `Iterator` and `ListIterator` offer more control, with `ListIterator` allowing bidirectional iteration and modification of lists.

## 249. Discuss the differences between the "for each" loop and ListIterator/Iterator/Enumeration in Java.
### **"for each" loop**:
- Introduced in Java 5, the **"for each" loop** simplifies iteration over collections and arrays.
- Can only iterate **forward** and does not provide the ability to modify the collection.
- Suitable for **read-only operations** when you don’t need to remove or modify elements.

### **Iterator**:
- Provides more flexibility than the "for each" loop, allowing iteration and **removal** of elements during iteration using `remove()`.
- Works with any collection and supports **forward iteration**.
- Example: Removing an element while iterating through a `HashSet`.

### **ListIterator**:
- A more advanced version of `Iterator`, **ListIterator** allows **bidirectional iteration** (both forward and backward).
- Supports **adding**, **removing**, and **modifying** elements during iteration.
- Useful when working with **lists** like `ArrayList` or `LinkedList`.

### **Enumeration**:
- The oldest interface for iteration, used in legacy collections like `Vector` and `Stack`.
- Only supports **forward iteration** and lacks the ability to modify the collection during iteration.
- Not commonly used in modern Java.

### Key Differences:
- **"for each" loop** is the simplest for read-only operations but doesn't allow removal or modification.
- **Iterator** and **ListIterator** provide more control (e.g., removal, modification), with **ListIterator** allowing bidirectional iteration.
- **Enumeration** is outdated and not recommended for new code.

### Conclusion:
Use the **"for each" loop** for simple, read-only iterations. Use **Iterator** or **ListIterator** for more control, especially when modifications are needed.

## 250. Explain when to use a "for" loop and when to use Iterators in Java.
### **Using a "for" loop**:
- Use a **"for" loop** when you need to iterate over a collection or array by index.
- Ideal for situations where the **index** is important or when you need to modify the index (e.g., skipping elements, breaking at a certain condition).
- Works well with **arrays** or **lists** when the position of the element is needed.

### **Using Iterators**:
- Use **Iterator** when you want to iterate over a **collection** (like `ArrayList`, `HashSet`) and **don’t need the index**.
- Ideal when you need to **remove** elements during iteration (via `remove()` method).
- Iterator is preferred for **modern collections** and for situations where **modification** or **simplified iteration** (without worrying about indexes) is required.

### Key Differences:
- **"for" loop** is index-based and more suitable for **arrays** and cases where the element index is important.
- **Iterator** is collection-based and more flexible, especially for **modifying** the collection during iteration.

### Conclusion:
Use a **"for" loop** when you need index-based iteration or when working with arrays. Use **Iterator** when working with collections and when modification (removal) during iteration is needed.

## 251. Why does ArrayList implement interfaces like java.util.RandomAccess, java.lang.Cloneable, and java.io.Serializable in Java?
### **java.util.RandomAccess**:
- **ArrayList** implements `RandomAccess` to signal that it allows **efficient random access** to elements, meaning you can quickly access any element by its index. This is possible due to its underlying array structure.

### **java.lang.Cloneable**:
- **ArrayList** implements `Cloneable` to allow **cloning** of the list. This means you can create a **shallow copy** of an `ArrayList` using the `clone()` method.

### **java.io.Serializable**:
- **ArrayList** implements `Serializable` so that it can be **serialized** (converted into a byte stream) and **deserialized** (converted back from a byte stream). This is important for saving or transferring the list across different systems or sessions.

### Conclusion:
- **RandomAccess** improves access speed for large lists, **Cloneable** enables cloning, and **Serializable** ensures the list can be persisted or transmitted.

## 252. Why has ArrayList extended the java.util.AbstractList class in Java?
### **Reason for ArrayList extending java.util.AbstractList**:
- **AbstractList** provides a **partial implementation** of the `List` interface, reducing the need to implement all methods from scratch.
- It implements most of the `List` interface methods, leaving only a few (like `get(int index)` and `size()`) to be implemented by the subclass.
- **ArrayList** extends **AbstractList** to inherit this partial implementation, allowing it to focus on implementing the remaining methods (like `get()` and `size()`), thus reducing boilerplate code.

### Conclusion:
- **AbstractList** provides the base implementation for list operations, allowing **ArrayList** to focus on specific behaviors and optimizations related to array-backed lists.

## 253. Why has LinkedList extended the java.util.AbstractSequentialList class instead of java.util.AbstractList class in Java?
### **Reason for LinkedList extending java.util.AbstractSequentialList**:
- **AbstractSequentialList** provides a **partial implementation** of the `List` interface specifically optimized for **sequential access** collections like **LinkedLists**.
- **LinkedList** is backed by a **doubly linked list**, where accessing elements is inherently sequential (i.e., you must traverse the list to reach an element), unlike `ArrayList`, which allows **random access** due to its array-based structure.
- By extending **AbstractSequentialList**, **LinkedList** inherits methods that are more suited for **sequential iteration** (such as `get(int index)` and `remove(int index)`), and only needs to implement methods specific to linked-list operations.

### Conclusion:
- **AbstractSequentialList** is tailored for sequential access collections like `LinkedList`, making it more efficient and logical for `LinkedList` to extend it rather than `AbstractList`, which is better suited for random-access collections.


## 254. Why has LinkedList not implemented the java.util.RandomAccess interface in Java?
### **Why LinkedList does not implement java.util.RandomAccess**:
- **RandomAccess** is implemented by collections like **ArrayList** where **random access** to elements is efficient due to its **array-based structure**.
- **LinkedList**, on the other hand, is a **doubly linked list** where accessing an element by index requires **sequential traversal** from the head or tail, making random access inefficient.
- Therefore, **LinkedList** does not implement `RandomAccess` because its underlying structure does not provide **constant time random access**, and it would be misleading to indicate otherwise.

### Conclusion:
- **LinkedList** is optimized for sequential access, and implementing `RandomAccess` would imply capabilities it doesn’t offer efficiently.

## 255. What is a Marker Interface in Java, and can you provide examples related to ArrayList and LinkedList?
### **What is a Marker Interface in Java?**
- A **Marker Interface** in Java is an interface that does not contain any methods.
- It is used to **mark** a class with a special property, behavior, or capability, and is typically used for **metadata purposes**.
- The presence of the interface allows the class to be treated differently at runtime, often via reflection or other mechanisms.

### **Examples in ArrayList and LinkedList**:
- **Serializable**: Both **ArrayList** and **LinkedList** implement the `Serializable` marker interface, which indicates that these classes can be serialized (converted to a byte stream for storage or transfer).
- **Cloneable**: Both classes also implement the `Cloneable` interface, marking them as capable of being cloned using the `clone()` method.

### Conclusion:
- Marker interfaces like **Serializable** and **Cloneable** provide special behavior without adding methods to the class.

## 256. Why doesn't LinkedList support a constructor with a size parameter, like new LinkedList<>(size), in Java?
### **Why LinkedList doesn't support a constructor with a size parameter**:
- **LinkedList** is a **doubly linked list**, where elements are linked through pointers and not stored in contiguous memory like arrays.
- It doesn’t require a **predefined size** because it can **grow dynamically** as elements are added. The **size of the list** adjusts automatically without needing an initial size allocation.
- Unlike **ArrayList**, which requires an initial array size to be allocated, a **LinkedList** does not need this, as its nodes are added dynamically as needed.

### Conclusion:
- A constructor with a size parameter is unnecessary for **LinkedList** since it doesn’t rely on contiguous memory allocation and can grow dynamically.

## 257. Why are Java Vector and Stack classes considered obsolete or deprecated?
### **Why Java Vector and Stack are considered obsolete or deprecated**:
- **Vector** and **Stack** are considered obsolete because they are **synchronized** by default, which introduces **performance overhead** in multithreaded environments.
- The **synchronization** leads to slower performance when thread-safety is not necessary, especially in modern applications where **concurrent collections** like `ArrayList` and `LinkedList` provide better performance.
- The **Stack** class represents a **LIFO (Last In, First Out)** collection but can be replaced by **Deque** (Double-Ended Queue) or **LinkedList** in most scenarios, which offer more flexibility and better performance.

### Conclusion:
- **Vector** and **Stack** are legacy classes with performance issues due to synchronization, and modern alternatives like **ArrayList** and **Deque** are recommended.

## 258. Why does the indexing of arrays start at zero in Java?
### **Why does indexing of arrays start at zero in Java?**
- **Historical reasons**: Starting array indexing at **zero** originates from early programming languages like **C**. It simplifies memory addressing, where the index directly represents an **offset** from the start of the array.
- In **C**, the array name points to the **first element** of the array, and the index is used to calculate the memory address of each element. The expression `array[i]` is essentially the address of `array + i`, so the first element is at **offset 0**.
- **Java** follows this convention for consistency with other languages and for efficiency in memory access.

### Conclusion:
- **Zero-based indexing** is a widely adopted convention that simplifies memory calculations and is maintained for consistency and performance reasons in Java.

## 259. What are the differences between the Collection and Collections classes in Java?
### **Differences between Collection and Collections in Java**:

- **Collection** is an interface, while **Collections** is a utility class.
- **Collection** represents a group of objects (like List, Set, Queue), and **Collections** provides static methods for operations like sorting, searching, etc., on collections.
- **Collection** is part of the collection hierarchy, whereas **Collections** is not.
- **Collection** defines methods like `add()`, `remove()`, `contains()`, etc., while **Collections** contains utility methods like `sort()`, `reverse()`, `max()`, etc.

### Conclusion:
- **Collection** is the foundation of the collection framework, while **Collections** is a helper class to perform common tasks on collections.

## 260. Explain the extra methods available in the LinkedList class that are not present in the ArrayList class and are used for creating Queue and Stack in Java.
### **Extra Methods in LinkedList (not in ArrayList) for Queue and Stack**:

- **Queue Methods**:
  - **offer(E e)**: Adds an element to the end of the list (in the context of a queue).
  - **poll()**: Retrieves and removes the head of the list, returning `null` if the list is empty.
  - **peek()**: Retrieves, but does not remove, the head of the list, returning `null` if the list is empty.

- **Stack Methods**:
  - **push(E e)**: Pushes an element onto the stack (adds an element to the front).
  - **pop()**: Removes and returns the first element of the list (removes the top element of the stack).
  - **peek()**: Retrieves the first element of the list without removing it (top of the stack).

### Conclusion:
- **LinkedList** provides extra methods for **Queue** and **Stack** operations, making it suitable for these data structures, unlike **ArrayList**, which does not have these methods.

## 261. How does a Vector dynamically increase in size in Java, and what is the formula behind it?
### **How does a Vector dynamically increase in size in Java?**

- A **Vector** in Java automatically grows when elements are added beyond its current capacity.
- The default growth strategy is to **double its size** when the capacity is exceeded.

### **Formula**:
- **New Capacity = Old Capacity + (Old Capacity / 2)** (if default growth factor is 1.5).
- Alternatively, **New Capacity = Old Capacity * 2** (for default 100% growth, typically when no explicit growth factor is set).

### Conclusion:
- **Vector** dynamically increases its size based on a growth factor, either doubling or increasing by a fixed percentage.

## 262. Differentiate between the "peek" and "pop" methods of the Stack class in Java.
### **Differences between "peek" and "pop" methods of the Stack class in Java**:

- **peek()**:
  - Retrieves the top element of the stack.
  - Does **not** remove the element from the stack.
  - Returns `null` if the stack is empty.
  
- **pop()**:
  - Retrieves and **removes** the top element of the stack.
  - Throws `EmptyStackException` if the stack is empty.

### Conclusion:
- Use **peek()** when you want to view the top element without modifying the stack, and **pop()** when you need to both retrieve and remove the top element.

## 263. What is the default size of an ArrayList in Java?
### **Default size of an ArrayList in Java**:

- The default initial capacity of an **ArrayList** in Java is **10**.
- When the number of elements exceeds the initial capacity, the **ArrayList** grows dynamically by **50%** of its current size.

### Conclusion:
- The default size of an **ArrayList** is **10**, but it automatically resizes as elements are added.

## 264. What is the default size of a Vector in Java?
### **Default size of a Vector in Java**:

- The default initial capacity of a **Vector** in Java is **10**.
- When the number of elements exceeds the current capacity, the **Vector** grows by **doubling** its size.

### Conclusion:
- The default size of a **Vector** is **10**, and it doubles in size when more space is needed.

## 265. How can you dynamically increase the size of an ArrayList in Java, and what is the formula for it?
### **How to Dynamically Increase the Size of an ArrayList in Java**:

- **ArrayList** in Java automatically increases its size when elements are added beyond its current capacity.
- By default, **ArrayList** grows by **50%** of its current size when it exceeds its capacity.

### **Formula**:
- **New Capacity = Old Capacity + (Old Capacity / 2)** (default growth factor of 1.5).
- Alternatively, the growth factor can be set to **double the size** when needed.

### Conclusion:
- **ArrayList** grows automatically by a factor of 1.5 (default) when the capacity is exceeded.

## 266. Explain the differences between ArrayList and LinkedList in Java.
### **Differences between ArrayList and LinkedList in Java**:

- **Implementation**:
  - **ArrayList** uses a dynamic array for storage.
  - **LinkedList** uses a doubly linked list for storage.

- **Access time**:
  - **ArrayList** allows faster access by index (O(1)).
  - **LinkedList** has slower access by index (O(n)).

- **Insertions/Deletions**:
  - **ArrayList** is slower for insertions and deletions (O(n)) due to array resizing.
  - **LinkedList** is faster for insertions and deletions (O(1)) at the beginning or end.

- **Memory usage**:
  - **ArrayList** requires contiguous memory.
  - **LinkedList** uses more memory due to pointers for each element.

- **Use case**:
  - **ArrayList** is ideal for random access and when the size doesn't change frequently.
  - **LinkedList** is ideal for frequent insertions and deletions.

- **Thread-safety**:
  - Both **ArrayList** and **LinkedList** are **not synchronized**.

### Conclusion:
- **ArrayList** is better for random access, while **LinkedList** is more efficient for insertions and deletions, especially at the ends.

## 267. Describe the internal structure of an ArrayList in Java.
### **Internal Structure of an ArrayList in Java**:

- **ArrayList** internally uses a **dynamic array** to store its elements.
- It maintains an **array** for holding the actual data and a **size variable** to keep track of the current number of elements in the list.
- The **initial capacity** of the array is 10 by default, and it increases dynamically when more elements are added.
  
### **Growth Strategy**:
- When the **capacity** of the internal array is exceeded, the **ArrayList** grows by **50%** of its current size.
- The growth factor is typically **1.5x** (i.e., current size + current size / 2).

### **Key Components**:
- **elementData**: A private array of type `Object[]` that holds the elements.
- **size**: An integer to track the number of elements currently in the list.

### Conclusion:
- **ArrayList** uses a dynamically resizing array to manage its elements, with automatic resizing when the number of elements exceeds its capacity.

## 268. Describe the internal structure of a LinkedList in Java.
### **Internal Structure of a LinkedList in Java**:

- **LinkedList** in Java uses a **doubly linked list** structure to store elements.
- Each element is represented by a **node** containing:
  - **Data**: The value of the element.
  - **Next**: A reference to the next node in the list.
  - **Previous**: A reference to the previous node in the list.

### **Key Components**:
- **head**: A reference to the first node in the list.
- **tail**: A reference to the last node in the list.
- **size**: A variable to track the number of elements in the list.

### **Node Structure**:
- **Node Class**:
  - Holds the data.
  - Points to both the **next** and **previous** nodes.

### Conclusion:
- **LinkedList** uses a doubly linked list structure where each element is a node with references to the next and previous elements, allowing efficient insertions and deletions at both ends.

## 269. What is the load factor in an ArrayList in Java?
### **Load Factor in an ArrayList in Java**:

- **Load Factor** refers to the threshold when the **ArrayList** needs to grow its internal array.
- **ArrayList** itself does not directly use a load factor like `HashMap`, but the concept of **growth** is similar.
- **ArrayList** grows by 50% when the internal array is full, which can be thought of as a "load factor" of 0.75 (since it increases capacity by 1.5 times).

### Conclusion:
- **ArrayList** increases its size dynamically when elements exceed its current capacity, which is similar to how the load factor works in other collections.

## 270. Provide the formula used to calculate the new size of an ArrayList in Java.
### **Formula to Calculate the New Size of an ArrayList in Java**:

- **New Size Formula**:
  - **New Capacity = Old Capacity + (Old Capacity / 2)**

- By default, when an **ArrayList** exceeds its current capacity, the size increases by **50%** of the old capacity.

### Example:
- If the old capacity is **10**, the new capacity will be **10 + (10 / 2) = 15**.

### Conclusion:
- **ArrayList** grows by 1.5 times its current capacity when more elements are added.

## 271. Why is an ArrayList considered slow for modifications in Java?
### **Why is an ArrayList Considered Slow for Modifications in Java?**

- **ArrayList** is slow for modifications (insertions and deletions) because:
  1. **Resizing the Array**: When the **ArrayList** exceeds its capacity, it needs to resize the underlying array, which involves creating a new, larger array and copying the elements.
  2. **Shifting Elements**: Inserting or deleting an element at a specific position requires shifting all subsequent elements, which takes **O(n)** time.

### Conclusion:
- **ArrayList** provides fast access but is slower for modifications like insertions and deletions due to resizing and shifting elements.

## 272. Explain the mostly used methods of the List interface in Java.
### **Mostly Used Methods of the List Interface in Java**:

- **add(E e)**: Adds the specified element to the end of the list.
- **add(int index, E element)**: Inserts the specified element at the specified position in the list.
- **get(int index)**: Returns the element at the specified index.
- **set(int index, E element)**: Replaces the element at the specified position with the specified element.
- **remove(int index)**: Removes the element at the specified position in the list.
- **remove(Object o)**: Removes the first occurrence of the specified element from the list.
- **size()**: Returns the number of elements in the list.
- **isEmpty()**: Returns `true` if the list is empty.
- **contains(Object o)**: Returns `true` if the list contains the specified element.
- **indexOf(Object o)**: Returns the index of the first occurrence of the specified element, or -1 if not found.
- **clear()**: Removes all elements from the list.
- **toArray()**: Converts the list into an array.

### Conclusion:
- These methods provide essential functionalities like adding, removing, accessing, and searching for elements in a List.

## 273. Describe how to convert an array to an ArrayList in Java.
### **Converting an Array to an ArrayList in Java**:

You can convert an array to an `ArrayList` using the following methods:

1. **Using Arrays.asList()**:
   ```java
   String[] array = {"Apple", "Banana", "Cherry"};
   ArrayList<String> list = new ArrayList<>(Arrays.asList(array));
   ```

2. **Using a loop**:
   ```java
   String[] array = {"Apple", "Banana", "Cherry"};
   ArrayList<String> list = new ArrayList<>();
   for (String item : array) {
       list.add(item);
   }
   ```

### Conclusion:
- **Arrays.asList()** is the most convenient method, while the loop approach gives more control for modifications.

## 274. What are legacy classes in Java Collections?
### **Legacy Classes in Java Collections**:

- **Legacy classes** are part of the original Java Collections Framework, introduced before the collections framework was standardized in Java 1.2.
- These classes were replaced by the more powerful **Collections Framework** but are still supported for backward compatibility.

#### Key Legacy Classes:
1. **Vector**: A growable array of objects, similar to an `ArrayList`, but synchronized.
2. **Stack**: A subclass of `Vector` that implements a stack data structure (LIFO).
3. **Hashtable**: A key-value store similar to `HashMap`, but synchronized.
4. **Properties**: A subclass of `Hashtable` used for managing key-value pairs, typically for configuration settings.

### Conclusion:
- Legacy classes are still in use but are considered outdated in favor of newer, more flexible classes like `ArrayList`, `HashMap`, and `HashSet`.

## 275. In which version of Java was ArrayList introduced?
### **ArrayList Introduction in Java**:

- **ArrayList** was introduced in **Java 1.2** as part of the **Java Collections Framework**.
- Before Java 1.2, classes like `Vector` were commonly used for dynamic arrays.

### Conclusion:
- **ArrayList** became the preferred choice for resizable arrays starting from Java 1.2.

## 276. Compare and contrast arrays, ArrayList, and LinkedList in Java.
### **Comparison of Arrays, ArrayList, and LinkedList in Java**:

- **Array**: Fixed-size, contiguous memory, O(1) for random access, not dynamic in size, memory-efficient for known size.
- **ArrayList**: Dynamic size, O(1) for random access, O(n) for insertions/deletions (shifting), resizes automatically.
- **LinkedList**: Doubly linked list, O(n) for random access, O(1) for insertions/deletions at head/tail, more memory due to pointers.

### Conclusion:
- **Array** is optimal for fixed-size data, **ArrayList** for dynamic arrays, and **LinkedList** for frequent insertions/deletions.

## 277. What is meant by insertion order in Java?
### **Insertion Order in Java**:

- **Insertion order** refers to the order in which elements are added to a collection.
- In some collections, elements are stored in the order they were added, while others may not preserve this order.

#### Collections that preserve insertion order:
1. **ArrayList**: Maintains the order in which elements are added.
2. **LinkedHashMap**: Maintains insertion order of keys.
3. **LinkedHashSet**: Maintains insertion order of elements.

#### Collections that do not preserve insertion order:
1. **HashMap**: Does not guarantee order.
2. **HashSet**: Does not guarantee order.

### Conclusion:
- **Insertion order** is preserved in certain collections like `ArrayList`, `LinkedHashMap`, and `LinkedHashSet`.

## 278. How do you sort an ArrayList in Java?
### **Sorting an ArrayList in Java**:

You can sort an `ArrayList` using the following methods:

1. **Using `Collections.sort()`**:
   ```java
   ArrayList<Integer> list = new ArrayList<>(Arrays.asList(5, 3, 8, 1));
   Collections.sort(list);  // Sorts in ascending order
   ```

2. **Using a custom Comparator**:
   ```java
   ArrayList<String> list = new ArrayList<>(Arrays.asList("Apple", "Banana", "Cherry"));
   Collections.sort(list, (s1, s2) -> s1.length() - s2.length());  // Sort by length of strings
   ```

3. **Using `List.sort()`** (Java 8 and later):
   ```java
   ArrayList<Integer> list = new ArrayList<>(Arrays.asList(5, 3, 8, 1));
   list.sort(Comparator.naturalOrder());  // Sorts in ascending order
   ```

### Conclusion:
- **`Collections.sort()`** is the standard way to sort an `ArrayList`. For custom sorting, use a `Comparator`.

## 279. Is ArrayList synchronized in Java?
### **Is ArrayList Synchronized in Java?**

- **No, ArrayList is not synchronized** in Java.
- It is not thread-safe, meaning multiple threads modifying an `ArrayList` concurrently can cause data inconsistencies.

### Conclusion:
- For thread-safety, use `Vector`, `CopyOnWriteArrayList`, or manually synchronize the `ArrayList`.

## 280. How can you make an ArrayList synchronized in Java?
### **Making an ArrayList Synchronized in Java**

You can make an `ArrayList` synchronized using the `Collections.synchronizedList()` method:

```java
ArrayList<Integer> list = new ArrayList<>(Arrays.asList(1, 2, 3, 4));
List<Integer> synchronizedList = Collections.synchronizedList(list);
```

### Conclusion:
- `Collections.synchronizedList()` wraps the `ArrayList` with a synchronized version, making it thread-safe for concurrent access.

## 281. Can you provide examples of situations where ArrayList is commonly used in Java?
### **Common Use Cases for ArrayList in Java**

1. **Storing Dynamic Data**:
   - When the size of the collection is not known in advance and can grow or shrink, e.g., storing user inputs or results from a database query.

2. **Random Access to Elements**:
   - When you need fast access to elements by index, e.g., a list of items in an e-commerce app.

3. **Handling Variable-Length Data**:
   - When you need a resizable array, e.g., storing logs, records, or event histories that may change in length.

4. **Efficient Search/Update Operations**:
   - When searching for an element or updating a specific index is common, e.g., managing a list of products or students.

### Conclusion:
- **ArrayList** is ideal when you need resizable storage with fast random access and are not heavily modifying the collection (no frequent insertions or deletions).

## 282. What is a Stack, and what is a Vector class in Java?
### **Stack in Java**

- A **Stack** is a collection that follows the **LIFO** (Last In, First Out) principle.
- Operations include:
  - `push(E e)` – Adds an element to the top.
  - `pop()` – Removes and returns the top element.
  - `peek()` – Returns the top element without removing it.
- Example:
  ```java
  Stack<Integer> stack = new Stack<>();
  stack.push(10);
  stack.push(20);
  stack.pop();  // Returns 20
  ```

### **Vector in Java**

- A **Vector** is a dynamic array that grows automatically when elements are added.
- It implements the `List` interface and is synchronized.
- Operations include:
  - `add(E e)` – Adds an element.
  - `get(int index)` – Retrieves an element at a specific index.
  - `remove(Object o)` – Removes the first occurrence of an element.
- Example:
  ```java
  Vector<String> vector = new Vector<>();
  vector.add("Java");
  vector.add("Python");
  ```

### Conclusion:
- **Stack** is used for LIFO operations, and **Vector** is a thread-safe dynamic array that grows as needed.

## 283. Why are Stack and Vector classes used less frequently compared to List classes in Java?
### **Why Stack and Vector are Used Less Frequently Compared to List Classes in Java**

1. **Synchronization Overhead**:
   - Both **Stack** and **Vector** are synchronized, which makes them thread-safe but also slower due to synchronization overhead.
   - Modern alternatives like **ArrayList** and **LinkedList** (non-synchronized) are preferred in single-threaded contexts for better performance.

2. **Improved Alternatives**:
   - **Stack** has been replaced by **Deque** implementations (like **ArrayDeque**) for stack operations, offering better performance without synchronization overhead.
   - **Vector** has been replaced by **ArrayList**, which provides similar functionality but without synchronization, making it more efficient in most use cases.

3. **Lack of Flexibility**:
   - **Vector** has a fixed growth policy (doubling its size), which may not be ideal in all cases, whereas **ArrayList** grows dynamically at a more controlled rate.

4. **Deemphasized in Modern Java**:
   - **Stack** and **Vector** are considered legacy classes and are now rarely used in modern Java applications.

### Conclusion:
- **Stack** and **Vector** are less commonly used because more efficient, flexible, and non-synchronized alternatives like **ArrayList** and **Deque** are available.

## 284. Which implemented class of the List interface is typically used to design a Queue in Java?
### **Implemented Class of List Interface for Queue Design in Java**

- **LinkedList** is typically used to design a **Queue** in Java.
  - Implements the **Queue** interface and supports both FIFO (First In, First Out) operations.
  - Provides methods like:
    - `offer(E e)` – Adds an element to the queue.
    - `poll()` – Removes and returns the front element.
    - `peek()` – Returns the front element without removing it.

### Conclusion:
- **LinkedList** is ideal for implementing queues due to its efficient addition and removal of elements from both ends.

## 285. What is the purpose of the RandomAccess interface implemented by List classes in Java?
### **Purpose of the RandomAccess Interface in Java**

- The **RandomAccess** interface is a marker interface used to indicate that a class supports fast (constant-time) random access to its elements.
- Implementing **RandomAccess** allows **List** classes to provide faster indexing with methods like `get(int index)` and `set(int index, E element)`.

### Conclusion:
- **RandomAccess** is used to optimize performance for **List** implementations like **ArrayList**, where accessing elements by index is efficient.

## 286. Which List class is preferred in a multi-threaded application in Java?
### **Preferred List Class in Multi-threaded Applications in Java**

- **CopyOnWriteArrayList** is preferred in multi-threaded applications.
  - It provides thread-safety by creating a new copy of the list on each write operation, ensuring that reads are not blocked by writes.
  - Ideal for scenarios where read operations are frequent and write operations are infrequent.
  - Methods like `add()`, `remove()`, and `set()` create a new copy of the list, ensuring consistency across threads.

### Conclusion:
- **CopyOnWriteArrayList** is the best choice for multi-threaded environments with more read operations than writes, providing thread-safety without external synchronization.

## 287. What is the difference between "new ArrayList<>()" and "new ArrayList<>(size)" in Java, and can you explain with examples?
### **Difference Between `new ArrayList<>()` and `new ArrayList<>(size)` in Java**

1. **`new ArrayList<>()`**:
   - Initializes an **ArrayList** with a default initial capacity (usually 10).
   - Example:
     ```java
     ArrayList<Integer> list = new ArrayList<>();
     // Initially capacity is 10, increases as elements are added
     ```

2. **`new ArrayList<>(size)`**:
   - Initializes an **ArrayList** with the specified **initial capacity**. The list will not resize until it exceeds this capacity.
   - Example:
     ```java
     ArrayList<Integer> list = new ArrayList<>(20);
     // Initial capacity is 20, won't resize until more than 20 elements are added
     ```

### Conclusion:
- Use **`new ArrayList<>()`** for dynamic growth with default initial capacity, and **`new ArrayList<>(size)`** when you know the number of elements in advance to optimize memory allocation.

## 288. Which package do collection classes belong to in Java?
### **Package for Collection Classes in Java**

- All collection classes in Java are part of the **java.util** package.
  - Examples: 
    - **ArrayList**, **LinkedList**, **HashMap**, **TreeSet**, **PriorityQueue**, etc.
  
### Conclusion:
- The **java.util** package provides various collection classes and interfaces to store and manipulate groups of objects.

## 289. Explain the difference between "import java.util.*" and "import java.util.ArrayList;" in Java.
### **Difference Between `import java.util.*` and `import java.util.ArrayList;` in Java**

1. **`import java.util.*;`**:
   - Imports all classes and interfaces from the **java.util** package.
   - Allows access to any class within **java.util**, such as **ArrayList**, **HashMap**, **HashSet**, etc.
   - Example:
     ```java
     import java.util.*;
     ArrayList<Integer> list = new ArrayList<>();
     ```

2. **`import java.util.ArrayList;`**:
   - Imports only the **ArrayList** class from the **java.util** package.
   - Only **ArrayList** can be used directly in the code, other classes in **java.util** would need individual imports.
   - Example:
     ```java
     import java.util.ArrayList;
     ArrayList<Integer> list = new ArrayList<>();
     ```

### Conclusion:
- **`import java.util.*;`** imports all classes in **java.util**, while **`import java.util.ArrayList;`** imports only the **ArrayList** class specifically.

## 290. What is an Iterable, and what is an Iterator in Java?
### **Iterable and Iterator in Java**

1. **Iterable**:
   - An interface that represents a collection of objects that can be iterated (looped) over.
   - Classes implementing **Iterable** must define the `iterator()` method, which returns an **Iterator** object.
   - Example:
     ```java
     public class MyCollection implements Iterable<Integer> {
         @Override
         public Iterator<Integer> iterator() {
             // Returns an iterator for the collection
         }
     }
     ```

2. **Iterator**:
   - An interface used to iterate over the elements of a collection, one at a time.
   - Provides methods like:
     - `hasNext()` – Checks if more elements are available.
     - `next()` – Returns the next element.
     - `remove()` – Removes the current element from the collection.
   - Example:
     ```java
     Iterator<Integer> iterator = list.iterator();
     while (iterator.hasNext()) {
         System.out.println(iterator.next());
     }
     ```

### Conclusion:
- **Iterable** is used by collections to allow iteration, while **Iterator** is used to traverse through the elements in a collection.

## 291. When should you use an Iterator instead of a "for each" loop in Java?
### **When to Use Iterator Instead of "For Each" Loop in Java**

1. **Use Iterator when:**
   - **Element Removal**: You need to **remove** elements while iterating through the collection. **Iterator** provides the `remove()` method for safe removal.
   - **Complex Iteration**: You require more **control** over the iteration process (e.g., skipping elements, modifying the collection during iteration).
   - **Custom Iteration Logic**: You need to implement custom iteration behavior (e.g., traversing in reverse order).

   Example:
   ```java
   Iterator<Integer> iterator = list.iterator();
   while (iterator.hasNext()) {
       Integer num = iterator.next();
       if (num % 2 == 0) {
           iterator.remove(); // Removing even numbers
       }
   }
   ```

2. **Use "For Each" loop when:**
   - The collection is not being modified during iteration.
   - You simply need to **iterate over all elements** in the collection without removing or altering them.

   Example:
   ```java
   for (Integer num : list) {
       System.out.println(num);
   }
   ```

### Conclusion:
- Use **Iterator** for more control, especially when modifying the collection, and use **"for each" loop** for simple, straightforward iterations.

## 292. How can you iterate through a List in reverse order in Java?
### **Iterating Through a List in Reverse Order in Java**

1. **Using `ListIterator`**:
   - **ListIterator** allows reverse iteration using the `hasPrevious()` and `previous()` methods.
   - Example:
     ```java
     List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
     ListIterator<Integer> iterator = list.listIterator(list.size());
     while (iterator.hasPrevious()) {
         System.out.println(iterator.previous());
     }
     ```

2. **Using `for` loop**:
   - You can manually iterate through the list in reverse order by adjusting the index.
   - Example:
     ```java
     List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
     for (int i = list.size() - 1; i >= 0; i--) {
         System.out.println(list.get(i));
     }
     ```

3. **Using `Collections.reverse()`**:
   - You can reverse the list and then iterate through it normally.
   - Example:
     ```java
     List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
     Collections.reverse(list);
     for (Integer num : list) {
         System.out.println(num);
     }
     ```

### Conclusion:
- Use **`ListIterator`** for optimal reverse iteration, or a **`for` loop** for more control. You can also use **`Collections.reverse()`** for simple cases.

## 293. What are the differences between an Array and an ArrayList in Java?
### **Differences Between an Array and an ArrayList in Java**

- **Size**: Arrays have a fixed size, while ArrayLists have a dynamic size that grows automatically.
- **Type**: Arrays can hold any type, including primitives, while ArrayLists can only hold objects (reference types).
- **Performance**: Arrays offer better performance for basic operations, while ArrayLists may have overhead due to resizing.
- **Methods**: Arrays don’t have built-in methods for manipulation, while ArrayLists offer many built-in methods (add, remove, etc.).
- **Null Elements**: Both can store `null` elements.
- **Resizing**: Arrays cannot be resized, while ArrayLists automatically resize when capacity is exceeded.

### Conclusion:
- Use **Array** for fixed size and performance; use **ArrayList** for flexibility and resizing needs.

## 294. In which situations is an Array or an ArrayList best suited in Java?
### **Situations Best Suited for Array vs. ArrayList in Java**

- **Use an Array when**:
  - The size of the collection is known in advance and does not change.
  - You need to store primitive types (e.g., `int`, `char`) for better performance.
  - Performance is critical and resizing or dynamic growth is not necessary.
  - You need a multi-dimensional collection (e.g., 2D arrays).

- **Use an ArrayList when**:
  - The size of the collection is dynamic and can change during runtime.
  - You need to store objects and benefit from built-in methods (e.g., `add()`, `remove()`, `clear()`).
  - You require more flexibility, such as easy addition or removal of elements.
  - You prefer easier handling of growing data collections with automatic resizing.

### Conclusion:
- **Array** is best for fixed size and primitive types.
- **ArrayList** is better for dynamic, flexible collections of objects.

## 295. Why does an array start with an index of 0 in Java?
### **Why does an Array start with an Index of 0 in Java?**

Arrays in Java (and most programming languages) start with an index of 0 due to historical reasons and efficiency:
- **Historical Influence**: Many early programming languages, like C, started array indexing at 0, and this tradition was carried forward.
- **Memory Address Calculation**: Starting from index 0 simplifies the calculation of memory addresses. The element at index `i` is located at `baseAddress + (i * sizeOfElement)`, and with 0-based indexing, the first element is exactly at `baseAddress`.
- **Performance**: 0-based indexing can be more efficient, as it avoids the need for adjusting the index in memory calculations.

### Conclusion:
- 0-based indexing is an efficient convention that simplifies memory management and improves performance.

## 296. Can you add any type of element to an ArrayList in Java?
### **Can You Add Any Type of Element to an ArrayList in Java?**

No, you cannot add any type of element to an ArrayList in Java. The type of elements in an ArrayList is determined by its generic type. 

- **For objects**: You can only add objects of the specified type or its subclasses.
- **For primitives**: You can’t add primitive types like `int`, `char`, etc., directly, but you can use their wrapper classes (`Integer`, `Character`, etc.) due to autoboxing.

### Example:
```java
ArrayList<Integer> list = new ArrayList<>();
list.add(10); // Allowed
list.add("String"); // Compile-time error
```

### Conclusion:
- ArrayLists are type-safe, meaning you can only add elements of the specified type or its subclasses.

## 297. How can you make an ArrayList type-safe in Java?
### **How Can You Make an ArrayList Type-Safe in Java?**

To make an **ArrayList type-safe**, use **Generics**. Generics allow you to specify the type of elements an ArrayList can hold, ensuring that only elements of the specified type are added, thus preventing `ClassCastException`.

### Example:
```java
// Type-safe ArrayList
ArrayList<String> list = new ArrayList<>();
list.add("Hello"); // Allowed
list.add(123); // Compile-time error: incompatible types
```

### Key Points:
- **Generics** enforce type safety at compile time.
- You specify the type using angle brackets (`<>`), e.g., `ArrayList<String>`, `ArrayList<Integer>`, etc.

### Conclusion:
- Using Generics, you can ensure that only the specified type of elements can be added to the ArrayList, making it type-safe.

## 298. What is the time complexity of operations for Array and ArrayList in Java? For example, searching with an index is O(1), but without an index, it's O(n) in the worst case.
### **Time Complexity of Operations for Array and ArrayList in Java**

#### **Array**:
- **Access by index**: `O(1)` – Arrays allow direct access via indices.
- **Search (without index)**: `O(n)` – You need to iterate through all elements in the worst case.
- **Insert/Remove (middle/end)**: `O(n)` – Shifting elements is required.
- **Insert/Remove (at start)**: `O(n)` – Shifting all elements.

#### **ArrayList**:
- **Access by index**: `O(1)` – ArrayLists allow direct access via indices (backed by arrays).
- **Search (without index)**: `O(n)` – Linear search.
- **Insert/Remove (middle/end)**: `O(n)` – Shifting elements for insertion/removal.
- **Insert/Remove (at start)**: `O(n)` – Shifting all elements.

### Key Points:
- **Array**: Fast for access, but resizing or inserting/removing elements can be slow.
- **ArrayList**: Dynamic resizing, but also has overhead for resizing and shifting elements.

### Conclusion:
- **Arrays** are ideal for fixed-size collections and fast indexing.
- **ArrayLists** are flexible and good for dynamic sizes but may be slower for certain operations (like insert/remove).

## 299. What is the understanding of the basic methods in the Collection interface in Java?
### **Basic Methods in the Collection Interface in Java**

The `Collection` interface is the root interface in the Java Collections Framework. Here are some basic methods defined in it:

1. **add(E e)**: 
   - Adds the specified element to the collection.
   - Returns `true` if the collection changed as a result.

2. **remove(Object o)**:
   - Removes a single occurrence of the specified element.
   - Returns `true` if the collection contained the specified element.

3. **size()**:
   - Returns the number of elements in the collection.

4. **isEmpty()**:
   - Checks if the collection is empty.
   - Returns `true` if the collection contains no elements.

5. **contains(Object o)**:
   - Checks if the collection contains the specified element.
   - Returns `true` if the element is present.

6. **clear()**:
   - Removes all elements from the collection.

7. **iterator()**:
   - Returns an iterator to traverse the collection.

8. **toArray()**:
   - Converts the collection into an array.

### Conclusion:
These methods provide basic functionalities for manipulating and querying collections in Java, such as adding/removing elements, checking for emptiness, and iterating over elements.

## 300. What are the extra methods available in each interface, for example, List, in Java?
### **Extra Methods Available in Each Collection Interface (e.g., List) in Java**

#### **List Interface** (extends Collection):
- **add(int index, E element)**: 
   - Inserts the specified element at the specified position in the list.
  
- **remove(int index)**: 
   - Removes the element at the specified position.

- **get(int index)**: 
   - Returns the element at the specified position in the list.

- **set(int index, E element)**: 
   - Replaces the element at the specified position.

- **indexOf(Object o)**: 
   - Returns the index of the first occurrence of the specified element.

- **lastIndexOf(Object o)**: 
   - Returns the index of the last occurrence of the specified element.

- **subList(int fromIndex, int toIndex)**: 
   - Returns a view of the portion of the list between the specified `fromIndex` (inclusive) and `toIndex` (exclusive).

#### **Set Interface** (extends Collection):
- **addAll(Collection<? extends E> c)**: 
   - Adds all elements from another collection to the set.
  
- **retainAll(Collection<?> c)**: 
   - Retains only the elements that are present in both sets.

- **removeAll(Collection<?> c)**: 
   - Removes from the set all elements that are contained in another collection.

#### **Queue Interface** (extends Collection):
- **offer(E e)**: 
   - Adds the specified element to the queue.

- **poll()**: 
   - Retrieves and removes the head of the queue.

- **peek()**: 
   - Retrieves but does not remove the head of the queue.

#### **Deque Interface** (extends Queue):
- **addFirst(E e)**: 
   - Inserts the specified element at the front of the deque.

- **addLast(E e)**: 
   - Inserts the specified element at the end of the deque.

- **removeFirst()**: 
   - Removes and returns the first element of the deque.

- **removeLast()**: 
   - Removes and returns the last element of the deque.

### Conclusion:
Each collection interface adds specific methods based on its intended use, such as index-based operations for `List`, element ordering for `Queue`, or uniqueness for `Set`.

## 301. What is an Iterable, and why is it important in Java?
### **Iterable in Java**

- **Definition**:  
  The `Iterable` interface is the root interface for all collection classes in Java. It represents a collection of elements that can be iterated (looped) through.

- **Key Method**:
  - `iterator()`:  
    Returns an `Iterator` object, which allows you to iterate through the elements of the collection one by one.

- **Importance**:
  - **For-each loop**:  
    Any class implementing `Iterable` can be used in the enhanced `for-each` loop in Java, providing a convenient way to loop through elements.
  
  - **Polymorphism**:  
    It allows collections (like `List`, `Set`, `Queue`, etc.) to be treated uniformly, regardless of their specific implementations, enabling code reuse and simplicity.
  
  - **Flexibility**:  
    Since `Iterable` is implemented by all collection classes, you can iterate through any collection in Java (like `ArrayList`, `HashSet`, `TreeMap`, etc.) using the same approach.

### Example:
```java
List<String> list = new ArrayList<>();
list.add("A");
list.add("B");
list.add("C");

for (String s : list) {
    System.out.println(s);  // Iterates through the list using Iterable
}
```

## 302. How do you understand extra methods available in each interface, such as List, in Java?
### **Extra Methods in Interfaces like `List` in Java**

- **List Interface**:  
  The `List` interface extends `Collection` and represents an ordered collection that allows duplicate elements. It provides additional methods specific to lists.

- **Key Extra Methods in `List`**:
  - `add(int index, E element)`:  
    Inserts the specified element at the specified position in the list.
  
  - `get(int index)`:  
    Returns the element at the specified position in the list.
  
  - `remove(int index)`:  
    Removes the element at the specified position in the list.
  
  - `set(int index, E element)`:  
    Replaces the element at the specified position in the list with the specified element.
  
  - `indexOf(Object o)`:  
    Returns the index of the first occurrence of the specified element in the list.
  
  - `lastIndexOf(Object o)`:  
    Returns the index of the last occurrence of the specified element in the list.

- **Why These Methods Matter**:  
  These methods allow you to manipulate elements by their positions, making `List` a useful interface when order matters and when elements need to be accessed by index.

### Example:
```java
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
list.add(1, "Orange");  // Adds "Orange" at index 1

System.out.println(list.get(1));  // Outputs: Orange
```

## 303. What is an Iterable in Java?
### **Iterable in Java**

- **Definition**:  
  `Iterable` is an interface in Java that represents a collection of elements that can be iterated over. It is the root interface for all collection classes in Java.

- **Key Method**:
  - `iterator()`:  
    Returns an `Iterator` object that can be used to iterate over the elements of the collection.

- **Importance**:
  - **For-each Loop**:  
    Any class implementing `Iterable` can be used in the enhanced `for-each` loop, allowing easy iteration through elements.
  
  - **Uniformity**:  
    Since all collection types like `List`, `Set`, and `Queue` implement `Iterable`, they can all be iterated in the same way.

### Example:
```java
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");

for (String fruit : list) {
    System.out.println(fruit);  // Iterates through the list
}
```

## 304. In which situations is an Array preferred in Java?
### **When to Use an Array in Java**

- **Fixed Size**:  
  Arrays are preferred when you know the exact number of elements in advance and the size will not change dynamically.
  
- **Performance**:  
  Arrays provide faster access to elements (O(1) time complexity for index-based access), making them ideal for performance-critical applications.
  
- **Memory Efficiency**:  
  Arrays are more memory-efficient compared to other collection types, especially when the size is fixed.
  
- **Primitive Types**:  
  When dealing with primitive types (like `int[]`, `char[]`), arrays avoid the overhead of autoboxing and provide better performance.

- **Low Overhead**:  
  Since arrays don’t have the extra functionality of collection classes, they incur less memory overhead.

### Example:
```java
int[] numbers = new int[10];  // Fixed-size array
numbers[0] = 1;  // Direct access
```

## 305. In which situations is an ArrayList preferred in Java?
### **When to Use an ArrayList in Java**

- **Dynamic Size**:  
  Use `ArrayList` when the number of elements is not known in advance and you expect the size to change dynamically (elements added or removed).

- **Random Access**:  
  `ArrayList` is ideal when you need fast random access to elements (O(1) time complexity for index-based access).

- **Built-in Methods**:  
  If you need additional functionality like automatic resizing, sorting, and easier element manipulation, `ArrayList` provides convenient methods.

- **Non-primitive Elements**:  
  If you're storing non-primitive types (like objects), `ArrayList` offers a flexible way to store and manage them.

- **Frequent Insertions/Deletions at the End**:  
  Insertion and deletion at the end of the `ArrayList` are faster (amortized O(1) time complexity), making it suitable for situations like dynamic list management.

### Example:
```java
ArrayList<String> fruits = new ArrayList<>();
fruits.add("Apple");  // Dynamic size
fruits.add("Banana");
```
