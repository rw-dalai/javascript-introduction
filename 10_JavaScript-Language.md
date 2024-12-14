# JavaScript Language Overview

<img src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" style="margin-left: 75px; margin-top: 20px; margin-bottom: 20px" width="200"/>

## 1. Basics

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

In JavaScript variables are declared using `let` and `const`.


* **let**: Mutable variable that can be reassigned.

```javascript
let name = "Alice";
name = "Bob"; // ✅ OK: Reassigning the variable
```

* **const**: Immutable variable that cannot be reassigned.

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

### Primitive Types
 
In JavaScript, there are 7 primitive data types but we will focus on the most common ones.  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Language_overview

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


### Object Types

In JavaScript `objects` are used to store an `unordered collection` of data as key-value pairs called `properties`.

* **Simple Objects**: An object is created using `{}` and by defining properties using `key: value` pairs.

```javascript
const person = {
    // Properties
    name: "Ana",
    age: 18,
};
```

* **Objects with Methods**: A method in an object is created using a `key: value` pair where the value is a function.

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

* **Accessing Properties**: Using the `.` operator.

```javascript
person.name;  // "Ana"
person.greet();  // "Hello, Ana"
```

* **Updating Properties**: Using the `=` operator.

```javascript
person.age = 19;  // Update age
```


### Functions

In JavaScript, functions are used to perform a specific task or calculate a value.

- **Simple Function**: A function that does not take any input parameters.

```javascript
function greet() {
    console.log("Hello, World!");
}
```

* **Function with Parameters**: A function that takes input parameters and uses them inside the function.

```javascript
function greet(name) {
    console.log("Hello, " + name);
}
```

* **Function with Return Value**: A function that returns a value using the `return` keyword.

```javascript
function add(num1, num2) {
    return num1 + num2;
}
```


### Arrays

In JavaScript, `arrays` are used to store an `ordered collection` of data called `elements`.

```javascript
const fruits = ["Apple", "Banana", "Cherry"];
```

* **Accessing Elements**: Using `[]` and the index.

```javascript
fruits[0];  // Access the first element, "Apple"
```

* **Updating Elements**: Using `=` and the index.

```javascript
fruits[0] = "Orange";  // Update the first element, to "Orange"
```


### Operators

In JavaScript operators are used to perform operations on variables and values.

- **Arithmetic Operators**: `+`, `-`, `*`, `/`

```javascript
let sum = 10 + 5;           // 15
let difference = 10 - 5;    // 5
let product = 10 * 5;       // 50
let quotient = 10 / 5;      // 2
```

- **Assignment Operators**: `=`, `+=`, `-=`, `*=`, `/=`

In JavaScript, you can assign values using `=` and perform an operation at the same time.

```javascript
let number = 10;
number += 5;                // number = number + 5
```

- **Loose vs Strict Equality**: `==`, `===`

In JavaScript, you can compare values using `===` (strict equality) and `==` (loose equality).

```javascript
10 == 10;                   // true (loose equality)
10 == "10";                 // true (loose equality)
10 === "10";                // false (strict equality)
```

- **Number**: Converts a `string` to an `number`.

In JavaScript, you can convert a string to an integer using the `Number` function.

```javascript
let number = Number("42");  // 42
typeof number;              // "number"
```

### Not a Number (NaN)

- **NaN**: is a number that is the result of an operation that cannot produce a normal result.

```javascript
typeof NaN;                 // "number"
```

- **Division by Zero**: Dividing a number by zero results in `NaN`.

```javascript
let result = 10 / "apple";  // NaN
typeof result;              // "number"
```
- **Invalid Number**: Converting an invalid number results in `NaN`.

```JavaScript
// User inputs `apple`
let getNumber = prompt("Enter a number:");

// Number("apple") returns `NaN`
let number = Number(getNumber);

// true
number === NaN;
```

### Control Structures

* **If-Else Statement**: Executes a block of code if a specified condition is `true`.

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

* **For-Statement**: Loops through a block of code a number of times.

```javascript
// Array of fruits
const fruits = ["Apple", "Banana", "Cherry"];

// Loop through the array
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```