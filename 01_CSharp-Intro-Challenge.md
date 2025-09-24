# Java to C# Translation Exercise

## 1. Java Classes to Translate

### Person Class

Create a C# class `Person` based on the following Java class.

- **Create Console App**

```sh
dotnet new console -n PersonApp
cd PersonApp
```


- **Translate the following Java class to C#:**

```java
public class Person {

    // Fields / Attributes
    private String firstName;

    // Ctor
    public Person() {
        this.firstName = "";
    }

    // Getter
    public String getFirstName() {
        return firstName;
    }

    // Setter
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }
}
```

## 2. Conceptual Questions

Answer these questions to deepen your understanding of C# concepts when translating from Java:

### Properties

**1. Fields**

* What is a field in C#?

**2. Properties**

* What is a property in C# and how does it differ from a field?

**3. Auto-Implemented Properties**

* What are auto-implemented properties in C#?

**4. Backing Fields**

* What is a backing field in C#?

**5. Object Initializer Syntax**

* How do you use object initializer syntax in C# to set properties when creating an object?

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
