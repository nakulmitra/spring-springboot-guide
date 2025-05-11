# Spring & Spring Boot Guide

A comprehensive guide to Spring and Spring Boot for learning and interview preparation.

## 📂 Contents
- Spring Core
- Spring AOP
- Spring MVC
- Spring Data JPA
- Spring Security
- Spring Boot
- Interview Questions

spring-springboot-guide/
│
├── README.md
├── spring-core/
│   ├── overview.md
│   ├── ioc-di.md
│   ├── bean-lifecycle.md
│   ├── annotations.md
│   └── interview-questions.md
│
├── spring-aop/
│   ├── aop-concepts.md
│   ├── annotations.md
│   └── interview-questions.md
│
├── spring-mvc/
│   ├── dispatcher-servlet.md
│   ├── controller.md
│   ├── request-response.md
│   └── annotations.md
│
├── spring-data-jpa/
│   ├── jpa-repositories.md
│   ├── query-methods.md
│   ├── entity-mapping.md
│   └── annotations.md
│
├── spring-security/
│   ├── security-overview.md
│   ├── custom-auth.md
│   └── annotations.md
│
├── spring-boot/
│   ├── overview.md
│   ├── starter-dependencies.md
│   ├── auto-configuration.md
│   ├── application-properties.md
│   ├── actuator.md
│   └── annotations.md
│
└── interview/
    ├── spring-vs-springboot.md
    ├── common-annotations.md
    ├── bean-scopes.md
    └── top-50-questions.md


## Key Topics to Include

### 1. **Spring Core**

* IOC Container, ApplicationContext, BeanFactory
* Dependency Injection (constructor, setter, field)
* Bean lifecycle (`@PostConstruct`, `@PreDestroy`, etc.)
* Common annotations: `@Component`, `@Configuration`, `@Bean`, `@Scope`, `@Lazy`

### 2. **Spring AOP**

* Join points, pointcuts, advices, aspects
* Annotations: `@Aspect`, `@Before`, `@After`, `@Around`, `@AfterReturning`, `@AfterThrowing`

### 3. **Spring MVC**

* DispatcherServlet flow
* `@Controller`, `@RestController`, `@RequestMapping`, `@GetMapping`, `@PostMapping`
* Exception handling: `@ControllerAdvice`, `@ExceptionHandler`

### 4. **Spring Data JPA**

* Repositories: `CrudRepository`, `JpaRepository`, `PagingAndSortingRepository`
* Entity relationships: `@OneToMany`, `@ManyToOne`, `@JoinColumn`
* Query creation and custom JPQL/native queries

### 5. **Spring Security**

* Basic auth, JWT integration
* CSRF, CORS, roles & permissions
* Annotations: `@EnableWebSecurity`, `@PreAuthorize`, `@Secured`

### 6. **Spring Boot**

* `@SpringBootApplication`, `@EnableAutoConfiguration`, `@ConfigurationProperties`
* Externalized configuration with `application.properties` or `application.yml`
* Actuator endpoints
* Embedded server and starter dependencies

### 7. **Interview Prep**

* Differences (Spring vs Spring Boot, IOC vs DI)
* Top annotations & when to use
* Bean scopes (`singleton`, `prototype`, etc.)
* Common performance and best practice questions