# Class

## basic example
```java
public class C {

    // Variables
     int a;
     int b;
     String c;

     // Constructor
    public C(int a, int b, String c) {
        this.a = a;
        this.b = b;
        this.c = c;
    }

    // Getter Setter ....

    // Methods

    // toString

}
```

## Syntax Constructor   
```java
    public C(int a, int b, String c) {
        this.a = a;
        this.b = b;
        this.c = c;
    }

    public C(int a) {
        this.a = a;
        this.b = 10;
        this.c = "b";
    }

    public C() {
        this.a = 5;
        this.b = 10;
        this.c = "b";
    }
```

## Inheritence

Parent class, superclass or base class :

```java
// Elternklasse -> Superklasse gennant
public class Instrument {
    
    private double price;
    private String color;

    public Instrument(double price, String color) {
        this.price = price;
        this.color = color;
    }

  public void makeNoise(){
        System.out.println("Intrument sounds");
    }

}
```

Child class :

```java
class Violin extends Instrument{

    int numberOfString;

    public Violin(double price, String color, int numberOfString) {
        super(price, color); // super is the way to acces of the parent class
        this.numberOfString = numberOfString;
    }

}
```

## Super

super is a connection way from children to eltern. It is use in the controllor with "super(variable1,variable2,etc)" or to acess to the parent method, fro example super.toString.


If you forgot the constror the compilator will be unhappy, and will ask for it in the children class with a special methode called "super()" :

<img width="884" alt="Screenshot 2024-03-15 at 09 54 00" src="https://github.com/louisBerlin/Java_Cheat_Sheet/assets/80892116/d125e0fc-3a45-4800-8504-fbd832dd8f80">


```java
class Violin extends Instrument{

    int numberOfString;

    public Violin(double price, String color, int numberOfString) {
        super(price, color);
        this.numberOfString = numberOfString;
    }
}
```

The child object will have acces to all the parent method :
 <img width="682" alt="Screenshot 2024-03-15 at 10 09 18" src="https://github.com/louisBerlin/Java_Cheat_Sheet/assets/80892116/95260ef4-8e2a-41f5-8dda-71eed98861e0">

and also in the child class with super.
<img width="731" alt="Screenshot 2024-03-15 at 10 45 53" src="https://github.com/louisBerlin/Java_Cheat_Sheet/assets/80892116/fd2904b6-c288-48c3-a779-eeb231c8137b">



## Override 

It is possible to rewrite and modify the methods/functions of the parent class, this is called "override". 
Example :

```java
   @Override
    public void makeNoise() {
        super.makeNoise(); // -> System.out.println("Intrument sounds");
    }
```


## Polymorphism


## Composition

