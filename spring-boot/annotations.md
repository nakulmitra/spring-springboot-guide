# Spring Boot Annotations

Here are key annotations used in Spring Boot applications:

## Core Annotations

| Annotation             | Description |
|------------------------|-------------|
| `@SpringBootApplication` | Combines `@Configuration`, `@EnableAutoConfiguration`, and `@ComponentScan` |
| `@Configuration`        | Marks a class as a source of bean definitions |
| `@Bean`                | Declares a bean to be managed by Spring |
| `@ComponentScan`       | Scans packages for components |
| `@EnableAutoConfiguration` | Enables auto-configuration |

## Web & REST

| Annotation     | Description |
|----------------|-------------|
| `@RestController` | Combines `@Controller` and `@ResponseBody` |
| `@RequestMapping` | Maps HTTP requests to methods |
| `@GetMapping`, `@PostMapping` | Shortcut annotations |
| `@RequestParam`, `@PathVariable` | Binds query/path parameters |
| `@RequestBody`, `@ResponseBody` | Serializes/deserializes JSON |

## Configuration Properties

```java
@ConfigurationProperties(prefix = "app")
public class AppConfig {
    private String name;
    private int version;
}
```

Enable with:

```java
@EnableConfigurationProperties(AppConfig.class)
```

> These annotations make Spring Boot powerful and easy to configure.
