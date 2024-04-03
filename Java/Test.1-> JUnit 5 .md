## Example of a Test
```java
public static int addition(int a, int b) {
    return a + b;
}
```
```java
@Test
void return15_whenAdditionWith5And10() {
// GIVEN
int a = 5;
int b = 10;
//WHEN
int actual = a + b;
//THEN
int expected = 15;
assertEquals(expected, actual);
}
```
## Resources
- [JUnit](https://junit.org/junit5/docs/current/user-guide/)
- [Test Driven Development](https://www.agilealliance.org/glossary/tdd/)
