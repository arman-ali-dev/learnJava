# Java Collections Framework - 300 Coding Questions (Beginner Friendly)

# 🔹 ArrayList

### 1. Create an ArrayList of integers and add five numbers to it.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        System.out.println(nums);
    }
}
```

### 2. Remove an element from an ArrayList by index and by value.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        nums.remove(Integer.valueOf(4)); // remove element by value
        nums.remove(1); // remove element by index

        System.out.println(nums);
    }
}
```

### 3. Get an element at a specific index from an ArrayList.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        System.out.println(nums.get(1));
    }
}
```

### 4. Replace an element at a specific index in an ArrayList.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        nums.set(1, 20);

        System.out.println(nums);
    }
}
```

### 5. Find the size of an ArrayList.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        System.out.println(nums.size());
    }
}
```

### 6. Check if an ArrayList is empty.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        System.out.println(nums.isEmpty());
    }
}
```

### 7. Clear all elements from an ArrayList.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        nums.clear();
        System.out.println(nums);
    }
}
```

### 8. Check if an ArrayList contains a specific element.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        System.out.println(nums.contains(30)); // false
        System.out.println(nums.contains(3)); // true
    }
}
```

### 9. Iterate over an ArrayList using a for-each loop.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        for(int n : nums) {
            System.out.println(n);
        }
    }
}
```

### 10. Iterate over an ArrayList using for loop and while loop.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        for(int i = 0; i < nums.size(); i++) {
            System.out.println(nums.get(i));
        }

        int i = 0;
        while(i < nums.size()) {
            System.out.println(nums.get(i));
            i++;
        }

    }
}
```

### 11. Convert an ArrayList to an array.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(1);
        nums.add(2);
        nums.add(3);
        nums.add(4);
        nums.add(5);

        Integer[] array = nums.toArray(new Integer[0]);

        for(int n : array) {
            System.out.println(n);
        }
    }
}
```

### 12. Convert an array to an ArrayList.

```java
class Main {
    public static void main(String[] args) {
       Integer[] array = {1,2,3,4,5};

       ArrayList<Integer> list = new ArrayList<>(Arrays.asList(array));

        System.out.println(list);
    }
}
```

### 13. Clone an ArrayList.

```java

class Main {
    public static void main(String[] args) {
       ArrayList<String> strList = new ArrayList<>();

       strList.add("Java");
       strList.add("C++");
       strList.add("Python");

     //  ArrayList<String> copy = new ArrayList<>(strList); // first way

        ArrayList<String> copy = (ArrayList<String>) strList.clone(); // second way
    }
}
```

### 14. Compare two ArrayLists for equality.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("Hello");
        list1.add("World");


        ArrayList<String> list2 = new ArrayList<>();
        list2.add("Hello");
        list2.add("World");


        System.out.println(list1.equals(list2));
        // Elements same hone chahiye
        // Order bhi same hona chahiye
    }
}
```

### 15. Check if one ArrayList contains all elements of another.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("Hello");
        list1.add("World");


        ArrayList<String> list2 = new ArrayList<>();
        list2.add("Hello");
        list2.add("World");


        System.out.println(list1.containsAll(list2));

        list2.add("!");

        System.out.println(list1.containsAll(list2));
    }
}
```

### 16. Copy contents of one ArrayList to another.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("Hello");
        list1.add("World");


        ArrayList<String> list2 = new ArrayList<>(list1);

        System.out.println(list2);
    }
}
```

### 17. Remove all elements from one ArrayList that exist in another.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("One");
        list1.add("Two");
        list1.add("Three");
        list1.add("Four");

        ArrayList<String> list2 = new ArrayList<>();
        list2.add("Three");
        list2.add("One");

        list1.removeAll(list2);

        System.out.println(list1);
    }
}
```

### 18. Retain only common elements between two ArrayLists.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("One");
        list1.add("Two");
        list1.add("Three");
        list1.add("Four");

        ArrayList<String> list2 = new ArrayList<>();
        list2.add("Three");
        list2.add("One");
        list2.add("Five");

        list1.retainAll(list2);

        System.out.println(list1);
    }
}
```

### 19. Remove duplicates from an ArrayList using Set.

```java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.Set;

class Main {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("One");
        list1.add("Two");
        list1.add("Three");
        list1.add("One");
        list1.add("Four");

        Set<String> set = new HashSet<>(list1);

        ArrayList<String> list = new ArrayList<>(set);
        System.out.println(list);
        }
}
```

### 20. Convert a Set to an ArrayList.

```java
class Main {
    public static void main(String[] args) {
        Set<String> set = new HashSet<>();

        set.add("Java");
        set.add("C++");
        set.add("Java");
        set.add("C");

       ArrayList<String> list = new ArrayList<>(set);

        System.out.println(list); // we can use sort() method also
    }
}
```

### 21. Sort an ArrayList of integers.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(125);
        list.add(55);
        list.add(23);
        list.add(155);
        list.add(40);
        list.add(30);
        list.add(50);
        list.add(200);

        int pos = 0, temp;

        for(int i = 0; i < list.size() - 1; i++ ) {
            int min = list.get(i);

            for(int j = i; j < list.size(); j++) {
                if(list.get(j) < min) {
                    pos = j;
                    min = list.get(j);
                }
            }

                temp = list.get(i);
                list.set(i, min);
                list.set(pos, temp);
        }

        System.out.println(list);
    }
}
```

### 22. Sort an ArrayList of strings alphabetically.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("java");
        list.add("python");
        list.add("c");
        list.add("c++");

        int pos = 0;
        String temp;

        for(int i = 0; i < list.size() ; i++) {
            for(int j = 0; j < list.size() - 1; j++) {
                if(list.get(j).length() > list.get(j + 1).length()) {
                    temp = list.get(j);
                    list.set(j, list.get(j + 1));
                    list.set((j + 1), temp);
                }
            }
        }

        System.out.println(list);
    }
}
```

### 23. Sort an ArrayList in descending order.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(125);
        list.add(55);
        list.add(23);
        list.add(155);
        list.add(40);
        list.add(30);
        list.add(50);
        list.add(200);

        int pos = 0, temp;

        for(int i = 0; i < list.size() - 1; i++ ) {
            int max = list.get(i);

            for(int j = i; j < list.size(); j++) {
                if(list.get(j) > max) {
                    pos = j;
                    max = list.get(j);
                }
            }

            temp = list.get(i);
            list.set(i, max);
            list.set(pos, temp);
        }

        System.out.println(list);
    }
}
```

### 24. Sort strings by length using Comparator.

```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("java");
        list.add("python");
        list.add("c");
        list.add("c++");

        list.sort(=(a,b) -> a.length() - b.length());

        System.out.println(list);
    }
}
```

### 25. Search for an element in a sorted ArrayList using binary search.
