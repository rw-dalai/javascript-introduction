# Java to C# Translation Exercise

## 1. Java Classes to Translate

### Person Class (Beginner Level)

Translate the following Java class into **worst** practice and **best** practice C#.

```java
/**
 * A simple Person class demonstrating basic OOP concepts
 */
public class Person {

    // Fields --------------------------------------------------
    private String firstName;
    private String lastName;
    private int age;

    // Ctor --------------------------------------------------
    public Person() {
        this.firstName = "";
        this.lastName = "";
        this.age = 0;
    }
    
    public Person(String firstName, String lastName, int age) {
        setFirstName(firstName);
        setLastName(lastName);
        setAge(age);
    }

    // Getter --------------------------------------------------
    public String getFirstName() {
        return firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public int getAge() {
        return age;
    }

    // Setter --------------------------------------------------
    public void setFirstName(String firstName) {
        this.firstName = firstName != null ? firstName.trim() : "";
    }

    public void setLastName(String lastName) {
        this.lastName = lastName != null ? lastName.trim() : "";
    }

    public void setAge(int age) {
        if (age < 0 || age > 100) {
            throw new IllegalArgumentException("Age must be between 0 and 100");
        }
        this.age = age;
    }
    
    // Methods ----------------------------------------
    public String getFullName() {
        return firstName + " " + lastName;
    }

    public boolean isAdult() {
        return age >= 18;
    }

    // toString --------------------------------------------------
    @Override
    public String toString() {
        return String.format("Person{name='%s', age=%d}", getFullName(), age);
    }
}
```

## 2. Conceptual Questions

Answer these questions to deepen your understanding of C# concepts when translating from Java:

---

### Data Types & Type System

**1. Value Types vs Reference Types**

* What are the main differences between value types and reference types in C#?

---

### Properties

**2. Fields**

* What is a field in C#?

**3. Properties**

* What is a property in C# and how does it differ from a field?

**4. Auto-Implemented Properties**

* What are auto-implemented properties in C#?

**5. Backing Fields**

* What is a backing field in C#?

**6. Computed (Calculated) Properties**

* What is a computed (or calculated) property in C#?

---

### Naming & Code Conventions

**7. Naming Conventions**

* What is the PascalCase convention and where is it used in C# (classes, properties, methods)?

**8. Code Style & Braces**

* What is the standard brace placement style in C#?
* Where should opening braces be placed for classes, methods, and control structures?

---

### String Handling & Null Safety

**9. String Interpolation**

* How does string interpolation work in C# using the `$` prefix?
* How do you convert `String.format("Hello %s", name)` to C# string interpolation?
