
# 🌱 Inversion of Control (IoC) in Spring Boot

## 🧠 What is Inversion of Control (IoC)?

**Inversion of Control (IoC)** is a design principle where the control over object creation and dependency management is shifted from the program itself to a framework or container. In Spring Boot, this control is managed by the **Spring IoC Container**, which creates and manages the lifecycle of application components (also known as beans).

This principle is key to making applications **loosely coupled**, easier to maintain, and easier to test.

---

## 🧩 IoC vs Traditional Programming

### 🛠️ Traditional Approach:
```java
Service service = new Service(); // Developer controls object creation
````

### 🌿 IoC with Spring Boot:

```java
@Component
public class Service {
  ...
}

@Autowired
private Service service; // Spring handles creation and injection
```

Here, Spring controls the creation and wiring of objects, not you — that's the **Inversion of Control**.

---

## ⚙️ IoC Container in Spring

Spring provides two main containers:

* `BeanFactory` (basic container)
* `ApplicationContext` (advanced, widely used)

In Spring Boot, `ApplicationContext` is used automatically.

Example:

```java
ApplicationContext context = 
  new AnnotationConfigApplicationContext(AppConfig.class);
MyBean bean = context.getBean(MyBean.class);
```

But with Spring Boot, you rarely write this manually — it's all auto-configured.

---

## 🧪 Example: IoC in Action

### ✅ Step 1: Define a Service Bean

```java
import org.springframework.stereotype.Service;

@Service
public class MyService {
    public String serve() {
        return "Service is working!";
    }
}
```

### ✅ Step 2: Inject into a Controller

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class MyController {

    @Autowired
    private MyService myService;

    @GetMapping("/test")
    public String test() {
        return myService.serve();
    }
}
```

Spring Boot automatically:

* Creates `MyService` bean
* Detects and injects it into `MyController` where required

---

## 🏷️ Important Spring Annotations in IoC

| Annotation        | Purpose                                         |
| ----------------- | ----------------------------------------------- |
| `@Component`      | Marks a generic Spring-managed bean             |
| `@Service`        | Marks a service layer component                 |
| `@Repository`     | Marks a DAO component and handles DB exceptions |
| `@Controller`     | Marks a web controller (MVC pattern)            |
| `@RestController` | Same as `@Controller` but returns data as JSON  |
| `@Autowired`      | Injects a required bean automatically           |

---

## 🧠 Key Points to Remember

* **IoC** is a fundamental concept in Spring Boot.
* It allows **Spring to control object creation and wiring**, reducing coupling.
* Works closely with **Dependency Injection** (which you learned earlier).
* Relies on Spring annotations and scanning to find and manage beans.

---

## ✅ Summary

> Inversion of Control helps create more maintainable and modular applications. You simply define components, and Spring Boot manages them for you — effortlessly and transparently.

---

```
```
