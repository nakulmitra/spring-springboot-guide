# Controllers in Spring MVC

Controllers handle client requests and return responses. They are annotated with `@Controller` or `@RestController`.

## `@Controller`

Used for handling web pages (returns views).

```java
@Controller
public class HomeController {
    @GetMapping("/")
    public String home() {
        return "home"; 
    }
}
````

## `@RestController`

Combines `@Controller` and `@ResponseBody` for REST APIs.

```java
@RestController
public class ApiController {
    @GetMapping("/api/data")
    public Data getData() {
        return new Data("Dev Portal", 2025);
    }
}
```

## Request Mapping Methods

| Annotation        | HTTP Method |
| ----------------- | ----------- |
| `@GetMapping`     | GET         |
| `@PostMapping`    | POST        |
| `@PutMapping`     | PUT         |
| `@DeleteMapping`  | DELETE      |
| `@RequestMapping` | Custom/Any  |

> Always use specific mappings like `@GetMapping` for REST APIs.