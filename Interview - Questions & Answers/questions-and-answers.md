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
