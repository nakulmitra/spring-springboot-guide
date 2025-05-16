# Spring Boot Overview

Spring Boot simplifies the setup, configuration, and deployment of Spring applications. It reduces boilerplate code and offers production-ready features.

## Key Features

- Auto-configuration
- Embedded servers (Tomcat, Jetty)
- Opinionated starter dependencies
- Spring Boot CLI
- Spring Actuator
- Simplified configuration using `application.properties` or `application.yml`

## Example

```java
@SpringBootApplication
public class DemoApplication {
    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}
```

## Embedded Server

Spring Boot comes with an embedded server (default is Tomcat), so no need to deploy WAR files.

> Spring Boot enables rapid application development with minimal configuration.

````

---

### ✅ `spring-boot/starter-dependencies.md`

```markdown
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
````

> 💡 These starters manage transitive dependencies and versioning automatically.

````

---

### ✅ `spring-boot/auto-configuration.md`

```markdown
# Auto Configuration in Spring Boot

Spring Boot auto-configures your application based on the libraries present in the classpath.

## How It Works

- Auto-configuration is triggered via `@EnableAutoConfiguration` (included in `@SpringBootApplication`).
- Spring Boot uses `spring.factories` to load auto-configuration classes.

## Example

If `spring-boot-starter-web` is on the classpath:
- A `DispatcherServlet` is auto-configured
- Embedded Tomcat is started
- `@RestController` and related web annotations become functional

## Conditional Annotations

| Annotation                      | Use |
|----------------------------------|-----|
| `@ConditionalOnClass`           | Applies config if class exists |
| `@ConditionalOnMissingBean`     | Applies config if bean not defined |
| `@ConditionalOnProperty`        | Applies config based on property |

## Custom Auto-Configuration

```java
@Configuration
@ConditionalOnClass(MyService.class)
public class MyAutoConfig {
    @Bean
    public MyService myService() {
        return new MyService();
    }
}
````

> ⚠️ Auto-config can be overridden by defining your own beans.

````

---

### ✅ `spring-boot/application-properties.md`

```markdown
# application.properties in Spring Boot

Spring Boot uses `application.properties` or `application.yml` to configure the application.

## Common Properties

```properties
# Server
server.port=8081

# Datasource
spring.datasource.url=jdbc:postgresql://localhost:5432/mydb
spring.datasource.username=postgres
spring.datasource.password=secret

# JPA
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# Logging
logging.level.org.springframework=INFO
````

## Profiles

```properties
# application-dev.properties
server.port=8082
```

Set the active profile in the main `application.properties`:

```properties
spring.profiles.active=dev
```

## YAML Example

```yaml
server:
  port: 8080

spring:
  datasource:
    url: jdbc:mysql://localhost:3306/test
    username: root
    password: pass
```

> 💡 YAML supports hierarchical configuration and is easier to read for complex configs.

````

---

### ✅ `spring-boot/actuator.md`

```markdown
# Spring Boot Actuator

Spring Boot Actuator provides production-ready endpoints to monitor and manage your application.

## How to Enable

```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
````

## Common Endpoints

| Endpoint            | Description                  |
| ------------------- | ---------------------------- |
| `/actuator/health`  | Application health status    |
| `/actuator/info`    | Custom info                  |
| `/actuator/metrics` | Metrics like memory, threads |
| `/actuator/env`     | Environment properties       |

## Enable/Disable Endpoints

```properties
management.endpoints.web.exposure.include=health,info,metrics
management.endpoint.health.show-details=always
```

## Custom Info

```properties
info.app.name=My App
info.app.version=1.0.0
```

Add `@ConfigurationProperties` or use `@Value` to inject.

---

> 📊 Actuator is useful for integrating with tools like Prometheus, Grafana, etc.

````

---

### ✅ `spring-boot/annotations.md`

```markdown
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
````

Enable with:

```java
@EnableConfigurationProperties(AppConfig.class)
```

---

> 🧠 These annotations make Spring Boot powerful and easy to configure.

```

---

Let me know when you're ready for the final **interview** section or if you'd like a bundled zip version of all these files.
```
