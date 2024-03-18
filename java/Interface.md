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





##  Can I use polymorphism with interface in Java ?

 Yes, interfaces allow us to define polymorphism in a declarative way, unrelated to implementation
```java
public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle(5.0); // Erstelle ein Circle-Objekt über das Shape-Interface
        Shape square = new Square(4.0); // Erstelle ein Square-Objekt über das Shape-Interface
        
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

