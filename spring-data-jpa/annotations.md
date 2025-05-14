# Common JPA Annotations

## Entity & Table

| Annotation     | Description |
|----------------|-------------|
| `@Entity`      | Marks a class as a JPA entity |
| `@Table`       | Maps to a specific database table |

## ID & Generation

| Annotation           | Description |
|----------------------|-------------|
| `@Id`                | Marks the primary key |
| `@GeneratedValue`    | Configures ID generation |
| `@SequenceGenerator` | Used with `SEQUENCE` strategy |

## Column Mapping

| Annotation     | Description |
|----------------|-------------|
| `@Column`      | Maps a field to a table column |
| `@Transient`   | Field not persisted |
| `@Lob`         | Large object (CLOB/BLOB) |
| `@Enumerated`  | Stores enums |

## Relationships

| Annotation     | Description |
|----------------|-------------|
| `@OneToOne`    | One-to-one mapping |
| `@OneToMany`   | One-to-many mapping |
| `@ManyToOne`   | Many-to-one mapping |
| `@ManyToMany`  | Many-to-many mapping |
| `@JoinColumn`  | Defines foreign key column |
| `@JoinTable`   | Used in many-to-many for join tables |

## Lifecycle Hooks

| Annotation       | Purpose |
|------------------|---------|
| `@PrePersist`    | Before insert |
| `@PostPersist`   | After insert |
| `@PreUpdate`     | Before update |
| `@PostLoad`      | After entity is loaded |

> Combine annotations with Lombok to reduce boilerplate (`@Data`, `@Builder`, etc.).