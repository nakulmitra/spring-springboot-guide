# Spring vs Spring Boot

Understanding the difference between Spring and Spring Boot is fundamental for interviews.

## 1. Definition

| Aspect        | Spring                                      | Spring Boot                                             |
|---------------|---------------------------------------------|----------------------------------------------------------|
| Core Idea     | Framework for building Java applications    | Extension of Spring with pre-configured defaults         |
| Purpose       | Provides flexibility and full control       | Simplifies setup with auto-configuration and starters    |

## 2. Setup

| Spring                      | Spring Boot                         |
|----------------------------|--------------------------------------|
| Manual XML or Java config  | Auto-configuration                   |
| Needs external server      | Embedded Tomcat/Jetty/Undertow       |
| Complex dependency setup   | Uses starter dependencies            |

## 3. Configuration

| Spring                                 | Spring Boot                               |
|----------------------------------------|--------------------------------------------|
| Verbose configuration (XML or Java)    | Convention over configuration              |
| Requires boilerplate code              | Reduces boilerplate                        |

## 4. Deployment

| Spring           | Spring Boot                     |
|------------------|----------------------------------|
| Requires WAR     | Generates standalone JAR        |
| Needs external server | No need to deploy separately |

## 5. Key Features Comparison

| Feature                     | Spring             | Spring Boot          |
|-----------------------------|--------------------|----------------------|
| Dependency Injection        | Present            | Present              |
| Web MVC / REST              | Present            | Present              |
| Auto Configuration          | Absent             | Present              |
| Embedded Server             | Absent             | Present              |
| Starter Dependencies        | Absent             | Present              |
| Spring Actuator             | Absent (manual)    | Present (built-in)   |


> Spring Boot is **opinionated and production-ready**, while Spring Framework offers **fine-grained control**.