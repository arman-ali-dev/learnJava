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
```java
class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

class Main {
    public static void main(String[] args) {
        ArrayList<Student> studentsList = new ArrayList<>();

        studentsList.add(new Student("Armaan Ali", 17));
        studentsList.add(new Student("Ali", 17));
        studentsList.add(new Student("Farmaan Ali", 18));
        studentsList.add(new Student("MD. Jagir", 17));

        studentsList.sort(Comparator.comparing(s -> s.getName()));
        
        studentsList.forEach(e -> System.out.println(e.getName()));
    }
}
```

### 43. Sort ArrayList of custom objects by multiple fields (e.g., age, name).
```java
class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

class Main {
    public static void main(String[] args) {
        ArrayList<Student> studentsList = new ArrayList<>();

        studentsList.add(new Student("Armaan Ali", 17));
        studentsList.add(new Student("Ali", 16));
        studentsList.add(new Student("Farmaan Ali", 18));
        studentsList.add(new Student("MD. Jagir", 15));

        studentsList.sort(Comparator
                .comparing(Student::getAge)
                .thenComparing(Student::getName)
        );

        studentsList.forEach(e -> System.out.println(e.getName()));
    }
}
```

### 44. Group custom objects based on a field using Map.
```java
class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

class Main {
    public static void main(String[] args) {
        ArrayList<Student> studentsList = new ArrayList<>();

        studentsList.add(new Student("Armaan Ali", 17));
        studentsList.add(new Student("Ali", 16));
        studentsList.add(new Student("Farmaan Ali", 18));
        studentsList.add(new Student("MD. Jagir", 15));

        Map<Integer, List<Student>> groupByAge = studentsList.stream()
                                                .collect(Collectors.groupingBy(Student::getAge));

        groupByAge.forEach((age, students) -> {
            System.out.print(age + "  -> ");
            students.forEach(s -> System.out.print(s.getName()));
            System.out.println();
        });
    }
}
```

### 45. Remove objects from ArrayList based on a field value.
```java
class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

class Main {
    public static void main(String[] args) {
        ArrayList<Student> studentsList = new ArrayList<>();

        studentsList.add(new Student("Armaan Ali", 17));
        studentsList.add(new Student("Ali", 16));
        studentsList.add(new Student("Farmaan Ali", 16));
        studentsList.add(new Student("MD. Jagir", 15));

        studentsList.removeIf(s -> s.getAge() == 16);

        studentsList.forEach(s -> System.out.println(s.getName()));
    }
}class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

class Main {
    public static void main(String[] args) {
        ArrayList<Student> studentsList = new ArrayList<>();

        studentsList.add(new Student("Armaan Ali", 17));
        studentsList.add(new Student("Ali", 16));
        studentsList.add(new Student("Farmaan Ali", 16));
        studentsList.add(new Student("MD. Jagir", 15));

        studentsList.removeIf(s -> s.getAge() == 16);

        studentsList.forEach(s -> System.out.println(s.getName()));
    }
}
```

### 46. Count frequency of each word from an ArrayList of strings.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("One");
        list.add("Two");
        list.add("One");
        list.add("Three");

        list.forEach(e -> System.out.println(e + " -> " + Collections.frequency(list, e)));
    }
}
```

### 47. Convert ArrayList to comma-separated string.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("One");
        list.add("Two");
        list.add("One");
        list.add("Three");

        String result = list.stream().collect(Collectors.joining(", "));

        System.out.println(result);
    }
}
```

### 48. Partition an ArrayList into sublists of size N.
```java
class Main {
    public static void main(String[] args) {
        List<Integer> originalList = Arrays.asList(1,2,3,4,5,6,7);
        int N = 3;

        List<List<Integer>> partitions = new ArrayList<>();

        for(int i = 0; i < originalList.size(); i += N) {
          partitions.add(
                  originalList.subList(
                          i, Math.min(i + N, originalList.size())
                  )
          );
        }

        System.out.println(partitions);
    }
}
```

### 49. Check if an ArrayList has any null or empty string.
```java
class Main {
    public static void main(String[] args) {
        List<String> list = Arrays.asList("Hello", "", "How", "Are", "You");

        if(list.contains(null) || list.contains("")){
            System.out.println("Yes Null OR Empty String Is Exists In List!");
        }
    }
}
```

### 50. Convert ArrayList of strings to ArrayList of integers.
```java
class Main {
    public static void main(String[] args) {
        ArrayList<String> strList  = new ArrayList<>();
        strList.add("10");
        strList.add("20");
        strList.add("30");

        List<Integer> integerList = strList.stream().map(Integer::parseInt).collect(Collectors.toList());

        System.out.println(integerList);
    }
}
```

# 🔹 LinkedList

### 1. Create a LinkedList of strings and add four names.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println(names);
    }
}
```

### 2. Add an element at the first and last position in a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("filiya");
        names.add("chintu");

        names.addFirst("liliya");
        names.addLast("candy");

        System.out.println(names);
    }
}
```

### 3. Iterate through a LinkedList using for-each loop.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("filiya");
        names.add("chintu");

        names.addFirst("liliya");
        names.addLast("candy");


        names.forEach(System.out::println);
    }
}
```

### 4. Iterate through a LinkedList using Iterator.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("filiya");
        names.add("chintu");

        names.addFirst("liliya");
        names.addLast("candy");

        Iterator<String> iterator = names.iterator();

        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

### 5. Iterate through a LinkedList using ListIterator.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("filiya");
        names.add("chintu");

        names.addFirst("liliya");
        names.addLast("candy");

        ListIterator<String> iterator = names.listIterator();

        while(iterator.hasNext()){
            System.out.println(iterator.next());
        }
    }
}
```

### 6. Access the first and last element of a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println("First Element: " + names.getFirst());
        System.out.println("Last Element: " + names.getLast());
    }
}
```

### 7. Remove the first and last element of a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        names.removeFirst();
        names.removeLast();

        System.out.println(names);
    }
}
```

### 8. Get the element at a specific index.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println(names.get(3));
    }
}
```

### 9. Replace an element at a specific index.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        names.set(2, "pintu");

        System.out.println(names);
    }
}
```

### 10. Check if a LinkedList contains a specific element.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");


        System.out.println(names.contains("chintu"));
    }
}
```

### 11. Find the index of a given element.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println(names.indexOf("chintu"));
    }
}
```

### 12. Remove an element by value.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        names.remove("chintu");
        System.out.println(names);
    }
}
```

### 13. Remove an element by index.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        names.remove(2);
        System.out.println(names);
    }
}
```

### 14. Clear all elements from a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        names.clear();
        System.out.println(names);
    }
}
```

### 15. Check if a LinkedList is empty.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        System.out.println(names.isEmpty());
    }
}
```

### 16. Find the size of a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println(names.size());
    }
}
```

### 17. Convert a LinkedList to an array.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        String[] nameArr = names.toArray(new String[0]);

        for (String s : nameArr) {
            System.out.println(s);
        }
    }
}
```

### 18. Convert an array to a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        int[] arr = {1,2,3,4};

        LinkedList<Integer> linkedList = new LinkedList<>();

        for (int n : arr) {
            linkedList.add(n);
        }

        System.out.println(linkedList);
    }
}
```

### 19. Sort a LinkedList of strings alphabetically.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        Collections.sort(names);

        System.out.println(names);
    }
}
```

### 20. Reverse a LinkedList manually.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        int start = 0, end = names.size() - 1;
        String temp;

        for(int i = 0; i < names.size() / 2; i++) {
            temp = names.get(start);
            names.set(start, names.get(end));
            names.set(end, temp);

            start++;
            end--;
        }

        System.out.println(names);
    }
}
```

### 21. Reverse a LinkedList using Collections.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        Collections.reverse(names);

        System.out.println(names);
    }
}
```

### 22. Shuffle a LinkedList randomly.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> names = new LinkedList<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        Collections.shuffle(names);

        System.out.println(names);
    }
}
```

### 23. Merge two LinkedLists.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> linkedList1 = new LinkedList<>();
        linkedList1.add(1);
        linkedList1.add(2);
        linkedList1.add(3);

        LinkedList<Integer> linkedList2 = new LinkedList<>();
        linkedList2.add(4);
        linkedList2.add(5);
        linkedList2.add(6);

        linkedList1.addAll(linkedList2);

        System.out.println(linkedList1);
    }
}
```

### 24. Clone a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> linkedList1 = new LinkedList<>();
        linkedList1.add(1);
        linkedList1.add(2);
        linkedList1.add(3);

        LinkedList<Integer> cloned = (LinkedList<Integer>) linkedList1.clone();
    }
}
```

### 25. Compare two LinkedLists for equality.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> linkedList1 = new LinkedList<>();
        linkedList1.add(1);
        linkedList1.add(2);
        linkedList1.add(3);

        LinkedList<Integer> linkedList2 = new LinkedList<>();
        linkedList2.add(1);
        linkedList2.add(3);
        linkedList2.add(2);

        System.out.println(linkedList1.equals(linkedList2));
    }
}
```

### 26. Check if one LinkedList contains all elements of another.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> linkedList1 = new LinkedList<>();
        linkedList1.add(1);
        linkedList1.add(2);
        linkedList1.add(3);
        linkedList1.add(4);

        LinkedList<Integer> linkedList2 = new LinkedList<>();
        linkedList2.add(1);
        linkedList2.add(3);
        linkedList2.add(2);

        System.out.println(linkedList1.containsAll(linkedList2));
    }
}
```

### 27. Retain common elements between two LinkedLists.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> linkedList1 = new LinkedList<>();
        linkedList1.add(1);
        linkedList1.add(2);
        linkedList1.add(3);
        linkedList1.add(4);

        LinkedList<Integer> linkedList2 = new LinkedList<>();
        linkedList2.add(1);
        linkedList2.add(3);
        linkedList2.add(2);

        linkedList1.retainAll(linkedList2);

        System.out.println(linkedList1);
    }
}
```

### 28. Remove all elements from one LinkedList that exist in another.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> linkedList1 = new LinkedList<>();
        linkedList1.add(1);
        linkedList1.add(2);
        linkedList1.add(3);
        linkedList1.add(4);

        LinkedList<Integer> linkedList2 = new LinkedList<>();
        linkedList2.add(1);
        linkedList2.add(3);
        linkedList2.add(2);

        linkedList1.removeAll(linkedList2);

        System.out.println(linkedList1);
    }
}
```

### 29. Convert a LinkedList to a Set.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> linkedList1 = new LinkedList<>();
        linkedList1.add(1);
        linkedList1.add(2);
        linkedList1.add(3);
        linkedList1.add(4);
        linkedList1.add(3);

        Set<Integer> set = new HashSet<>(linkedList1);

        System.out.println(set);
    }
}
```

### 30. Add null values and observe behavior.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(null);
        list.add(null);
        list.add(null);

        System.out.println(list);
    }
}
```

### 31. Create a LinkedList of integers and remove even numbers.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

        list.removeIf(n -> n % 2 == 0);
        System.out.println(list);
    }
}
```

### 32. Add elements at a specific index.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

        list.set(1, 20);
        System.out.println(list);
    }
}
```

### 33. Create a synchronized LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

        List<Integer> synchronizedList = Collections.synchronizedList(list);

    }
}
```

### 34. Create an unmodifiable LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(1);
        list.add(2);
        list.add(3);

        List<Integer> unmodifiableList  = Collections.unmodifiableList(list);

       // list.add(4); give an unsupportedOperationException

        System.out.println(unmodifiableList);
    }
}
```

### 35. Traverse a LinkedList backward using descendingIterator.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(1);
        list.add(2);
        list.add(3);

        Iterator<Integer> reverseIterator = list.descendingIterator();

        while (reverseIterator.hasNext()) {
            System.out.println(reverseIterator.next());
        }
    }
}
```

### 36. Use LinkedList as a Queue (FIFO behavior).
```java
class Main {
    public static void main(String[] args) {
        Deque<String> list = new LinkedList<>();
        list.add("First");
        list.add("Second");
        list.add("Third");

        list.remove(); // remove first element

        System.out.println(list);
    }
}
```

### 37. Use LinkedList as a Stack (LIFO behavior).
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> stack = new LinkedList<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        
        stack.remove() ; // LIFO (Last In First Out) Behavior

        System.out.println(stack);
    }
}
```

### 38. Demonstrate peek(), poll(), and offer() methods.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();

        // offer() - adds elements to the end of the LinkedList
        list.offer(1);
        list.offer(2);
        list.offer(3);

        // peek() - return head element of LinkedList
        System.out.println(list.peek());

        // poll() - removes and returns the head of the LinkedList
        System.out.println(list.poll());
        System.out.println(list);
    }
}
```

### 39. Use LinkedList to store custom objects.
```java
class Student {
    private int age;
    private String name;

    public Student(int age, String name) {
        this.age = age;
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}

class Main {
    public static void main(String[] args) {
        LinkedList<Student> students = new LinkedList<>();

        students.add(new Student(17, "Armaan Ali"));
        students.add(new Student(18, "Farman Khan"));
    }
}
```

### 40. Sort LinkedList of custom objects using Comparator.
```java
class Student {
    private int age;
    private String name;

    public Student(int age, String name) {
        this.age = age;
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}

class Main {
    public static void main(String[] args) {
        LinkedList<Student> students = new LinkedList<>();

        students.add(new Student(17, "Armaan Ali"));
        students.add(new Student(18, "Farman Khan"));
        students.add(new Student(18, "Ali"));

        Collections.sort(students, Comparator.comparing(Student::getName));

        students.forEach(s -> System.out.println(s.getName()));
    }
}
```

### 41. Iterate and remove elements using removeIf().
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();

        list.add("c");
        list.add("c++");
        list.add("java");
        list.add("javaScript");
        list.add("python");

        list.removeIf(elem -> elem.equals("python"));

        System.out.println(list);
    }
}
```

### 42. Create a sublist from a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();

        list.add("c");
        list.add("c++");
        list.add("java");
        list.add("javaScript");
        list.add("python");

        List<String> subList = list.subList(1, 4);

        System.out.println(subList);
    }
}
```

### 43. Use listIterator to modify elements.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();

        list.add("c");
        list.add("c++");
        list.add("java");
        list.add("javaScript");
        list.add("python");

        ListIterator iterator  = list.listIterator();

        while (iterator.hasNext()) {
            iterator.set(iterator.next().toString().toUpperCase());
        }

        System.out.println(list); // Modified List
    }
}
```

### 44. Count frequency of elements using Collections.frequency().
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();

        list.add("c");
        list.add("c++");
        list.add("java");
        list.add("c");
        list.add("python");

        System.out.println(Collections.frequency(list,"c"));
    }
}
```

### 45. Find max and min in a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();

        list.add(12);
        list.add(34);
        list.add(2);
        list.add(45);
        list.add(95);
        list.add(92);

        int max = 0, min = Integer.MAX_VALUE;

        for (Integer num : list) {
            if(num > max) max = num;
            if (num < min) min = num;
        }

        System.out.println("Max Number: " + max);
        System.out.println("Min Number: " + min);
    }
}
```

### 46. Add elements from another collection.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<Integer> list1 = new LinkedList<>();

        list1.add(1);
        list1.add(2);
        list1.add(3);

        LinkedList<Integer> list2 = new LinkedList<>();

        list2.add(4);
        list2.add(5);
        list2.add(6);

        list1.addAll(list2);

        System.out.println(list1);
    }
}
```

### 47. Convert LinkedList to comma-separated string.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        list.add("C");
        list.add("Java");
        list.add("JavaScript");

        String result = list.stream().collect(Collectors.joining(", "));

        System.out.println(result);
    }
}
```


### 48. Capitalize first letter of each string in a LinkedList.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        list.add("hello");
        list.add("world");
        list.add("how");
        list.add("are");
        list.add("you");

        ListIterator<String> iterator = list.listIterator();

        while(iterator.hasNext()) {
            String current = iterator.next();
            String capitalizeStr = current.substring(0, 1).toUpperCase() +
                    current.substring(1);

            iterator.set(capitalizeStr);
        }

        System.out.println(list);
    }
}
```

### 49. Filter out null or empty strings.
```java
class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        list.add("hello");
        list.add("world");
        list.add("");
        list.add("how");
        list.add("are");
        list.add(null);
        list.add("you");

        List<String> collect = list.stream().filter(s -> s != null && !s.isBlank() ).collect(Collectors.toList());

        System.out.println(collect);
    }
}
```

### 50. Count vowels in each string of a LinkedList.
```java
import java.util.LinkedList;

class Main {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        list.add("hello");
        list.add("world");
        list.add("how");
        list.add("are");
        list.add("yoU");

        int vowelCount = 0;

        for (String s : list) {
            for (int i = 0; i < s.length(); i++) {
                char ch = s.charAt(i);
                if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ||
                    ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U') {
                    vowelCount++;
                }
            }
        }

        System.out.println("Total Vowels In Each String Of List: " + vowelCount);
    }
}
```

# 🔹 Vector

### 1. Create a Vector of integers and add five elements to it.
```java
class Main {
    public static void main(String[] args) {
        Vector<Integer> vector = new Vector<>();

        vector.add(1);
        vector.add(2);
        vector.add(3);
        vector.add(4);
        vector.add(5);

        System.out.println(vector);
    }
}
```

### 2. Create a Vector of Strings and add 3 names.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        System.out.println(names);
    }
}
```

### 3. Insert an element at a specific index in a Vector.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        names.set(1, "Arman Ali");

        System.out.println(names);
    }
}
```

### 4. Retrieve an element from a Vector using index.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        System.out.println(names.get(1));
    }
}
```

### 5. Get the size of a Vector.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        System.out.println(names.size());
    }
}
```

### 6. Remove an element from a Vector by index.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        names.remove(1);
        
        System.out.println(names);
    }
}
```

### 7. Remove an element by value from a Vector.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        names.remove("Armaan");

        System.out.println(names);
    }
}
```

### 8. Replace an element at a given index in a Vector.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        names.set(1, "Arman Ali");

        System.out.println(names);
    }
}
```

### 9. Check if a Vector contains a specific value.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        System.out.println(names.contains("Ali"));
    }
}
```

### 10. Clear all elements from a Vector.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        names.clear();
        
        System.out.println(names);
    }
}
```


### 11. Iterate over a Vector using a for-each loop.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        names.forEach(System.out::println);
    }
}
```

### 12. Iterate over a Vector using traditional for loop.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        for (int i = 0; i < names.size(); i++) {
            System.out.println("Element at index " + i + ": " + names.get(i));
        }
    }
}
```

### 13. Iterate using Iterator.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        Iterator<String> iterator = names.iterator();

        while (iterator.hasNext()){
            System.out.println(iterator.next());
        }
    }
}
```

### 14. Iterate using ListIterator (forward and backward).
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("Ali");
        names.add("Armaan");
        names.add("Maan");

        ListIterator<String> iterator = names.listIterator();

        System.out.println("Forward Iteration:");
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }

        System.out.println("\nBackward Iteration:");
        while (iterator.hasPrevious()){
            System.out.println(iterator.previous());
        }
    }
}
```

### 15. Find the index of a specific element.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println(names.indexOf("chintu"));
    }
}
```

### 16. Check if a Vector is empty.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println(names.isEmpty());

        names.clear();
        System.out.println(names.isEmpty());
    }
}
```

### 17. Get the first and last element of the Vector.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        System.out.println(names.getFirst());
        System.out.println(names.getLast());
    }
}
```

### 18. Convert a Vector to an Array.
```java
class Main {
    public static void main(String[] args) {
        Vector<String> names = new Vector<>();

        names.add("liliya");
        names.add("filiya");
        names.add("chintu");
        names.add("candy");

        String[] arr = names.toArray(new String[0]);

        for (String s : arr) {
            System.out.println(s);
        }
    }
}
```

### 19. Convert an Array to a Vector.
```java
class Main {
    public static void main(String[] args) {
        String[] nameArray = {"liliya", "filiya", "chintu", "candy"};

        Vector<String> nameVector = new Vector<>(Arrays.asList(nameArray));

        System.out.println(nameVector);
    }
}
```

### 20. Clone a Vector to another Vector.
```java
class Main {
    public static void main(String[] args) {
       Vector<String> vector = new Vector<>();
       vector.add("Hello");
       vector.add("World");

       Vector<String> cloned = (Vector<String>) vector.clone();

        System.out.println(cloned);
    }
}
```

### 21. Sort a Vector of Strings alphabetically.
```java
class Main {
    public static void main(String[] args) {
       Vector<String> vector = new Vector<>();
       vector.add("x");
       vector.add("a");
       vector.add("h");
       vector.add("k");
       vector.add("o");

        Collections.sort(vector);

       System.out.println(vector);
    }
}
```

### 22. Reverse a Vector of Integers.
```java
class Main {
    public static void main(String[] args) {
       Vector<Integer> vector = new Vector<>(Arrays.asList(1,2,3,4,5));

       System.out.println(vector.reversed());
    }
}
```

### 23. Shuffle a Vector of Strings randomly.
```java
class Main {
    public static void main(String[] args) {
       Vector<String> vector = new Vector<>(Arrays.asList("Hello", "World", "How", "Are", "You"));

       Collections.shuffle(vector);
        System.out.println(vector);
    }
}
```

### 24. Copy elements from one Vector to another.
```java
class Main {
    public static void main(String[] args) {
       Vector<String> vector1 = new Vector<>(Arrays.asList("Hello", "World", "How", "Are", "You"));

       Vector<String > vector2 = new Vector<>(vector1);

       System.out.println(vector2);
    }
}
```

### 25. Find the maximum and minimum from a Vector of Integers.
```java
class Main {
    public static void main(String[] args) {
       Vector<Integer> vector = new Vector<>(Arrays.asList( 45, 86, 77, 2, 65, 10 ));

       int max = 0, min = Integer.MAX_VALUE;

        for (Integer num : vector) {
            if(num > max) max = num;
            if(num < min) min = num;
        }

        System.out.println("Max Number: " + max);
        System.out.println("Min Number: " + min);
    }
}
```
