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
