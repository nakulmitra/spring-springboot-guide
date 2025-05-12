# Spring AOP Interview Questions

A list of frequently asked Spring AOP interview questions and concise answers.

### 1. What is AOP in Spring?
AOP (Aspect-Oriented Programming) allows you to modularize cross-cutting concerns such as logging, security, or transaction management by separating them from the business logic.

### 2. How does Spring AOP work under the hood?
Spring AOP uses proxy-based weaving. It creates proxies for beans either using JDK dynamic proxies (for interfaces) or CGLIB (for classes).

### 3. What are cross-cutting concerns?
These are functionalities that affect multiple parts of an application, like logging, security, auditing, etc., and are best handled separately.

### 4. What is the difference between Advice and Aspect?

- **Advice**: The action taken (before, after, etc.)
- **Aspect**: A class that contains multiple advices and pointcuts

### 5. What are Join Points and Pointcuts?

- **Join Point**: A point during execution (like a method call)
- **Pointcut**: A condition that matches join points

### 6. What is `@Pointcut` used for?
It defines reusable expressions for targeting join points, which can be reused in multiple advices.

### 7. What are the core concepts in AOP?
- Aspect
- Join Point
- Advice
- Pointcut
- Weaving

### 8. What are the types of Advice in Spring AOP?

- `@Before`
- `@After`
- `@AfterReturning`
- `@AfterThrowing`
- `@Around`

### 9. What is the difference between `@Before`, `@After`, `@Around` advice?
- `@Before`: Runs before the target method.
- `@After`: Runs after method execution (regardless of result).
- `@Around`: Can control method execution (before, after, and even suppress it).

### 10. What is the difference between `@Around` and other advices?

`@Around` gives you complete control before and after the method execution. You can even prevent the method from executing.

### 11. What is weaving in AOP?

Weaving is the process of linking aspects to the target object. Spring performs runtime weaving using proxies.

### 12. Can AOP be applied to private methods?

No. Spring AOP is proxy-based and works only on **public methods** of Spring-managed beans.

### 13. What is the difference between Spring AOP and AspectJ?

| Spring AOP          | AspectJ                    |
|---------------------|----------------------------|
| Proxy-based         | Bytecode weaving           |
| Runtime only        | Compile-time, load-time, runtime |
| Method-level only   | Field, constructor, etc.   |

### 14. What are the limitations of Spring AOP?
- It supports only **method-level** join points.
- Works only with **Spring-managed beans**.
- Doesn't support field or constructor-level interception (unlike AspectJ).


> Prepare examples and common pointcut expressions (`execution()`, `within()`) for deeper discussions.