# Streams

## Learning Objectives
- [ ] Gain understanding of the basics of Java Streams
- [ ] Learn and apply the different Stream methods
- [ ] Understand and utilize the functional approach of the Stream API

## Introduction

Java Streams allow working with a stream of data.
Each operation on the stream is considered as an operation that manipulates or restructures it.
The Stream API was introduced in Java 1.8 and follows the [Functional Programming](https://github.com/readme/guides/functional-programming-basics) (FP) approach.

```java
List<String> myList = List.of("Apple", "Banana", "Grapes", "Orange", "Mango");

// Beispiel: Filtern und Ausgeben von Elementen, die mit "A" beginnen
myList.stream()
      .filter(fruit -> fruit.startsWith("A"))
      .forEach(System.out::println);

// Beispiel: Mapping und Ausgeben in Großbuchstaben
myList.stream()
      .map(String::toUpperCase)
      .forEach(System.out::println);

// Beispiel: Reduzieren auf ein einzelnes Ergebnis (Anzahl der Buchstaben)
int totalLength = myList.stream()
                        .mapToInt(String::length)
                        .reduce(0, (a, b) -> a + b);

System.out.println("Wortgesamtlänge aller Früchte: " + totalLength);
```

The syntax with double colons `::` is a shortcut for a lambda function that is executed on the respective object from the list.
- `System.out::println` is a shortcut for `fruit -> System.out.println(fruit)`

If the 3rd example still seems a bit cryptic to you:
- `.mapToInt(String::length)` is a shortcut for `.mapToInt(fruit -> fruit.length())` and counts the number of letters for each word
- `.reduce(0, (a, b) -> a + b)` is a shortcut for `.reduce(0, Integer::sum)` and sums all values in the stream

## Stream Methods

A stream is typically started with `.stream()` and terminated with a terminal operation (explanation/examples - see below).
### Filter
- `filter`: Filters elements based on a condition.
- `distinct`: Removes duplicates from the stream.
- `limit`: Limits the number of elements in the stream.

```java
List<Integer> numbers = List.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

List<Integer> evenNumbers = numbers.stream()
                                   .filter(n -> n % 2 == 0)
                                   .collect(Collectors.toList());

System.out.println(evenNumbers); // Ausgabe: [2, 4, 6, 8, 10]
```

### Structural
- `map`: Transforms each element of the stream according to a given function.
- `flatMap`: Transforms each element of the stream and flattens the result.
- `sorted`: Sorts the elements in the stream.

```java
List<String> names = List.of("Alice", "Bob", "Charlie", "David");

List<String> upperCaseNames = names.stream()
                                   .map(String::toUpperCase)
                                   .collect(Collectors.toList());

System.out.println(upperCaseNames); // Ausgabe: ["ALICE", "BOB", "CHARLIE", "DAVID"]

List<String> letters = names.stream()
                            .map(name -> name.split(""))
                            .flatMap(Arrays::stream)
                            .collect(Collectors.toList());

System.out.println(letters); // Ausgabe: ["A", "l", "i", "c", "e", "B", "o", "b", "C", "h", "a", "r", "l", "i", "e", "D", "a", "v", "i", "d"]
```
### Terminator
- `reduce`: Reduces the stream to a single value.
- `forEach`: Performs an action for each element in the stream.
- `collect`: Collects the elements of the stream into a data structure.

```java
List<Integer> numbers = List.of(1, 2, 3, 4, 5);

int sum = numbers.stream()
                .reduce(0, Integer::sum);

System.out.println("Summe: " + sum); // Ausgabe: 15

List<String> fruits = List.of("Apple", "Banana", "Grapes");

String result = fruits.stream()
                     .collect(Collectors.joining(", "));

System.out.println("Früchte: " + result); // Ausgabe: Apple, Banana, Grapes
```

## Resources
- [Java Streams Tutorial](https://www.baeldung.com/java-streams)
- [Oracle Java Documentation - Stream API](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html)
- [Java Stream Cheat Sheet](https://www.jrebel.com/blog/java-streams-cheat-sheet)
