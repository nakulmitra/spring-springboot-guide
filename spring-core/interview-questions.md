# Spring Core Interview Questions

Here are some common Spring Core questions often asked in interviews:

### 1. What is Inversion of Control (IoC)?
IoC is a design principle where object creation and dependency management are delegated to a container like Spring.

### 2. What is the difference between BeanFactory and ApplicationContext?
- `BeanFactory` is a basic container with lazy loading.
- `ApplicationContext` is a more advanced container supporting AOP, events, and internationalization.

### 3. What are the types of Dependency Injection in Spring?
- Constructor Injection
- Setter Injection
- Field Injection (not recommended)

### 4. What is the default scope of a Spring bean?
The default scope is `singleton` - only one instance is created per Spring container.

### 5. When would you use `@Lazy`?
Use `@Lazy` when you want to delay bean initialization until it is actually needed.

### 6. What are `@PostConstruct` and `@PreDestroy` used for?
They are lifecycle annotations to define initialization and cleanup logic.

### 7. Can you explain the Spring bean lifecycle?
Instantiation -> Dependency Injection -> Initialization (`@PostConstruct`) -> Destruction (`@PreDestroy`)

### 8. What is the difference between `@Component` and `@Bean`?
- `@Component` is used at the class level for automatic component scanning.
- `@Bean` is used inside a `@Configuration` class to define beans manually.

> Prepare with practical examples and dive deep into `ApplicationContext`, custom scopes, and bean wiring for advanced rounds.