# JPA Repositories in Spring Data

Spring Data JPA simplifies the implementation of data access layers by providing repository interfaces out of the box.

## Key Interfaces

| Interface            | Description |
|----------------------|-------------|
| `CrudRepository`     | Basic CRUD operations |
| `PagingAndSortingRepository` | CRUD + pagination and sorting |
| `JpaRepository`      | Extends both, adds JPA-specific features |

## Example

```java
public interface UserRepository extends JpaRepository<User, Long> {
}
````

> Spring Data will automatically generate the implementation at runtime.

## Custom Repository Example

```java
public interface ProductRepository extends JpaRepository<Product, Integer> {
    List<Product> findByCategory(String category);
}
```

## Optional Methods

```java
Optional<User> findById(Long id);
boolean existsByEmail(String email);
void deleteByUsername(String username);
```

## Pagination and Sorting

```java
Page<User> findAll(Pageable pageable);
List<User> findAll(Sort.by("name"));
```

> We can combine method names and query annotations for advanced use cases.