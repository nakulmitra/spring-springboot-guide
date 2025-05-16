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