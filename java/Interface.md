# Java Interfaces
## Example 
```java
public interface Form {
    double calculateArea();   // methode will have to be Override
}

```


```java
public class Circle implements Form {
    private double radius;
    
    // Konstruktor, Getter und Setter
    
    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}


public class Square implements Shape {
    private double side;
    
    // Konstruktor, Getter und Setter
    
    @Override
    public double calculateArea() {
        return side * side;
    }
}

```




## How many classes can you implement in Java ?

There are no restrictions on the number of classes that can be present in one Java program. 

```java
public class Test implements H, H1, H2 {
...
}


 interface H {
...
}

interface H1 {
...
}

interface H2 {
...
}

```

