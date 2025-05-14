# Query Methods in Spring Data JPA

Spring Data JPA can automatically generate queries from method names.

## Common Keywords

| Keyword       | Example                        |
|---------------|--------------------------------|
| `findBy`      | `findByUsername(String name)`  |
| `and`, `or`   | `findByUsernameAndAge()`       |
| `Between`     | `findByAgeBetween(int, int)`   |
| `LessThan`    | `findBySalaryLessThan()`       |
| `Like`        | `findByNameLike()`             |
| `In`          | `findByRoleIn(List<Role>)`     |
| `OrderBy`     | `findByAgeOrderByNameDesc()`   |

## Example Queries

```java
List<Employee> findByDeptAndSalaryGreaterThan(String dept, double salary);
List<User> findByEmailLike(String email);
List<Order> findByStatusIn(List<String> statusList);
````

## Custom Queries Using `@Query`

```java
@Query("SELECT u FROM User u WHERE u.email = ?1")
User findByEmail(String email);

@Query("SELECT p FROM Product p WHERE p.price > :price")
List<Product> findExpensive(@Param("price") double price);
```

## Native Queries

```java
@Query(value = "SELECT * FROM users WHERE active = true", nativeQuery = true)
List<User> findActiveUsers();
```

> Use `@Modifying` for update/delete operations with `@Query`.