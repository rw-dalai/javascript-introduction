# Java vs JavaScript

## 1. Type System

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

## 2. Classes and Objects

### Java Classes

- In Java we can define classes with `class` and place `attributes` and `methods` inside the class.
- This encapsulates the data `attributes` and behavior `methods` inside the class.
- Then we create `instances` with `new` and access the public methods.

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
// 1. Create an Instance with `new`
Person person = new Person("Alice");

// 2. Use the instance
person.setName("Bob");
String greetings = person.greet();
System.out.println(greetings); // "Hello, Bob"
```


### JavaScript Classes

- In JavaScript we can uses classes like in Java.
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

- **Usage**: After we instantiate an object and access its public methods.
```javascript
// 1. Create an Instance with `new`
const person = new Person("Alice");

// 2. Use the object
person.name = "Bob";
console.log(person.name);
console.log(person.greet());
```

### JavaScript Objects

- In JavaScript we often create `objects` with specific `properties` and their values directly.
- We can also add `methods` to the object to encapsulate the behavior.
- However, the properties are public and can be accessed directly.

```javascript
const person = {
    // Properties
    name: "Alice",
    
    // Methods
    greet: function() {
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




