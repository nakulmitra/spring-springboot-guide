# Inversion of Control (IoC) and Dependency Injection (DI)

## Inversion of Control (IoC)

IoC is a design principle where the control of object creation is transferred from the program itself to the container (Spring).

Spring provides two types of IoC containers:
- `BeanFactory`: Basic container, lazy initialization, lightweight.
- `ApplicationContext`: Full-featured container with support for AOP, internationalization, and more.

## Dependency Injection (DI)

DI is the process of injecting dependent objects into a class from outside rather than creating them inside.

### Types of DI:

1. **Constructor Injection**
2. **Setter Injection**
3. **Field Injection** *(Not recommended)*

### Example: Constructor Injection

```java
@Component
public class UserService {
    private final UserRepository repository;

    @Autowired
    public UserService(UserRepository repository) {
        this.repository = repository;
    }
}
```

> Constructor injection is preferred for mandatory dependencies and immutability.

### Field Injection (Not recommended)

```java
@Component
public class OrderService {
    private OrderRepository repository;

    @Autowired
    public void setRepository(OrderRepository repository) {
        this.repository = repository;
    }
}
```

### Example: Constructor Injection

```java
@Component
public class OrderService {
    @Autowired
    private OrderRepository repository;
}
```

> Field injection is not ideal for unit testing and immutability.