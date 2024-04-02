
## Using the Spring Initializr in IntelliJ

The Spring Initializr is a web-based tool that allows us to quickly and easily set up a new Spring or Spring Boot project. Here are the steps to do this in IntelliJ:

1. Open IntelliJ and select "File" > "New" > "Project...".
2. Choose "Spring Initializr" from the list of project templates.
3. Provide the required information such as group name, artifact ID, and the desired Spring Boot version.
4. Select the necessary dependencies you want to use in the project, such as "Spring Web" for a web application.
5. Click "Finish" to create the new project.

## The Application Class

```java
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class MyApp {
    public static void main(String[] args) {
        SpringApplication.run(MyApp.class, args);
    }
}
```

## Controller

```java
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api")
public class MyController {

    @GetMapping("/hello")
    public String sayHello() {
        return "Hello, World!";
    }

    @PostMapping("/greet")
    public String greet(@RequestParam String name) {
        return "Hello, " + name + "!";
    }

    @DeleteMapping("/remove/{id}")
    public String removeItem(@PathVariable int id) {
        // Code zum Löschen eines Elements mit der ID
        return "Item with ID " + id + " removed successfully.";
    }
}
```


- `@RestController`: Indicates that the class is a controller capable of handling HTTP requests and combines the `@Controller` and `@ResponseBody` annotations to facilitate returning data as HTTP responses.
- `@RequestMapping`: Assigns a URL path to a method or controller - in this case, `/api` is considered as the prefix for the class endpoints.
- `@GetMapping`/ `@PostMapping`/ `@DeleteMapping`: Assigns an HTTP endpoint to a method that responds to the corresponding HTTP verb.
- `@PathVariable`: Binds a variable from the URL path to a method.

## Path Variables

```java
@DeleteMapping("/remove/{id}")
public String removeItem(@PathVariable int id) {
    // Code zum Löschen eines Elements mit der ID
    return "Item with ID " + id + " removed successfully.";
}
```


