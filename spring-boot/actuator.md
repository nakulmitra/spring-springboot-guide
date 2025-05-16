# Spring Boot Actuator

Spring Boot Actuator provides production-ready endpoints to monitor and manage your application.

## How to Enable

```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

## Common Endpoints

| Endpoint            | Description                  |
| ------------------- | ---------------------------- |
| `/actuator/health`  | Application health status    |
| `/actuator/info`    | Custom info                  |
| `/actuator/metrics` | Metrics like memory, threads |
| `/actuator/env`     | Environment properties       |

## Enable/Disable Endpoints

```properties
management.endpoints.web.exposure.include=health,info,metrics
management.endpoint.health.show-details=always
```

## Custom Info

```properties
info.app.name=My App
info.app.version=1.0.0
```

Add `@ConfigurationProperties` or use `@Value` to inject.

> Actuator is useful for integrating with tools like Prometheus, Grafana, etc.