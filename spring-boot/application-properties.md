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
```

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

> YAML supports hierarchical configuration and is easier to read for complex configs.