# Java Collections Framework 

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

### 26. Create a synchronized version of a Vector.
```java
// Here, Vector is already synchronized internally, so it's thread-safe for most simple use cases.

public class Main {
    public static void main(String[] args) {
        Vector<String> vector = new Vector<>();
        vector.add("Apple");
        vector.add("Banana");

        System.out.println(vector);
    }
}
```

### 27. Convert a Vector to ArrayList.
```java
class Main {
    public static void main(String[] args) {
       Vector<Integer> vector = new Vector<>(Arrays.asList( 45, 86, 77, 2, 65, 10 ));

       ArrayList<Integer> list = new ArrayList<>(vector);

        System.out.println(list);
    }
}
```

### 28. Use Collections.frequency() with Vector.
```java
class Main {
    public static void main(String[] args) {
       Vector<Integer> vector = new Vector<>(Arrays.asList( 45, 86, 77, 2, 65, 77, 10 ));

        System.out.println(Collections.frequency(vector,77));
    }
}
```

### 29. Count occurrences of a word in a Vector.
```java
class Main {
    public static void main(String[] args) {
       Vector<String> vector = new Vector<>(Arrays.asList( "Hello", "World", "Hello", "Java"  ));

        for (String s : vector) {
            System.out.println(s + " -> " + Collections.frequency(vector, s));
        }
    }
}
```

### 30. Filter elements starting with a specific letter from Vector.
```java
class Main {
    public static void main(String[] args) {
       Vector<String> vector = new Vector<>(Arrays.asList( "Hello", "World", "How", "Are", "You"));

        List<String> filteredVector = vector.stream().filter(s -> s.startsWith("H")).collect(Collectors.toList());

        System.out.println(filteredVector);
    }
}
```

### 31. Remove all even numbers from a Vector.
```java
class Main {
    public static void main(String[] args) {
       Vector<Integer> vector = new Vector<>(Arrays.asList(1,2,3,4,5,6));
       vector.removeIf(elem -> elem % 2 == 0);

        System.out.println(vector);
    }
}
```

### 32. Remove duplicates using Set.
```java
class Main {
    public static void main(String[] args) {
       Vector<Integer> vector = new Vector<>(Arrays.asList(1,2,3,1,5,2));

       Set<Integer> set = new HashSet<>(vector);

       Vector<Integer> newVector = new Vector<>(set);

        System.out.println(newVector);
    }
}
```

### 33. Convert Vector to Stream and filter values.    
```java
class Main {
    public static void main(String[] args) {
       Vector<Integer> vector = new Vector<>(Arrays.asList(1,2,3,1,5,2));

        Stream<Integer> integerStream = vector.stream().filter(e -> e % 2 == 0);
    }
}
```

### 34. Use Vector to store custom objects.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Main {
    public static void main(String[] args) {
        Vector<Person> personVector = new Vector<>();
        personVector.add(new Person("Armaan Ali", 18));
        personVector.add(new Person("Ali", 17));
    }
}
```

### 35. Sort a Vector of custom objects using Comparator.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
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
        Vector<Person> personVector = new Vector<>();
        personVector.add(new Person("Armaan Ali", 18));
        personVector.add(new Person("Ali", 17));

        personVector.sort(Comparator.comparing(Person::getName));

        for (Person person : personVector) {
            System.out.println(person.getName());
        }
    }
}
```

### 36. Explain how Vector is synchronized.

#### What is Synchronization?
**Synchronization** in Java means that only one thread can access a method or block of code at a time. This helps prevent:

- Data corruption
- Race conditions
- Inconsistent results in multithreaded environments

#### How is `Vector` Synchronized?

The `Vector` class in Java is **synchronized by default**. This means:
- All major methods like `add()`, `remove()`, `get()`, `set()` etc. are synchronized.
- Internally, `Vector` uses the `synchronized` keyword to ensure thread-safe access.

### 37. Difference between Vector and ArrayList.

## 1. Synchronization
- **`Vector`**: It is **synchronized** by default, meaning it is thread-safe. Multiple threads can safely access a `Vector` without causing data inconsistencies.
- **`ArrayList`**: It is **not synchronized** by default. This makes it **faster** in single-threaded environments, but you need to manually synchronize it if required.

## 2. Growth Policy
- **`Vector`**: It **doubles its size** when it runs out of space. For example, if a `Vector` with 10 elements reaches its capacity, it increases the capacity to 20 elements.
- **`ArrayList`**: It **grows by 50%** of the current size. For example, if an `ArrayList` with 10 elements exceeds its capacity, it increases the capacity by 5 elements (i.e., 15 total).

## 3. Performance
- **`Vector`**: Due to synchronization and doubling of size, `Vector` is generally **slower** compared to `ArrayList`, especially in single-threaded applications.
- **`ArrayList`**: It is **faster** as it is not synchronized and grows by 50%, making it more efficient in most use cases.

## 4. Methods
- **`Vector`**: It includes some legacy methods such as `elementAt()`, `addElement()`, and `removeElement()`, which are not present in `ArrayList`.
- **`ArrayList`**: It uses modern collection methods, and doesn't include legacy methods that are specific to `Vector`.

## 5. Memory Overhead
- **`Vector`**: The synchronization mechanism introduces additional **memory overhead**.
- **`ArrayList`**: Since it's not synchronized, there is less **memory overhead** compared to `Vector`.

## 6. Default Size
- **`Vector`**: It has a **default capacity** of 10 elements, but it may grow more significantly when the capacity exceeds the current size.
- **`ArrayList`**: It has a **default capacity** of 10 elements, and it increases its capacity by 50% when needed.

## 7. Legacy Status
- **`Vector`**: It is a **legacy class** in Java. It was part of the original version of Java, but it's been largely replaced by other collection classes like `ArrayList`.
- **`ArrayList`**: It is a **modern class** introduced in the Java Collections Framework and is the preferred choice for list operations in most cases.

---

## When to Use Which?

- Use **`Vector`** when:
  - You need thread-safety with **built-in synchronization**.
  - You are working with legacy code that depends on `Vector`.

- Use **`ArrayList`** when:
  - You don’t need synchronization, and you want better **performance**.
  - You are working with modern code and Java Collections Framework.

## 38. Why Vector is slower than ArrayList.

1. **Synchronization**:  
   - `Vector` is synchronized by default, introducing overhead for thread safety.  
   - `ArrayList` is not synchronized, making it faster in single-threaded environments.

2. **Growth Policy**:  
   - `Vector` doubles its size when capacity is exceeded, causing more frequent resizing.  
   - `ArrayList` increases its size by 50%, resulting in fewer resizes.

3. **Legacy Class**:  
   - `Vector` is older and less optimized for modern usage.  
   - `ArrayList` is newer and more efficient for general use.

4. **Thread Safety vs Performance**:  
   - `Vector` sacrifices performance for thread safety.  
   - `ArrayList` is faster without built-in thread safety.

## 39. When should Vector be used in modern Java?
# When Should `Vector` be Used in Modern Java?

`Vector` should be used in modern Java when:

1. **Thread Safety is Required**:  
   - If you need a thread-safe list where multiple threads will be accessing and modifying the list concurrently, and you prefer built-in synchronization.

2. **Legacy System Support**:  
   - When maintaining or interacting with legacy code that already uses `Vector` and changing it might introduce bugs or be costly.

3. **No Better Alternative**:  
   - When using modern alternatives like `ArrayList` or `CopyOnWriteArrayList` is not suitable for the specific requirements of your project.

However, in most cases, `ArrayList` or other concurrency-safe collections like `CopyOnWriteArrayList` are recommended for performance reasons.

## 40. What is capacity and capacity increment in Vector?

## 1. **Capacity**:
- The **capacity** of a `Vector` refers to the number of elements it can hold before needing to resize.
- When a `Vector` is created, it is initialized with a default capacity of 10 elements. However, you can specify an initial capacity when creating a `Vector`.

### Example:
```java
Vector<Integer> vector = new Vector<>(20);  // Initial capacity is 20
```

## 2. Capacity Increment:
 - The capacity increment defines how much the Vector’s capacity increases when it needs to grow.
 - If a Vector’s size exceeds its current capacity, the capacity will increase by a fixed increment (which is specified when the Vector is created).

### Example:
```java
Vector<Integer> vector = new Vector<>(10, 5);  // Initial capacity 10, increment 5
```

# 🔹 Stack

## 1. Create a Stack of integers and push five elements into it.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        System.out.println(stack);
    }
}
```

## 2. Pop an element from the Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        stack.pop();
        
        System.out.println(stack);
    }
}
```

## 3. Peek the top element of the Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        System.out.println(stack.peek());
    }
}
```

## 4. Check if the Stack is empty.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        System.out.println(stack.isEmpty());
    }
}
```

## 5. Find the size of the Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        System.out.println(stack.size());
    }
}
```

## 6. Search an element in the Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        System.out.println(stack.search(10));
    }
}
```

## 7. Use a loop to pop all elements from a Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        while (!stack.isEmpty()) {
            stack.pop();
        }

        System.out.println(stack);
    }
}
```

## 8. Convert Stack to List.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        List<Integer> list = new ArrayList<>(stack);

        System.out.println(list);
    }
}
```

## 9. Clear all elements from the Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        stack.clear();

        System.out.println(stack);
    }
}
```

## 10. Clone a Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        Stack<Integer> cloned  = (Stack<Integer>) stack.clone();

        System.out.println(cloned);
    }
}
```

## 11. Iterate through a Stack using a for-each loop.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        for (Integer n : stack) {
            System.out.println(n);
        }
    }
}
```

## 12. Iterate through a Stack using an Iterator.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        Iterator<Integer> iterator = stack.iterator();

        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

## 13. Reverse print Stack without modifying it.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        ListIterator<Integer> iterator = stack.listIterator(stack.size());

        while (iterator.hasPrevious()) {
            System.out.println(iterator.previous());
        }
    }
}
```

## 14.Print elements from bottom to top of Stack.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        ListIterator<Integer> iterator = stack.listIterator();

        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

## 15. Convert Stack to Array.
```java
class Main {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        stack.push(4);
        stack.push(5);

        Integer[] arr = stack.toArray(new Integer[0]);
    }
}
```

## 16. Check for balanced parentheses using Stack.
```java
class Main {
    public static boolean isBalanced(String str) {
        Stack<Character> stack = new Stack<>();

        for(Character ch : str.toCharArray()) {
            if(ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            }

            else if(ch == ')' || ch == '}' || ch == ']') {
                if(stack.isEmpty()) return false;

                Character top = stack.pop();

                if((ch == ')' && top != '(') ||
                   (ch == '}' && top != '{') ||
                   (ch == ']' && top != '[')) {
                    return  false;
                }
            }
        }

        return  stack.isEmpty();
    }

    public static void main(String[] args) {
        String str = "({[]})";

        if (isBalanced(str)) {
            System.out.println("Balanced!");
        } else {
            System.out.println("Not Balanced!");
        }
    }
}
```

# 🔹 HashSet

## 1. Create a HashSet of Strings and add five elements.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        System.out.println(set);
    }
}
```

## 2. Add duplicate elements to a HashSet and observe behavior.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Three"); // HashSet remove automatically duplicate element
        set.add("Five");

        System.out.println(set);
    }
}
```

## 3. Remove an element from the HashSet.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        set.remove("One");
        System.out.println(set);
    }
}
```

## 4. Check if an element exists in the HashSet.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        System.out.println(set.contains("Two"));
    }
}
```

### 5. Get the size of the HashSet.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        System.out.println(set.size());
    }
}
```

## 6. Clear all elements from the HashSet.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        set.clear();

        System.out.println(set);
    }
}
```

## 7. Iterate over a HashSet using for-each loop.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        set.forEach(System.out::println);
    }
}
```

## 8. Iterate over a HashSet using Iterator.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        Iterator<String> iterator = set.iterator();

        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

## 9. Convert HashSet to Array.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        String[] arr = set.toArray(new String[0]);
    }
}
```

## 10. Convert HashSet to List.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set  = new HashSet<>();

        set.add("One");
        set.add("Two");
        set.add("Three");
        set.add("Four");
        set.add("Five");

        List<String> list = new ArrayList<>(set);

        System.out.println(list);
    }
}
```

## 11. Perform Union of two HashSets.
```java
class Main {
    public static void main(String[] args) {
        HashSet<Integer> set1 = new HashSet<>(Arrays.asList(1,2,3));
        HashSet<Integer> set2 = new HashSet<>(Arrays.asList(3,4,5));

        HashSet<Integer> unionSet =  new HashSet<>(set1);
        unionSet.addAll(set2);

        System.out.println(unionSet);
    }
}
```

## 12. Perform Intersection of two HashSets.
```java
class Main {
    public static void main(String[] args) {
        HashSet<Integer> set1 = new HashSet<>(Arrays.asList(1,2,3));
        HashSet<Integer> set2 = new HashSet<>(Arrays.asList(3,4,5));

        HashSet<Integer> intersection =  new HashSet<>(set1);
        intersection.retainAll(set2); // // keep only common elements

        System.out.println(intersection);
    }
}
```

## 13. Perform Difference between two HashSets.
```java
class Main {
    public static void main(String[] args) {
        HashSet<Integer> set1 = new HashSet<>(Arrays.asList(1,2,3));
        HashSet<Integer> set2 = new HashSet<>(Arrays.asList(3,4,5));

        HashSet<Integer> diffrence =  new HashSet<>(set1);
        diffrence.removeAll(set2);

        System.out.println(diffrence);
    }
}
```

## 14. Check if one HashSet is a subset of another.
```java
class Main {
    public static void main(String[] args) {
        HashSet<Integer> set1 = new HashSet<>(Arrays.asList(1,2,3,4));
        HashSet<Integer> set2 = new HashSet<>(Arrays.asList(1,2));

        boolean isSubset = set1.containsAll(set2);

        System.out.println(isSubset);
    }
}
```

## 15. Compare two HashSets and print common elements.
```java
class Main {
    public static void main(String[] args) {
        HashSet<Integer> set1 = new HashSet<>(Arrays.asList(1,2,3,4));
        HashSet<Integer> set2 = new HashSet<>(Arrays.asList(1,2,5,6));

        HashSet<Integer> common = new HashSet<>(set1);
        common.retainAll(set2);

        System.out.println(common);
    }
}
```

## 16. Understand why HashSet does not allow duplicates.
> **HashSet** is a type of **Set**, and by definition, **Set does not allow duplicate elements**.

---

## ⚙️ Internal Working of HashSet

- HashSet is internally backed by a **HashMap**.
- When you add an element to a HashSet:
  1. Java calculates the **hashCode** of the element.
  2. It checks whether the element **already exists** in the set (via the key of HashMap).
  3. If it does, it **ignores** the new one.
  4. If not, it **adds** the element.
 
## 17. Observe ordering in HashSet.
  > ❌ **No**, `HashSet` does **not guarantee any specific order** of elements.

It stores elements **based on their hashcode**, so the iteration order can appear random and may change.

## 18. Use null values in HashSet.
```java
class Main {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();

        set.add("Hello");
        set.add(null);
        set.add("World!");

        System.out.println(set);
    }
}
```

## 19. Compare performance of HashSet vs TreeSet.
### 🧠 Overview

| Feature              | `HashSet`                | `TreeSet`                   |
|----------------------|--------------------------|-----------------------------|
| Order Maintained?    | ❌ No                    | ✅ Sorted (natural order)   |
| Duplicate Allowed?   | ❌ No                    | ❌ No                        |
| Backed By            | HashMap                  | TreeMap (Red-Black Tree)    |
| Insertion Time       | ⚡ **O(1)** (avg case)   | 🐢 **O(log n)**              |
| Lookup Time          | ⚡ O(1) (avg case)       | 🐢 O(log n)                  |
| Deletion Time        | ⚡ O(1) (avg case)       | 🐢 O(log n)                  |
| Null Allowed?        | ✅ Yes (only one)        | ⚠️ No (throws NullPointerException) |


## 20. Compare performance of HashSet vs LinkedHashSet.
### 🧠 Overview

| Feature              | `HashSet`                | `LinkedHashSet`             |
|----------------------|--------------------------|-----------------------------|
| Order Maintained?    | ❌ No                    | ✅ Insertion Order          |
| Duplicate Allowed?   | ❌ No                    | ❌ No                        |
| Backed By            | HashMap                  | HashMap (with Linked List)  |
| Insertion Time       | ⚡ **O(1)** (avg case)   | ⚡ **O(1)** (avg case)       |
| Lookup Time          | ⚡ O(1) (avg case)       | ⚡ O(1) (avg case)           |
| Deletion Time        | ⚡ O(1) (avg case)       | ⚡ O(1) (avg case)           |
| Null Allowed?        | ✅ Yes (only one)        | ✅ Yes (only one)           |
| Extra Memory         | ❌ Minimal               | ✅ Slightly more (due to Linked List) |

## 21. Add custom objects to HashSet.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

public class Main {
    public static void main(String[] args) {
        HashSet<Person> personHashSet = new HashSet<>();

        personHashSet.add(new Person("Arman Ali", 18));
        personHashSet.add(new Person("Farman Ali", 20));

    }
}
```

## 22. Override equals() and hashCode() for custom objects.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public boolean equals(Object obj) {
        if(this == obj) return true;
        if(obj == null || obj.getClass() != this.getClass()) return  false;
        Person other = (Person) obj;
        return  this.age == other.age && Objects.equals(this.name, other.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(this.name, this.age);
    }
}

public class Main {
    public static void main(String[] args) {
        HashSet<Person> personHashSet = new HashSet<>();

        personHashSet.add(new Person("Arman Ali", 18));
        personHashSet.add(new Person("Arman Ali", 18));

        System.out.println(personHashSet);
    }
}
```

## 23. Prevent duplicate custom objects using hashCode().
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public boolean equals(Object obj) {
        if(this == obj) return true;
        if(obj == null || obj.getClass() != this.getClass()) return  false;
        Person other = (Person) obj;
        return  this.age == other.age && Objects.equals(this.name, other.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(this.name, this.age);
    }
}

public class Main {
    public static void main(String[] args) {
        HashSet<Person> personHashSet = new HashSet<>();

        personHashSet.add(new Person("Arman Ali", 18));
        personHashSet.add(new Person("Arman Ali", 18));

        System.out.println(personHashSet);
    }
}
```

## 24. Store student records in a HashSet (with id, name).
```java
class Student {
    private int id;
    private String name;

    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public String toString() {
        return "Student{" +
                "id=" + id +
                ", name='" + name + '\'' +
                '}';
    }
}

public class Main {
    public static void main(String[] args) {
        HashSet<Student> students  = new HashSet<>();

        students.add(new Student(1, "Armaan"));
        students.add(new Student(2, "Farman"));

        students.forEach(System.out::println);
    }
}
```

## 25. Detect duplicates in custom class using HashSet.
```java
import java.util.HashSet;
import java.util.Objects;

class Student {
    int id;
    String name;

    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public boolean equals(Object o) {
        if(this == o) return true;
        if(o == null || getClass() != o.getClass()) return false;
        Student student = (Student) o;
        return id == student.id && Objects.equals(name, student.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(id, name);
    }

    @Override
    public String toString() {
        return "Student{id=" + id + ", name='" + name + "'}";
    }
}

public class Main {
    public static void main(String[] args) {
        HashSet<Student> students = new HashSet<>();

        students.add(new Student(1, "Maan"));
        students.add(new Student(1, "Maan"));

        System.out.println("Size: " + students.size());
        System.out.println(students);
    }
}
```

## 26. Find duplicate elements in an array using HashSet.
```java
public class Main {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 2, 4, 5, 1, 6};
        HashSet<Integer> set = new HashSet<>();

        for (int num : arr) {
            if(!set.contains(num)) {
                set.add(num);
            }else {
                System.out.println("duplicate number is: " + num);
            }
        }
    }
}
```

## 27. Remove duplicates from a list using HashSet.
```java
public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>(Arrays.asList(1, 2, 3, 2, 4, 5, 1, 6));

        HashSet<Integer> set =  new HashSet<>(list);

        ArrayList<Integer> newList = new ArrayList<>(set);

        System.out.println(newList);
    }
}
```

## 28. Check if two strings have common characters.
```java
public class Main {
    public static void main(String[] args) {
        String str1 = "hello";
        String str2 = "world";

        HashSet<Character> set = new HashSet<>();

        for(char ch : str1.toCharArray()) {
            set.add(ch);
        }

        for(char ch : str2.toCharArray()) {
            if(set.contains(ch)) {
                System.out.println("Common character found: " + ch);
            }
        }
    }
}
```

## 29. Count unique words in a sentence using HashSet.
```java
public class Main {
    public static void main(String[] args) {
        String sentence = "hello world hello java";

        String[] strArray = sentence.split(" ");

        HashSet<String> set  = new HashSet<>(Arrays.asList(strArray));

        System.out.println("unique words count of sentence: " + set.size());
    }
}
```

## 30. Find the first repeated character in a string.
```java
public class Main {
    public static void main(String[] args) {
        String str = "hello world";

        Set<Character> set = new HashSet<>();

        for(char ch : str.toCharArray()) {
            set.add(ch);
        }

        for (char ch : set) {
            if(str.indexOf(ch) != str.lastIndexOf(ch)) {
                System.out.println("first repeated character: " + ch);
                break;
            }
        }

    }
}
```

## 31. Add null multiple times and observe behavior.
```java
public class Main {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();

        set.add("Hello");
        set.add(null);
        set.add(null);
        set.add(null);
        set.add("World");
        set.add(null);

        System.out.println(set);
    }
}
```

## 32. Add elements of mixed case (upper/lower) and analyze.
```java
public class Main {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();

        set.add("Apple");
        set.add("apple");
        set.add("APPLE");

        System.out.println(set);
    }
}
```

## 33. Add same object reference multiple times.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
public class Main {
    public static void main(String[] args) {
        HashSet<Person> set = new HashSet<>();

        Person p1 = new Person("Arman Ali", 18);

        set.add(p1);
        set.add(p1);
        set.add(p1);

        System.out.println(set);
    }
}
```

## 34. Add very large number of elements and test performance.
```java
public class Main {
    public static void main(String[] args) {
        HashSet<Integer> set = new HashSet<>();
        int limit = 1_000_000;

        long startTime = System.currentTimeMillis();

        for (int i = 0; i < limit; i++) {
            set.add(i);
        }

        long endTime = System.currentTimeMillis();

        System.out.println("Time taken to add " + limit + " elements: " + (endTime - startTime) + " ms");
    }
}
```

## 35. Use HashSet with initial capacity and load factor.
```java
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        // Initial capacity = 1000, Load factor = 0.80
        HashSet<Integer> set = new HashSet<>(1000, 0.80f);

        for (int i = 0; i < 1000; i++) {
            set.add(i);
        }

        System.out.println("Size: " + set.size());
    }
}

// initialCapacity: Starting size of internal HashMap buckets.
// loadFactor: Kitna full hone par resize hoga. Default is 0.75f.
```

## 36. Implement a method to return unique elements from a list.
```java
public class Main {

    public static ArrayList<Integer> getUniqueElements(ArrayList<Integer> list) {
        HashSet<Integer> set = new HashSet<>(list);

        return new ArrayList<>(set);
    }

    public static void main(String[] args) {
       ArrayList<Integer> list = new ArrayList<>(Arrays.asList(1,2,3,2,4,1,5));

       list =  getUniqueElements(list);

        System.out.println(list);
    }
}
```

## 37. Store IP addresses that visited a website using HashSet.
```java
public class Main {
    public static void main(String[] args) {
        HashSet<String> ipAddresses = new HashSet<>();

        ipAddresses.add("192.168.1.1");
        ipAddresses.add("10.0.0.2");
        ipAddresses.add("192.168.1.1");  // duplicate
        ipAddresses.add("172.16.0.5");

        System.out.println(ipAddresses);
    }
}
```

## 38. Find distinct integers in a matrix using HashSet.
```java
public class Main {
    public static void main(String[] args) {
        int[][] matrix = {
                {1, 2, 3},
                {4, 2, 6},
                {7, 8, 3}
        };

        HashSet<Integer> set = new HashSet<>();

        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                set.add(matrix[i][j]);
            }
        }

        System.out.println("Distinct Integers in Matrix: " + set);
    }
}
```

## 39. Find unique elements between two arrays.
```java
public class Main {
    public static void main(String[] args) {
        int[] arr1 = {1,2,3,4};
        int[] arr2 = {3,4,5,6};

        HashSet<Integer> set = new HashSet<>();

        for (int num : arr1) {
            set.add(num);
        }

        for (int num : arr2) {
            set.add(num);
        }

        System.out.println(set);
    }
}
```

## 40. Find unique elements between two arrays.
```java
public class Main {
    public static void main(String[] args) {
        int[] arr1 = {1,2,3,4};
        int[] arr2 = {3,4,5,6};

        HashSet<Integer> set1 = new HashSet<>();
        HashSet<Integer> set2 = new HashSet<>();

        for (int num : arr1) set1.add(num);
        for (int num : arr2) set2.add(num);

        HashSet<Integer> union = new HashSet<>(set1);
        union.addAll(set2);

        HashSet<Integer> intersection = new HashSet<>(set1);
        intersection.retainAll(set2);

        union.removeAll(intersection);

        System.out.println(union);
    }
}
```

## 41. Remove duplicate emails from contact list.
```java
public class Main {
    public static void main(String[] args) {
        ArrayList<String> contactList = new ArrayList<>();

        contactList.add("armaanali.dev@gmail.com");
        contactList.add("farman@gmail.com");
        contactList.add("armaanali.dev@gmail.com");
        contactList.add("jhon@gmail.com");

        HashSet<String> set = new HashSet<>(contactList);

        contactList = new ArrayList<>(set);

        System.out.println(contactList);
    }
}
```

## 42. Detect duplicate login attempts by user IDs.
```java
public class Main {
    public static void main(String[] args) {
        int[] loginAttempts = {101, 102, 103, 101, 104, 102};

        HashSet<Integer> seen = new HashSet<>();

        for (int id : loginAttempts) {
            if (seen.contains(id)){
                System.out.println("Duplicate login attempt by user ID: " + id);
            } else {
                seen.add(id);
            }
        }
    }
}
```

## 43. Store unique hashtags from a tweet list.
```java
public class Main {
    public static void main(String[] args) {
        HashSet<String> tweetList = new HashSet<>();

        tweetList.add("#coding");
        tweetList.add("#java");
        tweetList.add("#javaScript");
        tweetList.add("#java");

        System.out.println(tweetList);
    }
}
```

## 44. Store unique file names in a directory.
```java
public class Main {
    public static void main(String[] args) {
        HashSet<String> directory = new HashSet<>();
        
        directory.add("Main.java");
        directory.add("HelloWorld.java");
        directory.add("Main.java");

        System.out.println(directory);
    }
}
```

## 45. Track unique page views in a web app.
```java
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        int[] pageViews = {101, 102, 101, 103, 104, 102, 105};

        HashSet<Integer> uniqueVisitors = new HashSet<>();

        for (int userId : pageViews) {
            uniqueVisitors.add(userId);
        }

        System.out.println("Unique Page Views: " + uniqueVisitors.size());
        System.out.println("User IDs: " + uniqueVisitors);
    }
}
```

## 46. Manually implement a simplified HashSet using ArrayList.
```java
public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

        if (!list.contains(3)) list.add(3);
        if(!list.contains(5)) list.add(5);
        if (!list.contains(3)) list.add(3);

        System.out.println(list);
    }
}
```

## 47. Explain internal working of HashSet.
A `HashSet` in Java is a collection that does not allow duplicate elements and does not guarantee any specific order of the elements. Internally, a `HashSet` is backed by a `HashMap`. The `HashSet` uses the hashing mechanism to store its elements.

### Definition

- **HashSet** is a part of the Java Collections Framework.
- It implements the `Set` interface and is backed by a `HashMap`.
- It does not allow duplicate elements.
- It provides constant-time performance for basic operations like add, remove, and contains.

### Internal Structure

Internally, a `HashSet` works by using a `HashMap`. When an element is added to the set, it is inserted into the map as a key, and the value associated with each key is a constant (commonly `PRESENT`). The keys in the `HashMap` represent the unique elements in the `HashSet`.

#### Steps:

1. **Hashing**: When an element is added to the `HashSet`, the `hashCode()` method of the element is called to get its hash code.
2. **Indexing**: The hash code is then used to find the appropriate index in the internal array (bucket array) where the element should be placed.
3. **Collision Handling**: If two elements have the same hash code (a collision), the elements are stored in the same bucket using a linked list or tree structure (in the case of many collisions).
4. **Equality Check**: Before adding the element, `HashSet` checks if the element already exists using the `equals()` method to ensure no duplicates are inserted.

# 🔹 LinkedHashSet

## 1. Create a LinkedHashSet and add five elements.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        System.out.println(lhs);
    }
}
```

## 2. Add duplicate elements and observe behavior.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(2);
        lhs.add(5);

        System.out.println(lhs);
    }
}
```

## 3. Remove an element from the LinkedHashSet.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        lhs.remove(3);
        System.out.println(lhs);
    }
}
```

## 4. Check if an element exists in the LinkedHashSet.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        System.out.println(lhs.contains(50));
    }
}
```

## 5. Get the size of the LinkedHashSet.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        System.out.println(lhs.size());
    }
}
```

## 6. Clear all elements from the LinkedHashSet.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        lhs.clear();
        
        System.out.println(lhs);
    }
}
```

## 7. Iterate using for-each loop.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        lhs.forEach(System.out::println);
    }
}
```

## 8. Iterate using Iterator.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        Iterator<Integer> iterator = lhs.iterator();

        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

## 9. Convert LinkedHashSet to Array.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs = new LinkedHashSet<>();

        lhs.add(1);
        lhs.add(2);
        lhs.add(3);
        lhs.add(4);
        lhs.add(5);

        int[] arr = lhs.stream().mapToInt(Integer::intValue).toArray();

        for (int n : arr) {
            System.out.println(n);
        }
    }
}
```

## 10. Convert LinkedHashSet to List.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<String> lhs = new LinkedHashSet<>();

        lhs.add("Hello");
        lhs.add("World");

        ArrayList<String> list = new ArrayList<>(lhs);

        System.out.println(list);
    }
}
```

## 11. Compare output of HashSet and LinkedHashSet.
```java
public class Main {
    public static void main(String[] args) {
        HashSet<Integer> hashSet = new HashSet<>();

        hashSet.add(10);
        hashSet.add(1);
        hashSet.add(2);
        hashSet.add(1);
        hashSet.add(3);
        hashSet.add(5);

        System.out.println(hashSet);

        LinkedHashSet<Integer> linkedHashSet =  new LinkedHashSet<>();

        linkedHashSet.add(10);
        linkedHashSet.add(1);
        linkedHashSet.add(2);
        linkedHashSet.add(1);
        linkedHashSet.add(3);
        linkedHashSet.add(5);

        System.out.println(linkedHashSet);
    }
}
```

## 12. Maintain insertion order using LinkedHashSet.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<String> lhs = new LinkedHashSet<>();

        lhs.add("One");
        lhs.add("Two");
        lhs.add("Three");
        lhs.add("Four");
        lhs.add("Five");

        lhs.forEach(System.out::println);
    }
}
```

## 13. Verify if insertion order is preserved after removal.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<String> lhs = new LinkedHashSet<>();

        lhs.add("One");
        lhs.add("Two");
        lhs.add("Three");
        lhs.add("Four");
        lhs.add("Five");

        lhs.remove("Three");

        lhs.forEach(System.out::println);
    }
}
```

## 14. Re-insert a removed element and check its position.    
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<String> lhs = new LinkedHashSet<>();

        lhs.add("One");
        lhs.add("Two");
        lhs.add("Three");
        lhs.add("Four");
        lhs.add("Five");

        lhs.remove("Three");

        lhs.add("Three");

        lhs.forEach(System.out::println);
    }
}
```

## 15. Add null values and observe position.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<String> lhs = new LinkedHashSet<>();

        lhs.add("One");
        lhs.add("Two");
        lhs.add(null);
        lhs.add("Three");
        lhs.add("Four");
        lhs.add("Five");
        lhs.add(null);

        lhs.forEach(System.out::println);
    }
}
```

## 16. Perform union of two LinkedHashSets.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs1 = new LinkedHashSet<>(Arrays.asList(1,2,3,4));
        LinkedHashSet<Integer> lhs2 = new LinkedHashSet<>(Arrays.asList(3,4,5,6));

        LinkedHashSet<Integer> union = new LinkedHashSet<>(lhs1);
        union.addAll(lhs2);

        System.out.println(union);
    }
}
```

## 17. Perform intersection of two LinkedHashSets.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs1 = new LinkedHashSet<>(Arrays.asList(1,2,3,4));
        LinkedHashSet<Integer> lhs2 = new LinkedHashSet<>(Arrays.asList(3,4,5,6,1));

        LinkedHashSet<Integer> intersection = new LinkedHashSet<>(lhs1);
        intersection.retainAll(lhs2);

        System.out.println(intersection);
    }
}
```

## 18. Perform difference of two LinkedHashSets.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs1 = new LinkedHashSet<>(Arrays.asList(1,2,3,4));
        LinkedHashSet<Integer> lhs2 = new LinkedHashSet<>(Arrays.asList(3,4,5,6,1));

        LinkedHashSet<Integer> union = new LinkedHashSet<>(lhs1);
        union.addAll(lhs2);

        LinkedHashSet<Integer> intersection = new LinkedHashSet<>(lhs1);
        intersection.retainAll(lhs2);

        union.removeAll(intersection);

        System.out.println(union);
    }
}
```

## 19. Check if one LinkedHashSet is subset of another.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs1 = new LinkedHashSet<>(Arrays.asList(1,2,3,4));
        LinkedHashSet<Integer> subset = new LinkedHashSet<>(Arrays.asList(1, 5, 2));

        if(lhs1.containsAll(subset)) {
            System.out.println("Yes!");
        } else {    
            System.out.println("No!");
        }
    }
}
```

## 20. Compare two LinkedHashSets and print common elements.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> lhs1 = new LinkedHashSet<>(Arrays.asList(1, 2, 3, 4));
        LinkedHashSet<Integer> lhs2 = new LinkedHashSet<>(Arrays.asList(3, 4, 5, 6));

        lhs1.retainAll(lhs2);
        
        System.out.println(lhs1);
    }
}
```

## 21. Add custom class objects (like Book, Student).
```java
class Student {
    private int rollNo;
    private String name;

    public Student(int rollNo, String name) {
        this.rollNo = rollNo;
        this.name = name;
    }

    public int getRollNo() {
        return rollNo;
    }

    public void setRollNo(int rollNo) {
        this.rollNo = rollNo;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Student> students = new LinkedHashSet<>();

        students.add(new Student(14, "Arman ali"));
        students.add(new Student(21, "Farman Khan"));

        students.forEach(s -> System.out.println(s.getName()));
    }
}
```

## 22. Implement equals() and hashCode() for ordering.
```java
class Student {
    private int rollNo;
    private String name;

    public Student(int rollNo, String name) {
        this.rollNo = rollNo;
        this.name = name;
    }

    public int getRollNo() {
        return rollNo;
    }

    public void setRollNo(int rollNo) {
        this.rollNo = rollNo;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public int hashCode() {
        return Objects.hash(this.rollNo, this.name);
    }

    @Override
    public boolean equals(Object obj) {
        if(obj == this) return true;
        if(obj == null || obj.getClass() != this.getClass()) return false;
        Student other = (Student) obj;

        return  this.rollNo == other.rollNo && Objects.equals(this.name, other.name);
    }
}

public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Student> students = new LinkedHashSet<>();

        students.add(new Student(14, "Arman ali"));
        students.add(new Student(21, "Farman Khan"));

        students.forEach(s -> System.out.println(s.getName()));
    }
}
```

## 23. Remove duplicate custom objects using LinkedHashSet.
```java
import java.util.LinkedHashSet;
import java.util.Objects;

class Student {
    private int rollNo;
    private String name;

    public Student(int rollNo, String name) {
        this.rollNo = rollNo;
        this.name = name;
    }

    @Override
    public boolean equals(Object o) {
        if (o == null || getClass() != o.getClass()) return false;
        Student student = (Student) o;
        return rollNo == student.rollNo && Objects.equals(name, student.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(rollNo, name);
    }

    public int getRollNo() {
        return rollNo;
    }

    public void setRollNo(int rollNo) {
        this.rollNo = rollNo;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Student> students = new LinkedHashSet<>();

        students.add(new Student(14, "Arman ali"));
        students.add(new Student(15, "Farman khan"));
        students.add(new Student(14, "Arman ali"));

        students.forEach(e -> System.out.println(e.getName()));
    }
}
```

## 24. Store user records in LinkedHashSet (id, name, email).
```java
class User {
    private int id;
    private String name;
    private int age;

    public User(int id, String name, int age) {
        this.id = id;
        this.name = name;
        this.age = age;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
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

public class Main {
    public static void main(String[] args) {
        LinkedHashSet<User> users = new LinkedHashSet<>();

        users.add(new User(1, "Arman", 17));
        users.add(new User(2, "Farman", 18));

        users.forEach(u -> System.out.println(u.getName()));
    }
}
```


## 25. Remove duplicate characters from string (keep order).
```java
public class Main {
    public static void main(String[] args) {
        String str = "hello world";
        LinkedHashSet<Character> set = new LinkedHashSet<>();

        for (char ch : str.toCharArray()) {
            set.add(ch);
        }

        str = set.stream().map(s -> s.toString()).collect(Collectors.joining(""));

        System.out.println(str);
    }
}
```

## 26. Find first non-repeating character using LinkedHashSet.
```java
public class Main {
    public static void main(String[] args) {
        String str = "hello world";
        LinkedHashSet<Character> set = new LinkedHashSet<>();

        for (char ch : str.toCharArray()) {
            set.add(ch);
        }

        for (char ch : set) {
            if(str.indexOf(ch) == str.lastIndexOf(ch)) {
                System.out.println("First Non-Repeating Character: " + ch);
                break;
            }
        }
    }
}
```

## 27. Store elements from a list while preserving uniqueness and order.
```java
public class Main {
    public static void main(String[] args) {
        List<Integer> list = new ArrayList<>();

        list.add(1);
        list.add(2);
        list.add(3);
        list.add(2);

        LinkedHashSet<Integer> linkedHashSet = new LinkedHashSet<>(list);

        System.out.println(linkedHashSet);
    }
}
```

## 28. Filter unique words from a paragraph while keeping order.
```java
public class Main {
    public static void main(String[] args) {
        String paragraph = "java is great and java is powerful";
        LinkedHashSet<String> set = new LinkedHashSet<>(Arrays.asList(paragraph.split(" ")));

        paragraph = set.stream().collect(Collectors.joining(" "));

        System.out.println(paragraph);
    }
}
```

## 29. Count frequency of elements using LinkedHashSet + Map.
```java
public class Main {
    public static void main(String[] args) {
        String paragraph = "java is great and java is powerful";
        LinkedHashSet<String> set = new LinkedHashSet<>(Arrays.asList(paragraph.split(" ")));

        Map<String, Integer> frequencyMap = new HashMap<>();

        for (String word : set) {
            int count = 0;
            for(String tmpWord : paragraph.split(" ")) {
                if(word.equals(tmpWord)) {
                    count++;
                }
            }

            frequencyMap.put(word, count);
        }

        frequencyMap.forEach((key, value) ->   System.out.println(key + ": " + value));
    }
}
```

## 30. Add multiple nulls and analyze.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<String> set = new LinkedHashSet<>();

        set.add("hello");
        set.add(null);
        set.add(null);
        set.add("world");
        set.add(null);

        System.out.println(set);
    }
}
```

## 31. Add elements with similar hashCode.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public int hashCode() {
        return name.hashCode();
    }

    @Override
    public boolean equals(Object o) {
        if (o == null || getClass() != o.getClass()) return false;
        Person person = (Person) o;
        return name.equals(person.name);
    }
}

public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Person> set = new LinkedHashSet<>();

        set.add(new Person("jhon", 20));
        set.add(new Person("arman", 18));
        set.add(new Person("jhon", 20));

        for (Person person : set) {
            System.out.println(person.getName());
        }
    }
}
```

## 32. Add elements with different types (observe compile-time errors).
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        set.add(1);
        set.add("Hello");
    }
}
```

## 33. Add large number of elements to test order preservation.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        for ( int i = 1; i <= 100000; i++) {
            set.add(i);
        }

        for (Integer num : set) {
            System.out.println(num);
        }
    }
}
```

## 34. Use LinkedHashSet with initial capacity and load factor.
```java
import java.util.LinkedHashSet;

public class Main {
    public static void main(String[] args) {
        // LinkedHashSet with initial capacity = 10 and load factor = 0.75
        LinkedHashSet<Integer> set = new LinkedHashSet<>(10, 0.75f);

        // Adding elements to the LinkedHashSet
        set.add(1);
        set.add(2);
        set.add(3);
        set.add(4);

        System.out.println(set);
    }
}

// 10: Initial capacity (set ki size pehle 10 elements ko accommodate kar sakega).
// 0.75f: Load factor (jab set ka size 75% ho jaayega, tab internal capacity ko double kar diya jayega).
```

## 35. Convert LinkedHashSet to TreeSet.
```java
public class Main {
    public static void main(String[] args) {
        LinkedHashSet<Integer> linkedHashSet = new LinkedHashSet<>(Arrays.asList(1,2,3,4,5));

        TreeSet<Integer> treeSet = new TreeSet<>(linkedHashSet);

        System.out.println(treeSet);
    }
}
```

## 36. Convert ArrayList to LinkedHashSet to remove duplicates.
```java
public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>(Arrays.asList(1,2,3,4,5,3,1));

        LinkedHashSet<Integer> set = new LinkedHashSet<>(list);

        set.forEach(System.out::println);
    }
}
```

## 37. Compare HashSet vs LinkedHashSet insertion order.
- **HashSet**:
  - Does not preserve insertion order.
  - Elements are stored based on their hash code.

- **LinkedHashSet**:
  - Preserves the insertion order.
  - Elements are stored in a linked list along with their hash code.

## 38. Measure performance: LinkedHashSet vs TreeSet.
- **LinkedHashSet**:
  - **Time Complexity**:
    - Insertion: **O(1)** (amortized)
    - Search: **O(1)**
    - Removal: **O(1)**
  - Preserves insertion order.
  - Uses a hash table to store elements.

- **TreeSet**:
  - **Time Complexity**:
    - Insertion: **O(log n)**
    - Search: **O(log n)**
    - Removal: **O(log n)**
  - Does **not** preserve insertion order.
  - Implements a **Red-Black Tree** to store elements, which ensures elements are sorted.

## 39. Understand internal structure of LinkedHashSet.
# Internal Structure of LinkedHashSet

- `LinkedHashSet` is a **hash table** + **doubly linked list** implementation of the `Set` interface.
- It **preserves insertion order**, unlike `HashSet`.

## 🔧 Inheritance Hierarchy:
```java
LinkedHashSet<E>
  ↳ extends HashSet<E>
      ↳ implements Set<E>
```

# 🔹 TreeSet

## 1. Create a TreeSet and add elements.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);

        System.out.println(set);
    }
}
```

## 2. Add duplicate elements and observe behavior.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        System.out.println(set);
    }
}
```

## 3. Remove an element from the TreeSet.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        set.remove(3);

        System.out.println(set);
    }
}
```

## 4. Check if an element exists in the TreeSet.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        System.out.println(set.contains(3));
    }
}
```

## 5. Get the size of the TreeSet.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        System.out.println(set.size());
    }
}
```

## 6. Clear all elements from the TreeSet.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        set.clear();
        System.out.println(set.size());
    }
}
```

## 7. Iterate using for-each loop.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        set.forEach(System.out::println);
    }
}
```

## 8. Iterate using Iterator.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        Iterator<Integer> iterator = set.iterator();

        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

## 9. Convert TreeSet to Array.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        Integer[] arr = set.toArray(new Integer[0]);

        for (Integer num : arr) {
            System.out.println(num);
        }
    }
}
```

## 10. Convert TreeSet to List.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(2);
        set.add(3);
        set.add(1);
        set.add(3);

        ArrayList<Integer> list = new ArrayList<>(set);

        System.out.println(list);
    }
}
```

## 11. Verify natural sorting of integers.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        set.add(100);
        set.add(56);
        set.add(20);
        set.add(40);
        set.add(101);

        System.out.println(set);
    }
}
```

## 12. Add strings and verify alphabetical sorting.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<String> set = new TreeSet<>();

        set.add("Armaan Ali");
        set.add("Farman Ali");
        set.add("Ali");
        set.add("Maan");

        set.forEach(System.out::println);
    }
}
```

## 13. Create TreeSet of custom objects (implement Comparable).
```java
class User {
    private String email;
    private String password;

    public User(String email, String password) {
        this.email = email;
        this.password = password;
    }

    public String getEmail() {
        return email;
    }

    public String getPassword() {
        return password;
    }

    @Override
    public String toString() {
        return "User{" +
                "email='" + email + '\'' +
                ", password='" + password + '\'' +
                '}';
    }

}

public class Main {
    public static void main(String[] args) {
        TreeSet<User> users = new TreeSet<>((u1, u2) -> u1.getEmail().compareTo(u2.getEmail()));

        users.add(new User("armaanali.dev@gmail.com", "arman"));
        users.add(new User("farman@gmail.com", "farman"));
        users.add(new User("armaanali.dev@gmail.com", "arman"));

        users.forEach(System.out::println);
    }
}
```

## 14. Sort custom objects by name or age.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age='" + age + '\'' +
                '}';
    }
}

public class Main {
    public static void main(String[] args) {
        TreeSet<Person> personTreeSet = new TreeSet<>((p1, p2) -> Integer.compare(p1.getAge(), p2.getAge()) );

        personTreeSet.add(new Person("Arman", 18));
        personTreeSet.add(new Person("Farman", 20));
        personTreeSet.add(new Person("Maan", 17));

        personTreeSet.forEach(System.out::println);
    }
}
```

## 15. Reverse the TreeSet using descendingSet().
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age='" + age + '\'' +
                '}';
    }
}

public class Main {
    public static void main(String[] args) {
        TreeSet<Person> personTreeSet = new TreeSet<>((p1, p2) -> Integer.compare(p1.getAge(), p2.getAge()) );

        personTreeSet.add(new Person("Arman", 18));
        personTreeSet.add(new Person("Farman", 20));
        personTreeSet.add(new Person("Maan", 17));

        System.out.println( personTreeSet.descendingSet());
    }
}
```

### 16. Use first() and last() methods.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age='" + age + '\'' +
                '}';
    }
}

public class Main {
    public static void main(String[] args) {
        TreeSet<Person> personTreeSet = new TreeSet<>((p1, p2) -> Integer.compare(p1.getAge(), p2.getAge()) );

        personTreeSet.add(new Person("Arman", 18));
        personTreeSet.add(new Person("Farman", 20));
        personTreeSet.add(new Person("Maan", 17));

        System.out.println( personTreeSet.first());
        System.out.println( personTreeSet.last());
    }
}
```

## 17. Use higher() and lower() methods.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> numbers = new TreeSet<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);

        System.out.println("Higher than 20: " + numbers.higher(20)); // 30
        System.out.println("Lower than 20: " + numbers.lower(20)); // 10
    }
}
```

## 18. Use ceiling() and floor() methods.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> numbers = new TreeSet<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);


        System.out.println("Ceiling of 25: " + numbers.ceiling(25)); // ➜ 30
        System.out.println("Ceiling of 30: " + numbers.ceiling(30)); // ➜ 30
        System.out.println("Ceiling of 45: " + numbers.ceiling(45)); // ➜ null

        System.out.println("Floor of 25: " + numbers.floor(25));     // ➜ 20
        System.out.println("Floor of 20: " + numbers.floor(20));     // ➜ 20
        System.out.println("Floor of 5: " + numbers.floor(5));       // ➜ null
    }
}
```
## 19. Use headSet() to get values less than a given element.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(0);
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);

        System.out.println(numbers.headSet(30));
    }
}
```

## 20. Use tailSet() to get values greater than or equal to an element.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(0);
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);

        System.out.println(numbers.tailSet(20));
    }
}
```

## 21. Perform union of two TreeSets.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set1 = new TreeSet<>(Arrays.asList(1,2,3,4));
        TreeSet<Integer> set2 = new TreeSet<>(Arrays.asList(3,4,5,6));

        TreeSet<Integer> union = new TreeSet<>(set1);
        union.addAll(set2);

        System.out.println(union);
    }
}
```

## 22. Perform intersection of two TreeSets.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set1 = new TreeSet<>(Arrays.asList(1,2,3,4));
        TreeSet<Integer> set2 = new TreeSet<>(Arrays.asList(3,4,5,6));

        TreeSet<Integer> intersection = new TreeSet<>(set1);
        intersection.retainAll(set2);

        System.out.println(intersection);
    }
}
```

## 23. Perform difference of two TreeSets.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set1 = new TreeSet<>(Arrays.asList(1,2,3,4));
        TreeSet<Integer> set2 = new TreeSet<>(Arrays.asList(3,4,5,6));

        TreeSet<Integer> union = new TreeSet<>(set1);
        union.addAll(set2);

        TreeSet<Integer> intersection = new TreeSet<>(set1);
        intersection.retainAll(set2);

        union.removeAll(intersection);

        System.out.println(union);
    }
}
```

## 24. Check if one TreeSet is subset of another.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set1 = new TreeSet<>(Arrays.asList(1,2,3,4));
        TreeSet<Integer> set2 = new TreeSet<>(Arrays.asList(3,4));

        System.out.println(set1.containsAll(set2) ? "Yes set2 is subset of set1" : "No set2 is not subset of set1");
    }
}
```

## 25. Compare two TreeSets and print common elements.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set1 = new TreeSet<>(Arrays.asList(10, 20, 30, 40));
        TreeSet<Integer> set2 = new TreeSet<>(Arrays.asList(20, 30, 50, 60));

        for (Integer num : set2) {
            if(set1.contains(num)) {
                System.out.println("Common Element: " + num);
            }
        }
    }
}
```

## 26. Convert TreeSet to ArrayList.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>(Arrays.asList(10, 20, 30, 40));
        ArrayList<Integer> list = new ArrayList<>(set);
    }
}
```

## 27. Convert TreeSet to LinkedList.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>(Arrays.asList(10, 20, 30, 40));
        LinkedList<Integer> list = new LinkedList<>(set);
    }
}
```

## 28. Convert ArrayList to TreeSet to remove duplicates.
```java
public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>(Arrays.asList(10, 20, 30, 50, 60, 40, 20, 30, 100));
        TreeSet<Integer> set = new TreeSet<>(list);

        set.forEach(System.out::println);
    }
}
```

## 29. Convert TreeSet to HashSet.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> treeSet = new TreeSet<>(Arrays.asList(10, 20, 30, 50, 60, 40, 20, 30, 100));
        HashSet<Integer> hashSet = new LinkedHashSet<>(treeSet);

        hashSet.forEach(System.out::println);
    }
}
```

## 30. Convert TreeSet to String.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<String> treeSet = new TreeSet<>(Arrays.asList("Hello", "How", "Are", "You"));
        String str = treeSet.stream().collect(Collectors.joining(" "));

        System.out.println(str);
    }
}
```

## 31. Add null values and observe behavior.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<String> treeSet = new TreeSet<>(Arrays.asList("Hello", "How", "Are",null, "You"));

        System.out.println(treeSet);
        // If you try to add null to a TreeSet (which uses natural ordering or comparator), it will throw a NullPointerException at runtime because null cannot             be compared to other elements.
    }
}
```

## 32. Add mixed data types (observe compile-time error).
A TreeSet is a generic collection that requires all elements to be of the same type. Adding mixed data types will result in a compile-time error, as elements must be mutually comparable.

## 33. Add custom objects without Comparable (runtime error).
If you add custom objects to a TreeSet without implementing Comparable or without providing a Comparator, Java will throw a ClassCastException at runtime, because TreeSet won’t know how to compare the objects.

## 34. Insert duplicate custom objects and observe behavior.
TreeSet does not allow duplicate elements. For custom objects, it uses the result of compareTo() (or provided Comparator) to decide uniqueness — not .equals() or .hashCode().

## 35. Add large number of elements and check sorting performance.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> set = new TreeSet<>();

        for(int i = 9999999; i >= 1; i--) {
            set.add(i);
        }

        set.forEach(System.out::println);
    }
}
```

## 36. Store sorted user IDs.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<String> userIds = new TreeSet<>();

        userIds.add("arman1");
        userIds.add("arman3");
        userIds.add("arman4");
        userIds.add("arman2");
        userIds.add("arman5");

        System.out.println(userIds);
    }
}
```

## 37. Filter and sort product prices.
```java
public class Main {
    public static void main(String[] args) {
      TreeSet<Integer> prices = new TreeSet<>(Arrays.asList(299, 1200, 499, 750, 999, 150));

      Set<Integer> filteredPrices = prices.stream().filter(p -> p > 500).collect(Collectors.toSet());

      System.out.println(filteredPrices);
    }
}
```

## 38. Use custom Comparator to sort in reverse order.
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

    public int getAge() {
        return age;
    }


    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}

class NameComparator implements Comparator<Student> {
    @Override
    public int compare(Student o1, Student o2) {
        return o2.getName().compareTo(o1.getName());
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Student> students = new ArrayList<>();

        students.add(new Student("Arman", 18));
        students.add(new Student("Farman", 19));
        students.add(new Student("Ali", 17));

        Collections.sort(students, new NameComparator());

        students.forEach(System.out::println);
    }
}
```

## 38. Create TreeSet of objects sorted by multiple fields.
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

    public int getAge() {
        return age;
    }


    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}

class StudentComparator implements Comparator<Student> {
    @Override
    public int compare(Student o1, Student o2) {
        int nameCompare = o1.getName().compareTo(o2.getName());

        if (nameCompare != 0) {
            return nameCompare;
        } else {
            return Integer.compare(o1.getAge(), o2.getAge());
        }
    }
}

public class Main {
    public static void main(String[] args) {
        TreeSet<Student> students = new TreeSet<>(new StudentComparator());

        students.add(new Student("Arman", 18));
        students.add(new Student("Farman", 19));
        students.add(new Student("Ali", 17));
        students.add(new Student("Arman", 17));


        for (Student student : students) {
            System.out.println(student);
        }
    }
}
```

## 39. Use TreeSet to implement auto-suggestions.
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<String> words = new TreeSet<>();

        words.add("apple");
        words.add("app");
        words.add("application");
        words.add("bat");
        words.add("banana");
        words.add("ball");

       String prefix = "app";

        for (String word : words.tailSet(prefix)) {
            if (word.startsWith(prefix)) {
                System.out.println(word);
            } else {
                break;
            }
        }
    }
}
```

## 40. Range queries using subSet().
```java
public class Main {
    public static void main(String[] args) {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);
        numbers.add(50);

        System.out.println(numbers.subSet(20, 40));
    }
}
```

## 41. Compare TreeSet vs HashSet (performance + sorting).
- **Performance**:
  - **TreeSet**: Slower than **HashSet** for basic operations (add, remove, contains) due to its underlying **Red-Black tree** structure (O(log n) time complexity).
  - **HashSet**: Faster for basic operations with an average time complexity of O(1) due to its underlying **hash table** structure.

- **Sorting**:
  - **TreeSet**: Elements are **sorted** in natural order (or according to a specified comparator).
  - **HashSet**: Does not guarantee any sorting of elements.


## 42. Understand internal structure of TreeSet (Red-Black Tree).

### 1. Red-Black Tree Basics

A **Red-Black Tree** is a self-balancing binary search tree (BST). It satisfies the following properties:

#### Binary Search Tree (BST) Property:
- For any given node `N`, all the values in the left subtree of `N` are smaller, and all the values in the right subtree of `N` are larger.

#### Red-Black Properties:
- **Root is Black:** The root of the tree is always black.
- **Red Nodes Can't Have Red Children:** No two red nodes can be adjacent (a red node cannot have a red child).
- **Every Path from Root to Null Has the Same Number of Black Nodes:** The number of black nodes from the root to any leaf (or null) node must be the same.
- **Red-Black Properties Ensure Balanced Height:** These properties ensure that the height of the tree remains balanced, resulting in logarithmic time complexity for insertion, deletion, and search operations.

### 2. TreeSet Structure in Java

A `TreeSet` in Java is backed by a **Red-Black Tree**, which ensures the following:

- **Sorted Elements:** `TreeSet` stores its elements in natural order (or according to a provided comparator). The Red-Black Tree maintains this order.
- **No Duplicates:** `TreeSet` does not allow duplicate elements. If an element is already present, it is not added again.
- **Navigable:** `TreeSet` implements the `NavigableSet` interface, which provides methods like `lower()`, `higher()`, `floor()`, and `ceiling()` to navigate through the set efficiently.


# 🔹 PriorityQueue

## 1. Create a PriorityQueue of integers.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.add(20);
        pq.add(10);
        pq.add(30);
        pq.add(15);

        System.out.println(pq);
    }
}
```

## 2. Add elements to the queue using offer().
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);

        System.out.println(pq);
    }
}
```

## 3. Retrieve and remove the head using poll().
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);

        pq.poll();

        System.out.println(pq);
    }
}
```

## 4. Retrieve but do not remove the head using peek().
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);

        System.out.println(pq.peek());
    }
}
```

## 5. Check if queue contains an element.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);

        System.out.println(pq.contains(10));
    }
}
```

## 6. Get the size of the queue.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);

        System.out.println(pq.size());
    }
}
```

## 7. Iterate through the PriorityQueue.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);

        Iterator<Integer> iterator = pq.iterator();

        while(iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```

## 8. Clear all elements from the queue.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);

        pq.clear();

        System.out.println(pq);
    }
}
```

## 9. Add duplicate elements and observe behavior.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(30);
        pq.offer(15);
        pq.offer(10);

        System.out.println(pq);
    }
}
```

## 10. Add negative numbers and check order.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(-30);
        pq.offer(15);
        pq.offer(10);

        System.out.println(pq);
    }
}
```

## 11. Insert integers and observe natural sorting.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(20);
        pq.offer(10);
        pq.offer(-30);
        pq.offer(15);
        pq.offer(10);

        System.out.println(pq);
    }
}
```

## 12. Add strings and check lexicographical order.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<String> pq = new PriorityQueue<>();

        pq.offer("Hello");
        pq.offer("How");
        pq.offer("Are");
        pq.offer("You");

        pq.forEach(System.out::println);
    }
}
```

## 13. Use forEach to print elements (not necessarily sorted).
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<String> pq = new PriorityQueue<>();

        pq.offer("Hello");
        pq.offer("How");
        pq.offer("Are");
        pq.offer("You");

        pq.forEach(System.out::println);
    }
}
```

## 14. Poll all elements and print in sorted order.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<String> pq = new PriorityQueue<>();

        pq.add("banana");
        pq.add("apple");
        pq.add("cherry");

        while (!pq.isEmpty()) {
            System.out.println(pq.poll());
        }
    }
}
```

## 15. Compare PriorityQueue with TreeSet ordering.

### PriorityQueue
- Maintains elements in **heap order** (min-heap by default).
- Only the **smallest element is guaranteed at the front**.
- Internal order is **not fully sorted**.
- `poll()` or `peek()` gives the smallest element.
- Allows **duplicates**.

### TreeSet
- Maintains elements in **sorted order** (ascending by default).
- All elements are stored in **fully sorted form**.
- Uses **Red-Black Tree** internally.
- No need to `poll()` to get sorted data.
- **Does not allow duplicates**.

## 16. Create max heap using Comparator.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<String> pq = new PriorityQueue<>(Comparator.reverseOrder());

        pq.add("banana");
        pq.add("apple");
        pq.add("cherry");

        for (String s : pq) {
            System.out.println(s);
        }
    }
}
```

## 17. Create PQ that sorts strings in reverse order.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<String> pq = new PriorityQueue<>(Comparator.reverseOrder());

        pq.add("banana");
        pq.add("apple");
        pq.add("date");
        pq.add("cherry");

        for (String s : pq) {
            System.out.println(s);
        }
    }
}
```

## 18. Store custom objects with custom Comparator.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}

class PersonComparator implements Comparator<Person> {
    @Override
    public int compare(Person o1, Person o2) {
        return o1.getAge() - o2.getAge();
    }
}

public class Main {
    public static void main(String[] args) {
        PriorityQueue<Person> pq = new PriorityQueue<>(new PersonComparator());

        pq.offer(new Person("Armaan Ali", 18));
        pq.offer(new Person("Farman Ali", 20));
        pq.offer(new Person("Ali", 17));

        for (Person person : pq) {
            System.out.println(person);
        }
    }
}
```

## 19. Sort people by age in descending order.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}

class PersonComparator implements Comparator<Person> {
    @Override
    public int compare(Person o1, Person o2) {
        return o2.getAge() - o1.getAge();
    }
}

public class Main {
    public static void main(String[] args) {
        PriorityQueue<Person> pq = new PriorityQueue<>(new PersonComparator());

        pq.offer(new Person("Armaan Ali", 18));
        pq.offer(new Person("Farman Ali", 20));
        pq.offer(new Person("Ali", 17));

        for (Person person : pq) {
            System.out.println(person);
        }
    }
}
```

## 20. Use remove() to delete specific element.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(10);
        pq.offer(20);
        pq.offer(30);
        pq.offer(40);
        pq.offer(50);

        pq.remove(30);

        System.out.println(pq);
    }
}
```

## 21. Use contains() to check membership.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(10);
        pq.offer(20);
        pq.offer(30);
        pq.offer(40);
        pq.offer(50);

        System.out.println(pq.contains(30));
    }
}
```

## 22. Use isEmpty() before polling.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(10);
        pq.offer(20);
        pq.offer(30);
        pq.offer(40);
        pq.offer(50);

        System.out.println(pq.isEmpty());

        while (!pq.isEmpty()) {
            pq.poll();
        }

        System.out.println(pq.isEmpty());
    }
}
```

## 23. Convert PriorityQueue to Array.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(10);
        pq.offer(20);
        pq.offer(30);
        pq.offer(40);
        pq.offer(50);

        Integer[] arr = pq.toArray(new Integer[0]);

        for (Integer num : arr) {
            System.out.println(num);
        }
    }
}
```

## 24. Convert List to PriorityQueue.
```java
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(10);
        pq.offer(20);
        pq.offer(30);
        pq.offer(40);
        pq.offer(50);

        ArrayList<Integer> list = new ArrayList<>(pq);

        System.out.println(list);
    }
}
```

## 25. Find k largest elements using max heap.
```java
public class Main {
    public static void main(String[] args) {
        int[] nums = {4, 1, 7, 3, 8, 5};
        int k = 4;

        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());

        for (int num : nums) {
            maxHeap.offer(num);
        }

        for(int i = 0; i < k; i++) {
            System.out.println(maxHeap.poll());
        }
    }
}
```

## 26. Find k smallest elements using min heap.
```java
public class Main {
    public static void main(String[] args) {
        int[] nums = {4, 1, 7, 3, 8, 5};
        int k = 4;

        PriorityQueue<Integer> minHeap = new PriorityQueue<>();

        for (int num : nums) {
            minHeap.offer(num);
        }

        for(int i = 0; i < k; i++) {
            System.out.println(minHeap.poll());
        }
    }
}
```
