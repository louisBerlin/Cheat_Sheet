# SET

```java
Set<String> fruits = new HashSet<>();

// Adding elements

fruits.add("Apple");
fruits.add("Banana");
fruits.add("Orange");

// Checking the existence of an element

boolean containsApple = fruits.contains("Apple");

// Removing elements

fruits.remove("Banana");
```



# Map

```java
Map<String, Integer> studentScores = new HashMap<>();

// Adding Values

studentScores.put("Alice", 95);
studentScores.put("Bob", 88);
studentScores.put("Charlie", 72);

// Retrieving a Value

int score = studentScores.get("Alice");

// Checking for Key Existence

boolean hasBob = studentScores.containsKey("Bob");

// Removing a Key-Value Pair

studentScores.remove("Charlie");
```



## Resources

- [Java Set Documentation](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Set.html)
- [Java Map Documentation](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Map.html)


## HashMap with Objects

When storing objects in a HashMap or HashSet, it is crucial to ensure that the classes from which the objects are created have implemented both a hashCode and an equals method.

```java
public class Student {
    private String firstName;
    private String lastName;
    private int id;

    public Student(String firstName, String lastName, int id) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.id = id;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof Student)) return false;
        Student student = (Student) o;
        return id == student.id && Objects.equals(firstName, student.firstName) && Objects.equals(lastName, student.lastName);
    }
    
    @Override
    public int hashCode() {
        return Objects.hash(firstName, lastName, id);
    }
}
```

```java
Map<String, Student> students = new HashMap<>();
students.put("Alice", new Student("Alice", "Smith", 12345));
students.put("Bob", new Student("Bob", "Jones", 23456));
```
