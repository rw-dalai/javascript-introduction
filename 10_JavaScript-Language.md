# JavaScript Language Overview

<img src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" style="margin-left: 75px; margin-top: 20px; margin-bottom: 20px" width="200"/>

## 1. Introduction

### Overview
* **Link**: https://developer.mozilla.org/en-US/docs/Web/JavaScript
* **Purpose**: A dynamic, multi-paradigm programming language primarily used for web/mobile development.
* **Developed By**: Brendan Eich at Netscape in 1995

### Key Features
* **Interpreted Language**: Executes code line by line without a compilation step.
* **Dynamic Typed**: Variables types can change during runtime.
* **Weakly Typed**: Allows implicit type conversion between different data types.


### Use Cases
* **Frontend Development**: Building interactive web apps using e.g. React, Angular, or Vue.
* **Backend Development**: Building server-side applications using e.g. Node.js.
* **Mobile Development**: Building cross-platform mobile applications using e.g. React Native.

## 2. Programming Languages 2024

Developer Survey [Stack Overflow](https://survey.stackoverflow.co/2024/?utm_source=iterable&utm_medium=email&utm_campaign=dev-survey-2024&utm_content=take-the-survey)  

<img src="https://cdn.prod.website-files.com/5e0f1144930a8bc8aace526c/66a257e610dfc5ab4106c314_wr19t7slu04g8963l40b.png" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="700"/>  


## 3. Basics

### Hello, World!

- **Console**: A built-in object that provides access to the console.

```javascript
console.log("Hello, World!");
```

- **Alert (browser only)**: A built-in function that displays a message box `in the browser`.

```javascript
alert("Hello, World!");
```

- **Prompt (browser only)**: A built-in function that displays a dialog box for user input `in the browser`.
```javascript
let name = prompt("Enter your name:");
alert("Hello, " + name);
```

### Variables

In JavaScript, variables are declared using `let` and `const`.


- **let**: Mutable variable that can be reassigned.

```javascript
let name = "Alice";
name = "Bob";  // ✅ OK: Reassigning the variable
```

- **const**: Immutable variable that cannot be reassigned.

```javascript
const pi = 3.14;
pi = 3.14159;  // ❌ Error: Assignment to constant variable
```

### Data Types

In JavaScript, there exists two types of data types: `Primitive` and `Objects`.

- **Primitives**: e.g. `string`

```javascript
let name = "Alice";
```

- **Objects**: Complex data structures e.g. `arrays`, `functions`, `objects`

```javascript
let person = { name: "Alice" };
```

- **typeof**: Returns the type of a variable as a `string`.

```javascript
let name = "Alice";
typeof name;  // "string"

let person = { name: "Alice" };
typeof person;  // "object"
```

### Primitives

In JavaScript, `primitive` data types are immutable in the sense that they cannot be changed. e.g. `42` is always `42`.
![img.png](_assets/js-primitive-types.png)

- **Number**: Numeric data type
```javascript
let number = 42;                // 42
typeof number;                  // "number"

let pi = 3.14;                  // 3.14
typeof pi;                      // "number"
```

- **String**: Textual data type
```javascript
let name = "Rene";              // "Rene"
typeof name;                    // "string"
```

- **Boolean**: Logical data type
```javascript
let turnedOn = true;            // true
typeof turnedOn;                // "boolean"
```

- **Undefined**: Default value of uninitialized variables
```javascript
let value;                      // undefined
typeof value;                   // "undefined"
```

- **Null**: Represents an intentional absence of any value
```javascript
let empty = null;               // null
typeof empty;                   // "object"
```

### Objects

In JavaScript, `objects` are used to store an `unordered collection` of data as `properties`.

- **Create an Object**: Using `{}` and defining its properties by `key: value` pairs.

```javascript
const person = { name: "Ana", age: 18 };
typeof person;  // "object"
```

- **Accessing Properties**: Using the `.` operator.

```javascript
person.name;  // "Ana"
```

- **Updating Properties**: Using the `=` operator.

```javascript
person.name = "Susi";
```

- **Accessing non-existing Properties**: Returns `undefined`.

```javascript
person.city;  // undefined
```


### Functions

In JavaScript, `functions` are used to perform a specific task or calculate a value.

- **Create a Function**: Using the `function` keyword. `function name() { ... }`

```javascript
function greet() {
    console.log("Hello, World!");
}

typeof greet; // "function"
```

- **with Parameters**: A function that accepts `parameters`.

```javascript
function greet(name) {
    console.log("Hello, " + name);
}
```

- **with Return Value**: A function that returns a value using the `return` keyword.

```javascript
function add(num1, num2) {
    return num1 + num2;
}
```

### Operators

In JavaScript, `operators` are used to perform operations on variables and values.

- **Arithmetic Operators**: `+`, `-`, `*`, `/`

```javascript
let sum = 10 + 5;               // 15
let difference = 10 - 5;        // 5
let product = 10 * 5;           // 50
let quotient = 10 / 5;          // 2
```

- **Assignment Operators**: `=`, `+=`, `-=`, `*=`, `/=`

```javascript
let number = 10;
number += 5;                    // number = number + 5
```

- **Loose vs Strict Equality**: `==`, `===`

In JavaScript, to compare values by using `===` (strict equality) and `==` (loose equality).

```javascript
10 == 10;                       // true (loose equality)
10 == "10";                     // true (loose equality)
10 === "10";                    // false (strict equality)
```

### Type Coercion

In JavaScript, `type coercion` is the automatic conversion of values from one data type to another.

- **String Concatenation**: Converts a `number` to a `string`.

```javascript
let string = "42" + 42;         // "4242"
typeof string;                  // "string"
```

- **Postfix +/- Operator**: Converts a `string` to a `number`.

```javascript
let number = +"42";             // 42
typeof number;                  // "number"

let negative = -"42";           // -42
typeof negative;                // "number"
```

### Type Conversion

In JavaScript, `type conversion` is the explicit conversion of a value from one data type to another.

- **Number Fn**: Converts an integer-based `string` to a `number`.

*Not forgiving*: If the string is not a valid integer, it returns `NaN`.

```javascript
let number = Number("42");      // 42
typeof number;                  // "number"

let pixel = Number("42px");     // NaN
typeof pixel;                   // "number"
```

- **parseInt Fn**: Converts an integer-based `string` to a `number`.

*Forgiving*: If the string is not a valid integer, it returns the `integer part`.

```javascript
let number = parseInt("42");    // 42
typeof number;                  // "number"

let pixel = parseInt("42px");   // 42
typeof pixel;                   // "number"
```

- **String Fn**: Converts a `number` to a `string`.

```javascript
let string = String(42);        // "42"
typeof string;                  // "string"
```

### Not a Number (NaN)

In JavaScript, `NaN` is a special number produced when a `mathematical operation` fails.

- **NaN**: is technically a `number`.

```javascript
typeof NaN;                     // "number"
```

- **Check for NaN**: Using the `isNaN` function.

```javascript
Number.isNaN(NaN);              // true
Number.isNaN(10);               // false
```

- **Division by Zero**: Dividing a number by zero results in `NaN`.

```javascript
let result = 10 / "apple";      // NaN
Number.isNaN(result);           // true
```
- **Converting not a Number**: Converting an invalid number results in `NaN`.

```JavaScript
let result = Number('42px');    // NaN
Number.isNaN(result);           // true
```

### Conditional Statements

In JavaScript, `conditional statements` are used to perform different actions based on different conditions.


- **If Statement**:

Executes a block of code if the condition is `true`. Otherwise, it skips the block.

```javascript
// Check if age is greater or equal to 18
if (age >= 18) {
    console.log("You are an adult");
}
```

- **If-Else Statement**:

Executes a block of code if the condition is `true`, otherwise executes another block of code.

```javascript
// Prompt the user for their age
const ageFromUser = prompt("Enter your age:");

// Convert the age to a number
const age = Number(ageFromUser);

// Check if age is greater or equal to 18
if (age >= 18) {
    console.log("You are an adult");
} else {
    console.log("You are a minor");
}
```


### Iteration Statements

In JavaScript, `iteration statements` are used to execute a block of code multiple times.

- **For-Statement**:

Call a block of code multiple times. `for (initialization; condition; increment) { ... }`

```javascript
// Loop from 0 to 4
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```


### Strings

In JavaScript, `strings` are used to store and manipulate Unicode text. Unicode can represent any character in the world, even emojis 😍.

- **Create a String**: Using `""` or `''`.

```javascript
const name = "Alice";
const message = 'Hello, World!';
```

- **Length**: The length property returns the number of characters.

```javascript
const name = "Alice";
name.length;  // 5
```

- **Concatenation**: Combining strings using the `+` operator.

```javascript
const greeting = "Hello, " + name;
```

- **Template Literals**: Using backticks to create strings with placeholders `${}`.

```javascript
const name = "Alice";
const greeting = `Hello, ${name}`;
```


### Arrays

In JavaScript, `arrays` are used to store an `ordered collection` of data called `elements`.

- **Create an Array**: Using `[]` and a list of elements.

```javascript
const fruits = ["Apple", "Banana", "Cherry"];
typeof fruits;  // "object"
```

- **Length**: The length property returns the number of elements.

```javascript
fruits.length;  // 3
```

- **Accessing Elements**: Using the `Bracket Notation` `[]` and the index.

```javascript
fruits[0];  // Access the first element, "Apple"
```

- **Updating Elements**: Using the `Bracket Notation` `[]` and the index.

```javascript
fruits[0] = "Orange";  // Update the first element, to "Orange"
```

- **Iterate over an array**: Using `for` and the `length` property.

```javascript
// Array of fruits
const fruits = ["Apple", "Banana", "Cherry"];

// Iterate over the array
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```


## 2. Advanced

### Objects

In JavaScript, `objects` are used to store an `unordered collection` of data called `properties`.

- **Key-Value Pairs**:

Properties consist of key-value pairs. Keys are `strings` and values can be any data type (e.g. `string`, `number`, `boolean` or `object`).

```javascript
const person = { name: "Alice", age: 18 };
```

- **Accessing Properties**:

Properties can be accessed using the `Dot Notation` `.` or the `Bracket Notation` `[]`.

```javascript
student.name;                   // Dot Notation
student["name"];                // Bracket Notation uses a string

const property = "name";
student[property];              // Bracket Notation with a variable
```

- **Accessing non-existing Properties**:

Accessing a non-existing property returns `undefined`.

```javascript
student.city;                    // undefined
student["city"];
```

- **Updating Properties**:

Properties can be updated using the `Dot Notation` `.` or the `Bracket Notation` `[]`.

```javascript
student.name = "Bob";           // Dot Notation
student["name"] = "Bob";        // Bracket Notation

const property = "name";
student[property] = "Bob";      // Bracket Notation with a variable
```

- **Adding Properties**:

Properties can be added to an object using the `Dot Notation` `.` or the `Bracket Notation` `[]`.

```javascript
student.city = "New York";       // Dot Notation
student["city"] = "New York";    // Bracket Notation
```

- **Deleting Properties**:

Properties can be deleted using the `delete` operator.

```javascript
delete student.name;
```


### Object Methods

- **Methods**:

Objects can have properties that are functions, called `methods`. The methods can access the object using `this`.

```javascript
const student = {
    // Properties with primitive values
    name: "Ana",
    age: 18,
    
    // Property is a function (aka method)
    greet: function() {
        // `this` refers to the object
        return `Hello, ${this.name}`;
    },
};
```

- **Calling Methods**:

Accessing a property and calling it with `()` executes the function (aka method).

```javascript
student.greet();                 // "Hello, Ana"
student["greet"]();
```


- **Calling non-existing Methods**:

Accessing a non-existing property and calling it with `()` results in an error.

```javascript
student.walk                     // undefined
student.walk();                  // ❌ Error: student.walk is not a function
```

### Object Nesting

- **Key-Value Pairs**:

Properties consist of key-value pairs. Keys are `strings` and values can be any data type even another `object`.

```javascript
const person = {
    // Properties with primitive values
    name: "Alice",
    age: 18,

    // Property is an object
    address: {
        city: "New York",
        zip: 10001,
    },
};
```

- **Accessing Nested Properties**:

Using the `Dot Notation` `.` or the `Bracket Notation` `[]`.

```javascript
person.address.city;             // "New York"
person["address"]["city"];       // "New York"
```