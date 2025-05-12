# Spring AOP Concepts

Spring AOP (Aspect-Oriented Programming) allows you to define cross-cutting concerns - logic that is common to multiple modules - in one place.

## Core AOP Concepts

| Concept    | Description |
|------------|-------------|
| **Aspect** | A module that encapsulates cross-cutting concerns (e.g., logging, security) |
| **Join Point** | A specific point in the program execution (like method execution) |
| **Advice** | Action taken at a join point (e.g., `before`, `after`, `around`) |
| **Pointcut** | A predicate that matches join points |
| **Weaving** | Linking aspects with other application types during runtime or compile time |
| **Proxy** | Spring AOP creates proxies around beans to implement AOP features |

## AOP in Spring

Spring AOP is **proxy-based** and supports only **method-level join points** on **Spring-managed beans**.

### Example Flow

1. Define an aspect (`@Aspect`)
2. Apply advice (`@Before`, `@After`, etc.)
3. Target methods using pointcuts (`execution(...)`, `within(...)`, etc.)

## Example:

```java
@Aspect
@Component
public class LoggingAspect {

    @Before("execution(* com.devportal.service.*.*(..))")
    public void logBefore(JoinPoint joinPoint) {
        System.out.println("Before method: " + joinPoint.getSignature().getName());
    }
}
```

> Spring AOP does not support field-level interception. Use AspectJ for advanced features.

## Use Cases

- Logging
- Security checks
- Performance monitoring
- Transaction management
- Auditing