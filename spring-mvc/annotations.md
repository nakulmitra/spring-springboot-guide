# Common Annotations in Spring MVC

Spring MVC provides several annotations for handling web requests.

## Controller Annotations

| Annotation        | Description |
|-------------------|-------------|
| `@Controller`     | Marks a class as a web controller |
| `@RestController` | Combines `@Controller` and `@ResponseBody` for REST APIs |

## Request Mapping Annotations

| Annotation        | Description |
|-------------------|-------------|
| `@RequestMapping` | Maps any HTTP method |
| `@GetMapping`     | Maps GET requests |
| `@PostMapping`    | Maps POST requests |
| `@PutMapping`     | Maps PUT requests |
| `@DeleteMapping`  | Maps DELETE requests |

## Parameter Annotations

| Annotation        | Purpose |
|-------------------|---------|
| `@RequestParam`   | To bind query parameters |
| `@PathVariable`   | To bind URI template variables |
| `@RequestBody`    | To bind request body (usually JSON) |
| `@RequestHeader`  | To read HTTP headers |
| `@ModelAttribute` | To bind form data to model objects |

## Response Annotations

| Annotation        | Purpose |
|-------------------|---------|
| `@ResponseBody`   | Returns response as JSON or plain text |
| `@ResponseStatus` | Sets custom HTTP status codes |

## Example

```java
@RestController
@RequestMapping("/api")
public class SampleController {

    @GetMapping("/user/{id}")
    public User getUser(@PathVariable int id) {
        return new User(id, "Dev Portal");
    }
}
````

> Use `@RestController` for APIs, `@Controller` for views.