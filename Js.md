# 🟨 JavaScript Basics

## 🔸 Declare Variables

### let

.Purpose: Declares a block-scoped variable that can be reassigned later.

.Scope: Block-scoped, meaning the variable is accessible only within the block (code enclosed in curly braces {}) where it's declared.

.Reassignment: Allowed, you can change the variable's value after its initial assignment.

.Re-declaration: Not allowed within the same scope; attempting to redeclare a let variable will result in a SyntaxError. 

```js
let  count = 10; // Declaring a variable 'count' with an initial value
console.log(count); // Output: 10

count = 25; // Reassigning a new value to 'count'
console.log(count); // Output: 25
```

### const

.Purpose: Declares a block-scoped constant, whose value cannot be reassigned after its initial assignment.

.Scope: Block-scoped, similar to let.

.Reassignment: Not allowed; attempting to reassign a const variable will result in a TypeError.

.Re-declaration: Not allowed within the same scope; attempting to redeclare a const variable will result in a SyntaxError.

.Initialization: Must be initialized during declaration.

```js
const PI = 3.14159; // Declaring a constant 'PI' with its value
console.log(PI); // Output: 3.14159

// The following would result in a TypeError: Assignment to constant variable.
// PI = 3.14; 

const person = { 
  name: "Alice", 
  age: 30 
};
person.age = 31; // Modifying a property of the object is allowed
console.log(person.age); // Output: 31
```
---

## 🔸 Data Types
Js  categorize data into two main types: Permitive and Non-Permitive

### Permitive Data Types:

```js
let name = "John";         // String
let age = 30;              // Number
let isStudent = true;      // Boolean
let score = null;          // Null
let grade;                 // Undefined
```
### Non Permitive Data Type:

.Arrays: Ordered collections values.Example:
```js
let colors = ["red","yellow","pink"]
```
.Functions: Block of code.Example:
```js
function greet(name){
console<log("Hello," + name):
}

```

---

## 🔸 Arithmetic & Comparison Operators

```js
// Arithmetic
let a = 10 + 5;       // 15
let b = 10 - 3;       // 7
let c = 4 * 2;        // 8
let d = 9 / 3;        // 3
let e = 5 % 2;        // 1

// Comparison
console.log(5 > 3);   // true
console.log(5 === 5); // true
console.log(5 !== 6); // true
```

---

## 🔸 Conditional Statements

### If-else statement:
The if statement evaluates a condition. If the condition is true, the block of code inside the if statement is executed. If the condition is false, the code block is skipped.

```js
let num = 10;

if (num > 0) {
  console.log("Positive number");
} else if (num === 0) {
  console.log("Zero");
} else {
  console.log("Negative number");
}
```
### Switch statement:
The switch statement evaluates an expression and executes a block of code based on matching cases, often serving as an alternative to multiple else-if statements for improved readability with numerous conditions based on a single variable's value.

```js
let fruit = "apple";

switch (fruit) {
  case "apple":
    console.log("You chose apple");
    break;
  case "banana":
    console.log("You chose banana");
    break;
  default:
    console.log("Unknown fruit");
}
```

---

# 🟦 Loops & Functions

## 🔹 For Loop to print numbers 1-10

```js
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

---

## 🔹 Use for...of to Loop through an Array
.The for...of loop in JavaScript is a modern and concise way to iterate over the values of iterable objects.
### Syntax:
```js
for (variable of iterable) {
  // code block to be executed
}
```
.Exaple:
```js
let colors = ["red", "green", "blue"];

for (let color of colors) {
  console.log(color);
}
```

---

## 🔹 Function to Return Square
.Function is generally a block of code which we can at the time of need.

```js
function square(num) {
  return num * num;
}

console.log(square(5)); // 25
```

---

## 🔹 Arrow Function Syntax
. It provide a shorter syntax compared to traditional function expressions.
. Callback functions in array methods like map(),filter(),etc.
 
### Syntax:
```js
const myFunction = (arg1, arg2) => {
  // function body
};
``` 
### Code:
```js
const square = (num) => num * num;

console.log(square(6)); // 36
```

---

# 🟦 Arrays

## 🔹 Create Array of Student Names

```js
let students = ["Ali", "Sara", "Zainab", "Mohammed"];
```

---

## 🔹 Convert All Names to Uppercase

.The map() method is a powerful and commonly used array method in JavaScript that allows you to transform each element in an array and create a new array based on the results. It's a non-mutating method, meaning it does not alter the original array, leaving it unchanged.

### Code
```js
let upperNames = students.map(name => name.toUpperCase());
console.log(upperNames);
// Output: ["ALI", "SARA", "ZAINAB", "MOHAMMED"]
```

---

## 🔹 Filter Names Longer Than 5 Characters

```js
let longNames = students.filter(name => name.length > 5);
console.log(longNames);
// Output: ["Zainab", "Mohammed"]
```

---

## 🔹 Find a Specific Name

```js
let findName = students.find(name => name === "Sara");
console.log(findName); // "Sara"
```

---

## 🔹 Add and Remove Items Using .push() and .splice()

```js
students.push("Yasir");       // Add at end
console.log(students);        // ["Ali", "Sara", "Zainab", "Mohammed", "Yasir"]

students.splice(1, 1);        // Remove 1 item at index 1
console.log(students);        // ["Ali", "Zainab", "Mohammed", "Yasir"]
```
### slice:
splice is used to add,remove and replacing elements.

### syntax:
```js
array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
```
### Parameters:

.start (Required): The index at which to start changing the array. A negative value counts from the end of the array, meaning -1 is the last element, -2 is the second-to-last, etc.

.deleteCount (Optional): The number of elements to remove from the start index. If omitted, all elements from start to the end of the array will be removed.

.item1, item2, ... (Optional): The elements to add to the array, starting at the start index. These elements are inserted after any elements that were removed.

---
