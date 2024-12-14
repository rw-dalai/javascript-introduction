# Java vs JavaScript

## 1. Execution

### Java

- Java is a `compiled` language which means that the code is compiled into `bytecode` and then executed by the `JVM`.
- Java code can be executed on any platform that has a `JVM` installed.

### JavaScript

- JavaScript is an `interpreted` language which means that the code is executed by the `JavaScript engine` without a compilation step.
- JavaScript code can be executed in the `browser` or on the `server` but it needs a `JavaScript runtime` to execute the code.


## 2. Compilation

### Java

- Java code is `compiled` into `bytecode` by the `Javac` compiler.
- The `bytecode` is then executed by the `JVM` which translates it into machine code.


### JavaScript

- JavaScript code get directly executed by the `JavaScript engine` without a compilation step.
- The `JavaScript engine` parses the code, generates `bytecode` and then executes it.


## 3. Type Error

### Java

- The Java Compiler checks the code for `type errors` during the compilation step.
- If there are any `type errors` the code will not compile and the developer has to fix the errors.


### JavaScript

- There is no Java Compiler in JavaScript that checks the code for `type errors`.
- If there are any `type errors` they will only be detected during runtime which can lead to unexpected behavior.


## 4. Type System

### Java

- Java has a `static` and `strong type` system which means that variables have a fixed type and cannot change.

```java
String name = "John";

// Static Typing: ❌ Error: Variables cannot change types
name = 42;              

// Strong Typing: ❌ Error: No type conversion from boolean to int
int value = +true;
```

### JavaScript

- JavaScript has a `dynamic` and `weak type` system which means that variables can change types and allow type conversion between different data types.

```javascript
let name = "John";
typeof name; // "string"

// Dynamic Typing: ✅ OK: Variables can change types
name = 42;
typeof name; // "number"

// Weak Typing: ✅ OK: type conversion from boolean to number
let value = +true; // 1
```

## 5. Classes and Objects

### Java Classes

- In Java we can define classes with `class` and place `attributes` and `methods` inside the class.
- This encapsulates the `attributes` aka data `methods` aka behaviour inside the same class.
- Then we create `instances` aka objects with `new` and access it's public methods.

```java
public class Person {
    private String name;                    // Private Attribute
    
    public Person(String name) {            // Constructor
        setName(name);
    }
    
    public String getName() {               // Getter
        return name;
    }
    
    public void setName(String name) {      // Setter
        this.name = name;
    }
    
    public String greet() {                 // Method
        return "Hello, " + name;
    }
}
```

- **Usage**: After we instantiate an object and access its public methods.
```java
// 1. Create an object with `new`
Person person = new Person("Alice");

// 2. Use the object
person.setName("Bob");
String greetings = person.greet();
System.out.println(greetings); // "Hello, Bob"
```


### JavaScript Classes

- In JavaScript we can use classes like in Java.
- However, internally JavaScript uses `prototypes` to mimic classes hence it's just a syntactic sugar.

```javascript
class Person {
    #name;                              // Private Attribute (note the #)
    
    constructor(name) {                 // Constructor
        this.#name = name;
    }
    
    get name() {                         // Getter   
        return this.#name;
    }
    
    set name(name) {                     // Setter
        this.#name = name;
    }
    
    greet() {                            // Method
        return `Hello, ${this.#name}`;
    }
}
```

- **Usage**: After we instantiate an object and access it's public methods.
```javascript
// 1. Create an object with `new`
const person = new Person("Alice");

// 2. Use the object
person.name = "Bob";
const greetings = person.greet();
console.log(greetings); // "Hello, Bob"
```

### JavaScript Objects

- In JavaScript we often create `objects` with specific `properties` and their values directly.
- We can also add `methods` to the object to encapsulate the behavior.
- However, the properties are public and can be accessed directly.

```javascript
const person = {
    name: "Alice",         // Property

    greet: function() {    // Method
        return "Hello, " + this.name;
    }
};
```

- **Usage**: After we just access the properties directly
```javascript
// 1. Create an object directly
// const person = { .. }

// 2. Use the object
person.name = "Bob";
const greetings = person.greet();
console.log(greetings); // "Hello, Bob"
```




