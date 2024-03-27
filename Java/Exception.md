# Exceptions
### Checked Exceptions

```java
public void readFile(String filename) throws IOException {
    // Code to read the file
}
```

### Unchecked Exceptions

```java
public void divide(int a, int b) {
    if (b == 0) {
        throw new ArithmeticException("Division by zero is not allowed.");
    }
    // Weitere Logik für die Division
}
```

### try-catch Blocks

Example of a try-catch block:
```java
try {
    // Code, der eine Exception auslösen kann
} catch (SomeException e) {
    // Behandlung der Exception
}
```

```java
try {
    // Code, der eine Exception auslösen kann
} catch (IOException e) {
    // Behandlung von IOException
} catch (NullPointerException e) {
    // Behandlung von NullPointerException
} catch (Exception e) {
    // Fallback-Behandlung für alle anderen Exceptions
}
```

## Testing Exceptions

### fail() or Assertions.fail() is unhappy if he dont have any exception
Using familiar means `try`/`catch` or `assertThrows` :

```java
@Test
void test() {
    try {
        aufrufDerFehlerhaftenMethode();
        fail("Es wurde eine Exception erwartet, aber keine geworfen!");
    } catch (Exception e) {
        // gut: der Fehlerzustand wurde gemeldet
    }
}
```

Alternatively, with `assertThrows` and advanced syntax:

```java
@Test
public void testMyMethod() {
// Aufruf der Methode von der du erwartest, dass sie die Exception auslöst
assertThrows(MyException.class, () -> aufrufDerFehlerhaftenMethode());

}
```

## Further Information

* `try` / `finally` defines actions that should always be executed<br/>(regardless of whether an error state occurs or not)
  * `try` defines the code to be executed
  * `finally` defines the code that should always be executed (come what may)
* It is also possible to define custom exception classes
  * usually with `extends Exception` or `extends RuntimeException`
  * These exceptions can also have their own fields and methods / constructors
* There is an alternative syntax for resources ("try with resources")
  * For example, to ensure that every file that is opened is also closed
  * `try (FileInputStream fis = new FileInputStream("file.txt")) { /*...*/ }`
 
    ## Resources
- [Java Tutorials on Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/)
- [Java Doc for the `Exception` class](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Exception.html)
- [Java Doc for the `RuntimeException` class](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/RuntimeException.html)
