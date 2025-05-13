# Request and Response Handling in Spring MVC

Spring MVC provides flexible ways to handle HTTP requests and craft responses.

## Accessing Request Parameters

### Using `@RequestParam`

```java
@GetMapping("/greet")
public String greet(@RequestParam String name) {
    return "Hello, " + name;
}
````

### With default value

```java
@GetMapping("/greet")
public String greet(@RequestParam(defaultValue = "Guest") String name) {
    return "Hello, " + name;
}
```

## Path Variables

```java
@GetMapping("/user/{id}")
public String getUser(@PathVariable int id) {
    return "User ID: " + id;
}
```

## Accessing Request Body

### Using `@RequestBody`

```java
@PostMapping("/users")
public String createUser(@RequestBody User user) {
    return "Created user: " + user.getName();
}
```

## Customizing the Response

### Using `@ResponseBody`

```java
@GetMapping("/hello")
@ResponseBody
public String hello() {
    return "Hello World";
}
```

### Returning JSON

```java
@RestController
public class DataController {
    @GetMapping("/api/info")
    public Info getInfo() {
        return new Info("Spring", "MVC");
    }
}
```

> Spring uses Jackson (by default) to convert Java objects to JSON.