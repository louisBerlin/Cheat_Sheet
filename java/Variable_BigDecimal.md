## Introduction to BigDecimal
BigDecimal is a class in Java that allows for precise calculations with decimal numbers. Unlike primitive data types like `double` or `float`, BigDecimal offers a nearly unlimited number of decimal places, which is particularly important when accuracy and rounding are required in calculations.
## Example :

```java
BigDecimal number1 = new BigDecimal("123.456");

//Another way is to use primitive data types:

int intValue = 42;
BigDecimal number2 = BigDecimal.valueOf(intValue);
```


```java
// BigDecimal supports common mathematical operations: addition, subtraction, multiplication, and division.

BigDecimal num1 = new BigDecimal("10.25");
BigDecimal num2 = new BigDecimal("3.75");

BigDecimal sum = num1.add(num2); // Addition
BigDecimal difference = num1.subtract(num2); // Subtraktion
BigDecimal product = num1.multiply(num2); // Multiplikation
BigDecimal quotient = num1.divide(num2); // Division
```


```java
// An important aspect of BigDecimal is that the objects are immutable. This means that each mathematical operation returns a new instance of BigDecimal instead of modifying the original object.

BigDecimal original = new BigDecimal("5");
BigDecimal multiplied = original.multiply(new BigDecimal("2"));

System.out.println(original); // Output: 5
System.out.println(multiplied); // Output: 10
```


```java
// The rounding behavior of BigDecimal can be defined by using the `setScale()` method or by using the `RoundingMode`.

BigDecimal num = new BigDecimal("7.3462");
BigDecimal rounded = num.setScale(2, RoundingMode.HALF_UP);

System.out.println(rounded); // Output: 7.35
```

## Resources

- [Java BigDecimal Documentation](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/math/BigDecimal.html)
