# Entity Mapping in JPA

Entities represent tables in our database. Use JPA annotations to map class fields to table columns.

## Basic Entity Setup

```java
@Entity
@Table(name = "users")
public class User {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false)
    private String name;

    private String email;
}
````

## Primary Key Generation

| Strategy   | Description                  |
| ---------- | ---------------------------- |
| `IDENTITY` | Auto-increment (DB-specific) |
| `SEQUENCE` | Uses database sequences      |
| `AUTO`     | Hibernate chooses strategy   |
| `TABLE`    | Table-based sequence         |

## Relationships

### One-to-Many

```java
@OneToMany(mappedBy = "user")
private List<Order> orders;
```

### Many-to-One

```java
@ManyToOne
@JoinColumn(name = "user_id")
private User user;
```

### One-to-One

```java
@OneToOne
@JoinColumn(name = "profile_id")
private Profile profile;
```

### Many-to-Many

```java
@ManyToMany
@JoinTable(name = "student_course",
    joinColumns = @JoinColumn(name = "student_id"),
    inverseJoinColumns = @JoinColumn(name = "course_id"))
private Set<Course> courses;
```

> Always handle lazy loading carefully to avoid `LazyInitializationException`.