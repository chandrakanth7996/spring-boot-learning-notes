# 📘 Day 5: Building a Basic CRUD API

---

## 🧠 CRUD Operations

| Action   | HTTP Method | Endpoint           |
|----------|-------------|--------------------|
| Create   | POST        | /students          |
| Read     | GET         | /students          |
| Update   | PUT         | (To be implemented)|
| Delete   | DELETE      | (To be implemented)|

---

## ✅ Endpoints Created

- `GET /students` — Get list of students
- `POST /students` — Add new student

---

## 🧩 Components

### 📦 Model: `Student.java`

```java
public class Student {
    private int id;
    private String name;
    private String course;
    // Getters & Setters
}

---

### 📦 Service: `StudentService.java`

```java
@Service
public class StudentService {
    List<Student> students = new ArrayList<>();
    public List<Student> getAllStudents() { return students; }
    public void addStudent(Student s) { students.add(s); }
}

---

### 📦 Contoller: `StudentContoller.java`

```java
@RestController
@RequestMapping("/students")
public class StudentController {
    @Autowired
    StudentService studentService;

    @GetMapping
    public List<Student> getStudents() {
        return studentService.getAllStudents();
    }

    @PostMapping
    public String addStudent(@RequestBody Student student) {
        studentService.addStudent(student);
        return "Student added successfully!";
    }
}
