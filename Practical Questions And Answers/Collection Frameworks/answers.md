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
public class Main {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Banana");
        fruits.add("Apple");
        fruits.add("Mango");
        fruits.add("Grapes");

        Collections.sort(fruits); // Ascending order (A-Z)

        System.out.println("Sorted List: " + fruits);
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

```java
class Main {
   public static int binarySearch(ArrayList<Integer> list, int target) {
        int high = list.size() - 1, low = 0;

        while (low <= high) {
            int mid = (high + low) / 2;

            if (list.get(mid) == target) {
                return target;
            } else if (target > list.get(mid)) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10);
        list.add(25);
        list.add(45);
        list.add(67);
        list.add(78);
        list.add(1000);

        int target = 25;

        int result = binarySearch(list, target);

        System.out.println(result == -1 ? target + " Not Found!" : target + " Founded!");
    }
}
```

### 26. Find the index of a specific element in an ArrayList.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        list.add("c");
        list.add("c++");
        list.add("java");
        list.add("python");

        System.out.println(list.indexOf("c++"));

    }
}
```

### 27. Find max and min elements from an ArrayList.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

        list.add(14);
        list.add(12);
        list.add(55);
        list.add(4);
        list.add(99);
        list.add(45);

        int max = 0, min = Integer.MAX_VALUE;

        for(int n : list) {
            if(n > max) max = n;
            if(n < min) min = n;
        }

        System.out.println("Max Number: " + max + "\n Min Number: " + min);
    }
}
```

### 28. Use Collections.frequency to count occurrences of an element.   
```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

        list.add(14);
        list.add(12);
        list.add(55);
        list.add(12);
        list.add(4);
        list.add(99);
        list.add(14);
        list.add(12);

        System.out.println(Collections.frequency(list, 12));
    }
}
```

### 29. Shuffle elements of an ArrayList randomly.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        list.add("c");
        list.add("c++");
        list.add("java");
        list.add("python");

        System.out.println(list); // original order

        Collections.shuffle(list);
        System.out.println(list); // shuffled
    }
}
```

### 30. Reverse an ArrayList.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40);
        list.add(50);

        int start = 0, end = list.size() - 1, temp;

        for(int i = 0; i < list.size() / 2; i++) {
            temp = list.get(start);

            list.set(start, list.get(end));
            list.set(end, temp);

            start++;
            end--;
        }

        System.out.println(list);
    }
}
```

### 31. Create a subList from an ArrayList.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");
        fruits.add("Grapes");
        fruits.add("Orange");

        List<String> subList = fruits.subList(1,3);

        System.out.println(subList);
    }
}
```

### 32. Modify elements in an ArrayList using ListIterator.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");
        fruits.add("Grapes");
        fruits.add("Orange");

        ListIterator<String> iterator = fruits.listIterator();

        while(iterator.hasNext()) {
            String fruit = iterator.next();
            iterator.set(fruit.toUpperCase());
        }

        System.out.println("Modified List: " + fruits);
    }
}
```

### 33. Replace all elements in an ArrayList using Collections.fill.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");

        Collections.fill(fruits, "Fruit");

        System.out.println(fruits);
    }
}
```

### 34. Remove elements that match a condition using removeIf().
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");
        fruits.add("Grapes");
        fruits.add("Orange");

        fruits.removeIf(f -> f.equals("Mango"));

        System.out.println(fruits);
    }
}
```

### 35. Flatten a list of ArrayLists using flatMap (Stream API).
```java
class Main {
    public static void main(String[] args) {
        List<List<String>> nestedList = Arrays.asList(
                Arrays.asList("Banana", "Mango"),
                Arrays.asList("Orange", "Grapes"),
                Arrays.asList("Pineapple"));

        List<String> flatList = nestedList.stream().flatMap(list -> list.stream()).toList();

        System.out.println(flatList);
     }
}
```

### 36. Use forEach() to print all elements.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40);
        list.add(50);

        list.forEach(elem -> System.out.println(elem));
     }
}
```

### 37. Filter null values from an ArrayList using Stream.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

        list.add(null);
        list.add(10);
        list.add(20);
        list.add(30);
        list.add(null);
        list.add(40);
        list.add(50);

        List<Integer> collect = list.stream().filter(e -> e == null).collect(Collectors.toList());

        System.out.println(collect);
    }
}
```

### 38. Convert an ArrayList of strings to uppercase using Stream.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        list.add("Java");
        list.add("C++");
        list.add("Python");

        List<String> collect = list.stream().map(e -> e.toUpperCase()).collect(Collectors.toList());


        System.out.println(collect);
    }
}
```

### 39. Remove whitespaces from all strings in an ArrayList.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        list.add(" Java " );
        list.add("C++ ");
        list.add("Python ");

        List<String> collect = list.stream().map(e -> e.trim()).collect(Collectors.toList());

        System.out.println(collect);
    }
}
```

### 40. Capitalize first letter of all strings in an ArrayList.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        list.add("java");
        list.add("c++ ");
        list.add("python ");

        List<String> collect = list.stream()
                .map(e -> e.substring(0, 1).toUpperCase() + e.substring(1)).collect(Collectors.toList());

        System.out.println(collect);
    }
}
```

### 41. Create an ArrayList of custom objects (e.g., Student class).
```java
class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Main {
    public static void main(String[] args) {
        ArrayList<Student> studentsList = new ArrayList<>();

        studentsList.add(new Student("Armaan Ali", 17));
        studentsList.add(new Student("Farmaan Ali", 18));

        System.out.println(studentsList);
    }
}
```

### 42. Sort ArrayList of custom objects by name.
