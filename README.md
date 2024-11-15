# Lesson 02: Numbers and Math

## Explanation

In JavaScript, numbers can be represented in several ways, including integers, floating-point numbers, and BigInts for very large numbers. JavaScript follows the standard arithmetic operations such as addition, subtraction, multiplication, and division. It also supports more complex operations like exponentiation, modulo operation, and handling of special numeric values such as `Infinity`, `-Infinity`, and `NaN` (Not a Number).

### Example Code

```javascript
// Basic Arithmetic Operations
console.log('Addition: ', 5 + 3); // Outputs: 8
console.log('Subtraction: ', 10 - 2); // Outputs: 8
console.log('Multiplication: ', 4 * 2); // Outputs: 8
console.log('Division: ', 16 / 2); // Outputs: 8

// Exponentiation (ES2016)
console.log('Exponentiation: ', 2 ** 3); // Outputs: 8

// Modulo operation - remainder of division
console.log('Modulo: ', 10 % 4); // Outputs: 2

// Special Numbers
console.log('Infinity: ', 1 / 0); // Outputs: Infinity
console.log('-Infinity: ', -1 / 0); // Outputs: -Infinity
console.log(
  'NaN (result of undefined or erroneous operations): ',
  Math.sqrt(-1)
); // Outputs: NaN

// BigInt (for very large numbers, append 'n' to the end of an integer)
console.log('BigInt: ', 1234567890123456789012345678901234567890n + 1n); // Outputs: 1234567890123456789012345678901234567891n
```

1. > document.body.innerHTML = "Addition:" 5 + 3; press Enter the console output is 'Addition: 8' the Browser is Addition: 8

This code demonstrates basic arithmetic operations, the use of exponentiation, modulo operation, handling of special numbers, and the use of BigInt for very large numbers. You can run these examples in the JavaScript console of your browser or in a Node.js environment.

### SyntaxError Code:

The code snippet `document.body.innerHTML = console.log("Addition:" 5 + 3);` has a couple of issues:

1. **Syntax Error**: There's a missing comma or plus sign between `"Addition:"` and `5`. To concatenate the string and the result, you should use a plus sign (`+`) or a comma within the `console.log` function. However, since the intention seems to be to display the result in the browser's body, using `console.log` is not necessary or correct in this context.
2. **Misuse of `console.log`**: The `console.log` function is used to log messages to the console; it does not return a value that can be assigned to `document.body.innerHTML`. Instead, you should directly assign the concatenated string to `document.body.innerHTML`.

document.body.innerHTML = console.log("Addition:" 5 + 3);
VM3444:1 Uncaught SyntaxError: missing ) after argument listUnderstand this error
document.body.innerHTML = (console.log("Addition:" 5 + 3));
VM3543:1 Uncaught SyntaxError: missing ) after argument listUnderstand this error
let console.log("Addition:", 5 + 3)
VM3

Here's the corrected code that displays the result in the browser:

```javascript
document.body.innerHTML = 'Addition: ' + (5 + 3); // Output: Addition: 8
let myConsole = console.log('Addition:', 5 + 3); // Output: Addition: 8
```

This code concatenates the string `"Addition: "` with the result of the addition `5 + 3` and then assigns this complete string to `document.body.innerHTML`, effectively displaying the result in the body of the webpage.

To perform mathematical operations on user input in JavaScript, follow these steps:

1. **Collect User Input**: Use `prompt()` to collect input or `<input>` elements in HTML for a more interactive approach.
2. **Parse the Input**: Convert the input string to a number using `parseInt()`, `parseFloat()`, or the unary `+` operator, depending on the expected number format (integer or floating-point).
3. **Perform Operations**: Apply the desired mathematical operations on the parsed numbers.
4. **Display the Result**: Show the result using `console.log()`, `alert()`, or by updating the DOM for web pages.

### Pseudocode

1. Collect input using `prompt()` or from an `<input>` element.
2. Parse the input to a number.
3. Perform the desired mathematical operation.
4. Display the result.

### Example Code

This example demonstrates collecting two numbers from the user, performing addition, and displaying the result:

```html
<!DOCTYPE html>
<html>
  <body>
    <!-- Input fields for numbers -->
    <input type="text" id="number1" placeholder="Enter first number" />
    <input type="text" id="number2" placeholder="Enter second number" />
    <button onclick="addNumbers()">Add Numbers</button>

    <p id="result"></p>

    <script>
      function addNumbers() {
        // Collect input values
        var num1 = document.getElementById('number1').value;
        var num2 = document.getElementById('number2').value;

        // Parse input to numbers
        num1 = parseFloat(num1);
        num2 = parseFloat(num2);

        // Perform addition
        var sum = num1 + num2;

        // Display the result
        document.getElementById('result').innerText = 'Result: ' + sum;
      }
    </script>
  </body>
</html>
```

This code provides a simple HTML form for user input and a button to trigger the addition. The result is displayed on the webpage. You can modify the `addNumbers` function to perform different mathematical operations as needed.

## Note: " \* and / calculate first", then " + and - calculate after", " \* and / have the same priority", but calculate from left to right, (...) in the bracket calculate first

2 + 2 // Output: 4
10 - 3; // Output: 7
10 _ 3; // Output: 30
10 / 5; // Output: 2
2 + 2 + 2 // Output: 6
2.2 + 2.2 // Output: 4.4
10.90 _ 2 + 20.95 // Output: 42.75
10.90 _ 2 + 20.95 + 4.99 // Output: 47.74
1 + 1 _ 3 // Output: 4
2 _ 3 / 5 // Output: 1.2
2 _ 3 // Output: 6
6 / 5 // Output: 1.2
(1 + 1) _ 3 // Output: 6
20.95 + 7.99 _ 2 // Output: 36.93
36.93 \* 0.1 // Output: 3.693

## ** Wrong ** 20.95 + 7.99 _ 2 _ 0.1 // Wrong Output: 22.548 \*\*

(20.95 + 7.99 _ 2) _ 0.1 // Output: 3.693

1. Weird behavior of math in JavaScript
   0.1 + 0.2 // Output: 0.30000000000000004
   20.95 + 7.99 // Output: 28.939999999999998
   (2099 + 799) / 100 // Output: 28.98
   (2095 + 799) / 100 // Output: 28.94
2. Math.round()
   Math.round(); // Output: NaN
   Math.round(2.2) // Output: 2
   Math.round(2.8) // Output: 3
   ((2095 + 799) _ 0.1) / 100 // Output: 2.894
   Math.round((2095 + 799) _ 0.1) // Output: 289
   Math.round((2095 + 799) \* 0.1) / 100 // Output: 2.89

### **_ javascript how to round a number _** in google.com

## REVIEW

Please generate the below review and code example in javascript for the console:

1. Numbers and Math
2. Order of Operators, and Brackets (...)
3. Calculated the numbers in final project
4. Calculations using floats can be inaccurate
5. Math.round()
6. How to search for code on our own

### Review and Code Examples in JavaScript for the Console

#### 1. Numbers and Math

JavaScript supports various mathematical operations. You can perform basic arithmetic operations directly with numbers.

```javascript
console.log(5 + 3); // Addition, outputs: 8
console.log(10 - 2); // Subtraction, outputs: 8
console.log(4 * 2); // Multiplication, outputs: 8
console.log(16 / 2); // Division, outputs: 8
```

#### 2. Order of Operators, and Brackets (...)

JavaScript follows the standard order of operations, also known as PEMDAS (Parentheses, Exponents, Multiplication and Division, Addition and Subtraction).

```javascript
console.log(2 + 3 * 2); // First multiplies, then adds, outputs: 8
console.log((2 + 3) * 2); // Parentheses first, then multiplication, outputs: 10
```

#### 3. Calculated the numbers in final project

In projects, you often calculate numbers using basic arithmetic operations, taking care of the order of operations.

```javascript
let result = (10 + 5) * 2;
console.log(result); // Outputs: 30
```

#### 4. Calculations using floats can be inaccurate

Due to the way JavaScript handles floating-point arithmetic, calculations can lead to precision issues.

```javascript
console.log(0.1 + 0.2); // Outputs: 0.30000000000000004
```

#### 5. Math.round()

To deal with floating-point inaccuracies, you can use `Math.round()` to round numbers to the nearest integer.

```javascript
console.log(Math.round(0.1 + 0.2)); // Outputs: 0, because 0.30000000000000004 rounds to 0
console.log(Math.round(2.5)); // Outputs: 3
```

#### 6. How to search for code on our own

To find solutions or code examples, use search engines effectively. Use specific keywords related to your problem. For example, if you need to round a number in JavaScript, you can search for:

- "JavaScript round number to nearest integer"
- "How to use Math.round in JavaScript"

Using precise keywords helps in finding relevant documentation, tutorials, and code snippets.
