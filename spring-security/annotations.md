# Spring Security Annotations

Spring Security provides annotations to apply security constraints declaratively.

## @EnableWebSecurity

Enables Spring Security in a Java config class.

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig { ... }
```

## @EnableMethodSecurity (Spring Boot 3+)

Enables method-level security (replaces `@EnableGlobalMethodSecurity`).

```java
@EnableMethodSecurity
public class SecurityConfig { ... }
```

## @Secured

Restricts access to a method based on roles.

```java
@Secured("ROLE_ADMIN")
public void deleteUser(Long id) { ... }
```

## @PreAuthorize / @PostAuthorize

Supports SpEL expressions for fine-grained access control.

```java
@PreAuthorize("hasRole('ADMIN')")
public void updateUser(User user) { ... }

@PostAuthorize("returnObject.owner == authentication.name")
public Document getDocument(Long id) { ... }
```

## @WithMockUser (For Testing)

Used in tests to simulate a logged-in user.

```java
@WithMockUser(username = "admin", roles = {"ADMIN"})
@Test
void testAdminAccess() { ... }
```

> Prefer `@PreAuthorize` for complex logic and `@Secured` for simple role checks.