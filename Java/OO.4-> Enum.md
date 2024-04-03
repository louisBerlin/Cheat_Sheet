## What are Enums?
Enums, short for "Enumerations", are special data types in Java that represent a set of constant values. These values are often used as enumerations or a list of possibilities. Enums in Java can help make the code more readable and maintainable by defining a fixed set of allowable values.

```java
public class EnumExample {
    public enum Day {
        MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
    }
}
```

```java
public class Person {
    private String name;
    private Gender gender;

    public Person(String name, Gender gender) {
        this.name = name;
        this.gender = gender;
    }

    // Weitere Methoden und Eigenschaften
}
```

```java
public enum Gender {
    MALE("male"),
    FEMALE("female"),
    OTHER("other");

    private final String value;

    Gender(String value) {
        this.value = value;
    }

    public String getValue() {
        return value;
    }
}
```

## How do I use Enums?
Using Enums in Java is simple. You can use them to represent variable-like constants.

```java
EnumExample.Day today = EnumExample.Day.WEDNESDAY;
if (today == EnumExample.Day.WEDNESDAY) {
    System.out.println("Mittwoch ist Mitte der Woche!");
}
```


## Resources
- [Java Optional Documentation](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/Optional.html)


