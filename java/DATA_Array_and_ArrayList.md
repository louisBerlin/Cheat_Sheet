# ArrayList

### Creating and Initializing an ArrayList
```java
List<String> names = new ArrayList<>();

// Adding Elements
names.add("Alice");
names.add("Bob");

// Accessing Elements
names.get(0);

// Removing Elements
names.remove("Alice");

// Removing the x. Element
names.remove(1);

// Adding Element at a Specific Position
names.add(1, "Charlie");

// Getting the Size of the List
names.size();

// Get the index of ("Bob")
name.indexOf(Bob);

System.out.println(name); -> [Alice,Bob]
```

## Interface `List`

When using `ArrayList`, one might initially think it's a good idea to also type variables, parameters, and return values as `ArrayList`:

```java
ArrayList<String> names = new ArrayList<>(); // not recommended!
```

However, this is not a good idea because it locks us into a specific implementation. If we later want to use a different implementation, we would have to modify all the places in the code where we used `ArrayList`. This is very time-consuming and error-prone.

By only specifying an interface in our code, we keep our code flexible and can easily replace the implementation later:

```java
List<Object> items = new ArrayList<>(); // best practice to define it like this once!
List<Object> items = new LinkedList<>(); // then we can simply use it like this later!
```





# Array


```java
// Example: An array of integers with a size of 5
int[] numbers = new int[5];
// or
int[] numbers = {1, 2, 3, 4, 5};

for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```


# The `for-each` Loop
The `for-each` loop is a simplified version of the `for` loop and makes it easier to iterate over arrays. It is used when we want to iterate over all elements in an array without using the index.

```java
int[] numbers = {1, 2, 3, 4, 5};

for (int number : numbers) {
    System.out.println(number);
}
```

The `for-each` loop is particularly useful when we don't need direct access to the index and simply want to access each element in the array.







