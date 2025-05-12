# Common Spring AOP Annotations

Spring provides several annotations to implement aspects using `@Aspect` and `@EnableAspectJAutoProxy`.

## Important AOP Annotations

| Annotation     | Description |
|----------------|-------------|
| `@Aspect`      | Marks a class as an aspect |
| `@EnableAspectJAutoProxy` | Enables Spring AOP support |
| `@Before`      | Advice that runs before the method execution |
| `@After`       | Advice that runs after the method execution (regardless of outcome) |
| `@AfterReturning` | Runs after the method returns a result |
| `@AfterThrowing` | Runs after the method throws an exception |
| `@Around`      | Runs before and after the method execution |
| `@Pointcut`    | Declares reusable pointcut expressions |

## Example Usage

```java
@Aspect
@Component
public class AuditAspect {

    @Pointcut("execution(* com.devportal.service.*.*(..))")
    public void serviceMethods() {}

    @Before("serviceMethods()")
    public void beforeAdvice() {
        System.out.println("Audit: Method called");
    }

    @AfterReturning(pointcut = "serviceMethods()", returning = "result")
    public void afterReturning(Object result) {
        System.out.println("Audit: Returned -> " + result);
    }
}
```

## Enabling AOP in Spring Boot

```java
@Configuration
@EnableAspectJAutoProxy
public class AppConfig {
}
```

## Common Pointcut Expressions

- `execution(* com.example..*(..))` - All methods in the package
- `within(com.example.service..*)` - All methods within a class/package
- `args(String, ..)` - Methods with a String as the first argument

> We can combine multiple pointcuts using &&, ||, and !