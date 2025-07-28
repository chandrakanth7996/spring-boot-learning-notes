# 📘 Day 4: Dependency Injection (DI) in Spring Boot

---

## 🧠 What is Dependency Injection?

**Dependency Injection (DI)** is a design pattern where the framework (Spring) provides the required **dependencies (objects)** to a class automatically, rather than the class creating them manually.

It follows the **Inversion of Control (IoC)** principle, where control of object creation is transferred to the Spring container.

---

## 🎯 Why Use DI?

| Without DI                            | With DI (Spring handles)                 |
|--------------------------------------|------------------------------------------|
| `Service service = new Service();`   | `@Autowired Service service;`           |
| You manage object lifecycle          | Spring manages object lifecycle          |
| More tightly coupled classes         | Loosely coupled, testable, scalable code |

---

## 🧩 Common DI Annotations

| Annotation        | Purpose                                  |
|------------------|-------------------------------------------|
| `@Component`      | Marks a class as a Spring bean           |
| `@Service`        | Marks a class that contains business logic |
| `@Repository`     | Marks a data access layer class           |
| `@Controller`     | Marks a class as a web controller         |
| `@RestController` | Shortcut for `@Controller + @ResponseBody` |
| `@Autowired`      | Injects dependencies into a class         |

---

## 💡 Real-World Analogy

Imagine a coffee machine needs a filter.

**Without DI:**
```java
Filter filter = new Filter();
CoffeeMachine machine = new CoffeeMachine(filter);

**With DI:**
@Autowired
Filter filter;
