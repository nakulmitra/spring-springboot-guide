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
```

> Auto-config can be overridden by defining your own beans.