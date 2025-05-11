# Spring Bean Lifecycle

The Spring container manages the complete lifecycle of a bean, from instantiation to destruction.

## Lifecycle Steps

1. Bean Instantiation
2. Populate Dependencies
3. `setBeanName()`, `setBeanFactory()` callbacks (optional)
4. `@PostConstruct` / `afterPropertiesSet()`
5. Bean is ready to use
6. Container shutdown
7. `@PreDestroy` / `destroy()` called

## Key Interfaces

- `InitializingBean`: Defines `afterPropertiesSet()`
- `DisposableBean`: Defines `destroy()`

## Annotations

- `@PostConstruct`: Executes after bean initialization
- `@PreDestroy`: Executes before bean destruction

### Example:

```java
@Component
public class MyBean {

    @PostConstruct
    public void init() {
        System.out.println("Bean initialized");
    }

    @PreDestroy
    public void cleanup() {
        System.out.println("Bean destroyed");
    }
}
````

> Prefer annotations over interfaces for cleaner and more decoupled code.