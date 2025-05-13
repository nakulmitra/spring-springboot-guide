# Dispatcher Servlet in Spring MVC

The `DispatcherServlet` is the **central controller** in Spring MVC. It routes incoming HTTP requests to the appropriate controller and handles the complete request processing lifecycle.

## Responsibilities

- Receives HTTP requests
- Delegates to appropriate handler (controller)
- Resolves views
- Returns HTTP responses

## Request Flow

1. Client sends request to DispatcherServlet.
2. DispatcherServlet consults `HandlerMapping` to find the correct controller.
3. Controller processes the request and returns a `ModelAndView`.
4. DispatcherServlet uses `ViewResolver` to render the view.
5. Response is returned to the client.

## Configuration (Java-based)

```java
@Configuration
@EnableWebMvc
@ComponentScan(basePackages = "com.devportal")
public class WebConfig implements WebMvcConfigurer {

    @Bean
    public InternalResourceViewResolver viewResolver() {
        InternalResourceViewResolver resolver = new InternalResourceViewResolver();
        resolver.setPrefix("/WEB-INF/views/");
        resolver.setSuffix(".jsp");
        return resolver;
    }
}
````

> In Spring Boot, `DispatcherServlet` is auto-configured.