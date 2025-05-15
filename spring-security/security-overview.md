# Spring Security Overview

Spring Security is a powerful and customizable authentication and access-control framework for Java applications.

## Core Features

- Authentication & Authorization
- Secure Password Storage (BCrypt)
- URL-based Access Control
- CSRF Protection
- Session Management
- OAuth2 and JWT integration

## Default Behavior

- All endpoints are secured by default.
- A login form is automatically provided if none is configured.
- In-memory user for development/testing
  
```java
@Bean
public UserDetailsService userDetailsService() {
    UserDetails user = User.withDefaultPasswordEncoder()
        .username("user")
        .password("password")
        .roles("USER")
        .build();
    return new InMemoryUserDetailsManager(user);
}
```

## Security Filter Chain

Spring Security uses a chain of filters:

* `UsernamePasswordAuthenticationFilter`
* `BasicAuthenticationFilter`
* `SecurityContextPersistenceFilter`
* `ExceptionTranslationFilter`

> Spring Security is highly extensible and can secure REST APIs, web apps, and microservices.