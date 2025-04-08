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

