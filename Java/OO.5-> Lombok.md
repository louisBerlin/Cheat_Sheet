# Lombok

## Maven pom.xml
```xml
<dependencies>
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <version>1.18.30</version>
        <scope>compile</scope>
    </dependency>
</dependencies>
```
## `@RequiredArgsConstructor`

 Generates a constructor for a class that accepts all final fields of the class as parameters. 
 
 ```java
import lombok.RequiredArgsConstructor;

@RequiredArgsConstructor
public class Person {
    private final String firstName;
    private final String lastName;
}
```
## `@With`

The `@With` annotation generates a method that returns a copy of the instance with one or more modified fields. 

```java
import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.With;

@Data
@AllArgsConstructor
public class Address {
    private String street;
    private String city;

    @With
    private String zipCode;
}
```

## `@Builder`

The `@Builder` annotation generates a builder for the class that provides a readable and chainable syntax for creating objects.

```java
import lombok.Builder;

@Builder
public class Book {
    private String title;
    private String author;
    private int pageCount;
}
```

## `@Data`

The `@Data` annotation generates getters, setters, `equals`, `hashCode`, and `toString` methods for the annotated class.

```java
import lombok.Data;

@Data
public class Product {
    private String name;
    private double price;
}
```

## Resources

- Official Lombok documentation: [Project Lombok](https://projectlombok.org/)
- Lombok tutorial: [Getting Started with Lombok](https://www.baeldung.com/intro-to-project-lombok)
