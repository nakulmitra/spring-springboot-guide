# Spring Bean Scopes

Spring manages objects using **bean scopes**, which define the lifecycle and visibility of beans within the application context.

## 1. Singleton (Default)

- **Scope**: One shared instance per Spring container
- **Use Case**: Stateless services
- **Declaration** (optional):

```java
@Scope("singleton")
````

## 2. Prototype

* **Scope**: New instance every time bean is requested
* **Use Case**: Stateful beans
* **Declaration**:

```java
@Scope("prototype")
```

> Spring does not manage full lifecycle of prototype beans (e.g., `@PreDestroy` won't work).

## 3. Request (Web Applications)

* **Scope**: One instance per HTTP request
* **Use Case**: Web request-specific data
* **Declaration**:

```java
@Scope(value = WebApplicationContext.SCOPE_REQUEST)
```

## 4. Session (Web Applications)

* **Scope**: One instance per HTTP session
* **Use Case**: User session data
* **Declaration**:

```java
@Scope(value = WebApplicationContext.SCOPE_SESSION)
```

## 5. Application

* **Scope**: One instance per ServletContext
* **Use Case**: Application-wide data
* **Declaration**:

```java
@Scope(value = WebApplicationContext.SCOPE_APPLICATION)
```

## 6. Websocket

* **Scope**: One instance per WebSocket
* **Use Case**: WebSocket-based apps
* **Declaration**:

```java
@Scope(value = "websocket")
```

## Summary Table

| Scope       | Description                   | Use Case              |
| ----------- | ----------------------------- | --------------------- |
| singleton   | One shared instance (default) | Stateless services    |
| prototype   | New instance per request      | Custom stateful beans |
| request     | Per HTTP request              | Web layer beans       |
| session     | Per HTTP session              | User-specific storage |
| application | Per ServletContext            | Application config    |
| websocket   | Per WebSocket session         | Real-time apps        |

> Use the right scope to avoid memory leaks and unexpected behaviors.