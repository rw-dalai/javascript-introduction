# JavaScript Questions and Exercises

## Conceptual Questions

- **Q1.** What is the difference between `let`, `const` JavaScript?
- **Q2.** What is the difference between `==` and `===` in JavaScript?
- **Q3.** Explain what is happening when comparing `42 == "42"`?
- **Q4.** What is the difference between `null` and `undefined` in JavaScript?
- **Q5.** What data types exist in JavaScript?
- **Q6.** How to check the type of a variable in JavaScript?
- **Q7.** What are primitive data types in JavaScript?
- **Q8.** What is an `object` in JavaScript?
- **Q9.** How to create an `object` in JavaScript?
- **Q10.** What is a `function` in JavaScript?
- **Q11.** How do you define a `function` in JavaScript?
- **Q12.** Can a function return `undefined`? If so, how?
- **Q13.** What is `NaN` in JavaScript?
- **Q14.** How to convert a `string` to a `number` in JavaScript?


## Strings

- **E1.** Create a string using `string concatenation` with the following message:
    - `Hello, my name is <your name>`.
    - **Test 1** Log the string to the console.


- **E2.** Create a string using `template literal` with the following message:
    - `Hello, my name is <your name>`.
    - **Test 1** Log the string to the console.


- **E3.** Create a string in an exotic language and check the length of the string.
    - **Test 1** Log the string to the console.
    - **Test 2** Log the length of the string to the console.


## Functions

- **E1.** Write a function `greet` that takes `name` parameter.
    - The function should return a greeting message including the name parameter.
    - If the parameter is not a string it should return `null`.
    - **Test 1** the function by calling it with ('John') and logging the result to the console.
    - **Test 2** the function by calling it with (25) and logging the result to the console.


- **E2.** Write a function `add` that takes two parameters.
    - The function should return the sum of the two numbers.
    - If the parameters are not numbers it should return `null`.
    - **Test 1** the function by calling it with two numbers (5, 3) and logging the result to the console.
    - **Test 2** the function by calling it with two strings ('5', '3') and logging the result to the console.


- **E3.** Write a function `subtract` that takes two parameters.
    - The function should return the difference of the two numbers.
    - If the parameters are not numbers it should return `null`.
    - **Test 1** the function by calling it with two numbers (5, 3) and logging the result to the console.
    - **Test 2** the function by calling it with two strings ('5', '3') and logging the result to the console.


- **E4 🤩.** Write a function `calculate` that takes three parameters `num1`, `num2`, and `operation`.
    - The function should return the result of the operation on the two numbers.
    - The operation can be one of the following: `add`, `subtract`, `multiply`, `divide`.
    - If the parameters are not numbers it should return `null`.
    - If the operation is not one of the above it should return `null`.
    - **Test 1** the function by calling it with (5, 3, 'add') and logging the result to the console.
    - **Test 2** the function by calling it with (5, 3, 'subtract') and logging the result to the console.
    - **Test 3** the function by calling it with (5, 3, 'multiply') and logging the result to the console.
    - **Test 4** the function by calling it with (5, 3, 'divide') and logging the result to the console.
    - **Test 5** the function by calling it with (5, 3, 'modulus') and logging the result to the console.


- **E5.** Write a function `getNumberFromUser` that prompts the user to enter a number and returns the number.
    - The function should prompt the user to enter a number (use `prompt`).
    - The function should return the number entered by the user as type `number`. (use `Number`)
    - If the user enters a value that is not a number it should return `null`.
    - **Test 1** Call the function and provide a valid number and log the result to the console.
    - **Test 2** Call the function and provide an invalid number and log the result to the console.


- **E6 🤩.** Extend the `getNumberFromUser`function that **loops** until the user enters a valid number.
    - The function should keep prompting the user to enter a number until a valid number is entered.


- **E7 🤯**. Combine the `calculate` and `getNumberFromUser` functions to create a simple calculator.
    - The calculator should prompt the user to enter two numbers and an operation.
    - The calculator should then calculate the result and log it to the console.
    - The calculator should keep running until the user enters `exit`.
    - **Test 1** Run the calculator and test the functionality.


## Objects

- **E1.** Create an object `person` with the following properties:
  - `name` of type `string`
  - `age` of type `number`
  - `isStudent` of type `boolean`
  - **Test 1** Log the object to the console.


- **E2.** Create an object `game` with the following properties:
  - `playerName` of type `string`
  - `score` of type `number`
  - `rank` of type `number`
  - `isAlive` of type `boolean`
  - **Test 1** Log the object to the console.


- **E3.** Add the following methods to the `game` object.
  - `updateScore` that takes one parameter and updates the score property.
  - `reset` that resets the score, rank, and isAlive properties to their default values.
  - **Test 1** the `updateScore` method by calling it with a number and logging the object to the console.
  - **Test 2** the `reset` method by calling it and logging the object to the console.


- **E4.** Write a function `createPerson` that takes two parameters `name` and `age`.
  - The function should return a person object with the properties `name` and `age` from the parameters.
  - If the parameters are not a string and a number it should return `null`.
  - **Test 1** the function by calling it with ('John', 25) and logging the result to the console.
  - **Test 2** the function by calling it with (25, 'John') and logging the result to the console.


## Arrays

- **E1.** Create an array `numbers` with the following numbers: 1, 2, 3, 4, 5.
    - **Test 1** Log the array to the console.
  

- **E2.** Add the number 6 to the end of the `numbers` array.
    - **Test 1** Log the array to the console.


- **E3.** Create a function sum that takes an `numbers array` and returns the sum of the numbers.
    - **Test 1** Call the function with the `numbers array` and log the result to the console.
    - **Test 2** Call the function with an `empty array` and log the result to the console.
    - **Test 3 🧐** Call the function with a `strings array` and log the result to the console.


