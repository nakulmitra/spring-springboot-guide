# Starter Dependencies in Spring Boot

Spring Boot provides pre-configured "starter" dependencies to simplify Maven/Gradle builds.

## Common Starters

| Starter                  | Purpose                          |
|--------------------------|----------------------------------|
| `spring-boot-starter`    | Core starter for basic setup     |
| `spring-boot-starter-web`| Web, REST, Tomcat                |
| `spring-boot-starter-data-jpa` | JPA & Hibernate       |
| `spring-boot-starter-security` | Spring Security         |
| `spring-boot-starter-test` | Testing libraries like JUnit, Mockito |
| `spring-boot-starter-actuator` | Monitoring & management |

## Example (Maven)

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

> These starters manage transitive dependencies and versioning automatically.