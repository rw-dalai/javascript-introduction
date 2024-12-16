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
name = "Bob"; // ✅ OK: Reassigning the variable
```

- **const**: Immutable variable that cannot be reassigned.

```javascript
const pi = 3.14;
pi = 3.14159;  // ❌ Error: Assignment to constant variable
```

### Data Types

In JavaScript, there exists two types of data types: `Primitive` and `Objects`.

- **Primitive**: Single values like `string`, `number`, `boolean`

```javascript
let name = "Alice";  // String
```

- **Objects**: Complex data structures like `arrays`, `functions`, `objects`

```javascript
let person = { name: "Alice" };  // Object
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
let number = 42;            // Number
typeof number;              // "number"

let pi = 3.14;              // Number
typeof pi;                  // "number"
```

- **String**: Textual data type
```javascript
let name = "Rene";          // String
typeof name;                // "string"
```

- **Boolean**: Logical data type
```javascript
let turnedOn = true;        // Boolean
typeof turnedOn;            // "boolean"
```

- **Undefined**: Default value of uninitialized variables
```javascript
let value;                  // Undefined
typeof value;               // "undefined"
```

- **Null**: Represents an intentional absence of any value
```javascript
let empty = null;           // Null
typeof empty;               // "object"
```

### Objects

In JavaScript, `objects` are used to store an `unordered collection` of data as key-value pairs called `properties`.

- **Simple Objects**: An object is created using `{}` and by defining properties using `key: value` pairs.

```javascript
const person = {
    // Properties
    name: "Ana",
    age: 18,
};
```

- **Objects with Methods**: A method in an object is created using a `key: value` pair where the value is a function.

```javascript
const person = {
    // Properties
    name: "Ana",
    age: 18,
    
    // A Property that is a function
    greet: function() {
        return "Hello, " + this.name;
    }
};
```

- **Accessing Properties**: Using the `.` operator.

```javascript
person.name;  // "Ana"
person.greet();  // "Hello, Ana"
```

- **Updating Properties**: Using the `=` operator.

```javascript
person.age = 19;  // Update age
```

### Functions

In JavaScript, `functions` are used to perform a specific task or calculate a value.

- **Simple Function**: A function that does not take any input parameters.

```javascript
function greet() {
    console.log("Hello, World!");
}
```

- **Function with Parameters**: A function that takes input parameters and uses them inside the function.

```javascript
function greet(name) {
    console.log("Hello, " + name);
}
```

- **Function with Return Value**: A function that returns a value using the `return` keyword.

```javascript
function add(num1, num2) {
    return num1 + num2;
}
```

### Operators

In JavaScript, `operators` are used to perform operations on variables and values.

- **Arithmetic Operators**: `+`, `-`, `*`, `/`

```javascript
let sum = 10 + 5;           // 15
let difference = 10 - 5;    // 5
let product = 10 * 5;       // 50
let quotient = 10 / 5;      // 2
```

- **Assignment Operators**: `=`, `+=`, `-=`, `*=`, `/=`

```javascript
let number = 10;
number += 5;                // number = number + 5
```

- **Loose vs Strict Equality**: `==`, `===`

In JavaScript, to compare values by using `===` (strict equality) and `==` (loose equality).

```javascript
10 == 10;                   // true (loose equality)
10 == "10";                 // true (loose equality)
10 === "10";                // false (strict equality)
```

### Type Conversion

- **Number**: Converts a `string` to a `number`.

In JavaScript, to convert a string to an integer by using the `Number` function.

```javascript
let number = Number("42");  // 42
typeof number;              // "number"
```

### Not a Number (NaN)

In JavaScript, `NaN` is a special number produced when a `mathematical operation` fails.

- **NaN**: is technically a `number`.

```javascript
typeof NaN;                 // "number"
```

- **Check for NaN**: Using the `isNaN` function.

```javascript
Number.isNaN(NaN);          // true
Number.isNaN(10);           // false
```

- **Division by Zero**: Dividing a number by zero results in `NaN`.

```javascript
let result = 10 / "apple";  // NaN

// true
Number.isNaN(number);
```
- **Converting not a Number**: Converting an invalid number results in `NaN`.

```JavaScript
let number = Number('apple'); // NaN

// true
Number.isNaN(number);
```

### If Statement

In JavaScript, the `if` statement is used to execute a block of code if a specified condition is `true`.


- **If Statement**: Executes a block of code if the condition is `true`.

```javascript
// Check if age is greater or equal to 18
if (age >= 18) {
    console.log("You are an adult");
}
```

- **If-Else Statement**: Executes a block of code if the condition is `true`, otherwise executes another block of code.

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


### For Statement

In JavaScript, the `for` statement is used to execute a block of code a number of times.

- **For-Statement**: Call a block of code multiple times.

```javascript
// Loop from 0 to 4
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```


### Strings

In JavaScript, `strings` are used to store and manipulate text.

- **Creating Strings**: A string is created using `""` or `''`.

```javascript
const name = "Alice";
const message = 'Hello, World!';
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

- **Length**: Returns the number of characters in a string.

```javascript
const name = "Alice";
name.length;  // 5
```


### Arrays

In JavaScript, `arrays` are used to store an `ordered collection` of data called `elements`.

- **Creating Arrays**: An array is created using `[]` and by defining elements separated by `,`.

```javascript
const fruits = ["Apple", "Banana", "Cherry"];
```

- **Accessing Elements**: Using `[]` and the index.

```javascript
fruits[0];  // Access the first element, "Apple"
```

- **Updating Elements**: Using `=` and the index.

```javascript
fruits[0] = "Orange";  // Update the first element, to "Orange"
```

- **Length**: Returns the number of elements in an array.

```javascript
fruits.length;  // 3
```

- **Looping over an array**: Using a `for` loop and the `length` property.

```javascript
// Array of fruits
const fruits = ["Apple", "Banana", "Cherry"];

// Loop through the array
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```