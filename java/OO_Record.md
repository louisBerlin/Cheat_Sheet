### ** All variable in a Record are Immutability ("final") **
### ** Constructor, getters, equals, hashCode, and toString are automatically generated **
### ** It can not get "Inheritence"                        **
### ** Come with java 14                                   **


## Creating and Using a Record

Creating a Record is simple and requires less boilerplate code compared to conventional classes.

```java
public record Person(String firstName, String lastName, int age) {
    // Constructor, getters, equals, hashCode, and toString are automatically generated
}
```

Records can be used just like regular classes:

```java
Person person = new Person("John", "Doe", 30);
String fullName = person.firstName() + " " + person.lastName();

// Records sind standardmäßig immutabel
// person.age = 31; // Dies führt zu einem Kompilierungsfehler
```
