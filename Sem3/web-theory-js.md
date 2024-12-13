
# Output

`document.write()`

`console.log()`

# Comments
```js
single line 
//

multi line 
/*
multi
*/
```

#  Variable
- Using `var`
	- **JavaScript var keyword**  - The [****var****](https://www.geeksforgeeks.org/javascript-var/) is the oldest keyword to declare a variable in [JavaScript](https://www.geeksforgeeks.org/introduction-to-javascript/). It has the [Global scoped](https://www.geeksforgeeks.org/understanding-variable-scopes-in-javascript/#:~:text=types%20of%20scopes-,Global%20Scope,-%E2%80%93%20Scope%20outside%20the) or function scoped. This means:
	- If you create a variable outside of a function, you can use it anywhere in your code.
	- If you create a variable inside a function, you can only use it within that function.
	- Redeclaring a variable using the `var` is possible. It also impose problems.
	
- Using `let`
	- These variables has the [block scope](https://www.geeksforgeeks.org/what-are-block-scoped-variables-and-functions-in-es6/)
	- It can’t be accessible outside the particular code block.
	- Variables defined with `let` and `const` **can not** be redeclared.
- Using `const`
	- The [const keyword](https://www.geeksforgeeks.org/javascript-const/) has all the properties that are the same as the [let keyword](https://www.geeksforgeeks.org/javascript-let/), except the user cannot update it and have to assign it with a value at the time of declaration.
	- These variables also have the [block scope](https://www.geeksforgeeks.org/what-are-block-scoped-variables-and-functions-in-es6/).
	- It is mainly used to create constant variables whose values can not be changed once they are initialized with a value.

```js
var x = 5;  
var y = 6;  
var z = x + y;

let x = 5;  
let y = 6;  
let z = x + y;

const x = 5;  
const y = 6;  
const z = x + y;
```

## JavaScript Dollar Sign $

Since JavaScript treats a dollar sign as a letter, identifiers containing $ are valid variable names:
```js
let $ = "Hello World";  
let $$$ = 2;  
let $myMoney = 5;
```

# Naming variables in JavaScript

- JavaScript is case-sensitive.
- The first character must be a letter (a-z, A-Z), an underscore (_), or a dollar sign ($).
- Rest of the characters can include letters, numbers, underscores, and dollar signs.
- Variable names cannot contain spaces.
- Variables cannot be the same as reserved keywords such as `if` or `const`.

# JavaScript Operators
## JavaScript Arithmetic Operators

Arithmetic operators perform arithmetic on numbers (literals or variables).

|Operator|Description|
|---|---|
|+|Addition|
|-|Subtraction|
|*|Multiplication|
|**|Exponentiation ([ES2016](https://www.w3schools.com/js/js_2016.asp))|
|/|Division|
|%|Modulus (Remainder)|
|++|Increment|
|--|Decrement|
## JavaScript Assignment Operators

Assignment operators assign values to JavaScript variables.

|Operator|Example|Same As|
|---|---|---|
|=|x = y|x = y|
|+=|x += y|x = x + y|
|-=|x -= y|x = x - y|
|*=|x *= y|x = x * y|
|/=|x /= y|x = x / y|
|%=|x %= y|x = x % y|
|**=|x **= y|x = x ** y|

## Shift Assignment Operators

|Operator|Example|Same As|
|---|---|---|
|<<=|x <<= y|x = x << y|
|>>=|x >>= y|x = x >> y|
|>>>=|x >>>= y|x = x >>> y|

## Bitwise Assignment Operators

|Operator|Example|Same As|
|---|---|---|
|&=|x &= y|x = x & y|
|^=|x ^= y|x = x ^ y|
|\|=|x \|= y|x = x \| y|

## Logical Assignment Operators

|Operator|Example|Same As|
|---|---|---|
|&&=|x &&= y|x = x && (x = y)|
|\|=|x \|= y|x = x \| (x = y)|
|??=|x ??= y|x = x ?? (x = y)|

# JavaScript Data Types

### JavaScript defines 7 types of primitive data types:

- `string`
- `number`
- `boolean`
- `null`
- `undefined`
- `symbol`
- `bigint`

# JavaScript Functions

```js
function myFunction(p1, p2) {  
  console.log(p1 + p2);  
}
myFunction(4, 3);


// Example - 2

let x = myFunction(4, 3);  
  
function myFunction(a, b) {  
// Function returns the product of a and b  
  return a * b;  
}
```

# JavaScript Objects [link](https://www.w3schools.com/js/js_objects.asp)

```js
// Create an Object  
const person = {  
  firstName: "John",  
  lastName: "Doe",  
  age: 50,  
  eyeColor: "blue"  
};

```

## Accessing Object Properties

You can access object properties in two ways:
```js
objectName.propertyName

objectName["propertyName"]
```

```js
// Example
person.lastName;

person["lastName"];
```

```js
// more example
const person = {
  firstName:"John",
  lastName:"Doe",
  age:50, eyeColor:"blue"
}

// Create a copy
const x = person;

// Change Age in both
x.age = 10;

console.log(x.age)            // 10
console.log(person.age)       // 10
```

# JavaScript Events

HTML events are **"things"** that happen to HTML elements.

When JavaScript is used in HTML pages, JavaScript can **"react"** on these events.

---
## HTML Events

```html
<element event = 'some javascript'>
```

## Common HTML Events

Here is a list of some common HTML events:

|Event|Description|
|---|---|
|onchange|An HTML element has been changed|
|onclick|The user clicks an HTML element|
|onmouseover|The user moves the mouse over an HTML element|
|onmouseout|The user moves the mouse away from an HTML element|
|onkeydown|The user pushes a keyboard key|
|onload|The browser has finished loading the page|
```html
// example
<button onclick="window.print()">The time is?</button>
```

# JavaScript if, else, and else if

```js
if (time < 10) {  
  greeting = "Good morning";  
} else if (time < 20) {  
  greeting = "Good day";  
} else {  
  greeting = "Good evening";  
}
```

# JavaScript Switch Statement

```js
// syntax
switch(expression) {  
  case x:  
    // code block    
    break;  
  case y:  
    // code block   
    break;  
  default:  
    // code block  
}
```

```js
switch (new Date().getDay()) {  
  case 0:  
    day = "Sunday";  
    break;  
  case 1:  
    day = "Monday";  
    break;  
  case 2:  
     day = "Tuesday";  
    break;  
  case 3:  
    day = "Wednesday";  
    break;  
  case 4:  
    day = "Thursday";  
    break;  
  case 5:  
    day = "Friday";  
    break;  
  case 6:  
    day = "Saturday";  
}
```

# JavaScript Strings

```js
let carName1 = "Volvo XC60";  // Double quotes  
let carName2 = 'Volvo XC60';  // Single quotes
```

## String Length

```js
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";  
let length = text.length;
```

## Q. `(x == y)` true or false? 
```js
let x = new String("John");  
let y = new String("John");

console.log(x==y) // false
```

>Comparing two JavaScript objects **always** returns **false**.

## String Methods

### Extracting String Parts

There are 3 methods for extracting a part of a string:

- slice(_start_, _end_)
- substring(_start_, _end_)
- substr(_start_, _length_)

### Converting to Upper and Lower Case

```js
let text1 = "Hello World!";  
let text2 = text1.toUpperCase();

let text1 = "Hello World!";       
let text2 = text1.toLowerCase();  
```

### trim()

```js
let text1 = "      Hello World!      ";  
let text2 = text1.trim(); 
// output
// Hello World! 
```

### split()

A string can be converted to an array with the `split()` method:
If the separator is "", the returned array will be an array of single characters

```js
text.split(",")    // Split on commas  
text.split(" ")    // Split on spaces  
text.split("|")    // Split on pipe

// example

let str = "Hello"
let arr = str.split("")
console.log(arr)

// (5) ['H', 'e', 'l', 'l', 'o']
```

### Number Methods

These **number methods** can be used on all JavaScript numbers:

| Method        | Description                                        |
| ------------- | -------------------------------------------------- |
| toString()    | Returns a number as a string                       |
| toFixed()     | Returns a number written with a number of decimals |
| toPrecision() | Returns a number written with a specified length   |

# JavaScript Arrays

```js
const cars = ["Saab", "Volvo", "BMW"];
// cars[0] = "Saab"
```



## Array Methods

### length

```js
cars.length
```

```js
### Adding Array Elements

const fruits = [1,2,3,4,];
fruits.push(8);
// [1, 2, 3, 4, 8]


### pop()

const fruits = [1,2,3,4,];
fruits.pop();
// [1, 2, 3]


## shift()

const fruits = [1,2,3,4,];
fruits.shift();
// [2, 3, 4]

## unshift()
const fruits = [1,2,3,4,];
fruits.unshift(7)
// [7, 1, 2, 3, 4]
```

## Sorting an Array

The `sort()` method sorts an array alphabetically:
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];  
fruits.sort();
// ['Apple', 'Banana', 'Mango', 'Orange']

const nums = [2,4, 10, 21, 5, 51]
nums.sort();
// [10, 2, 21, 4, 5, 51]
```

## Reversing an Array

The `reverse()` method reverses the elements in an array:

```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];  
fruits.reverse();
// ['Mango', 'Apple', 'Orange', 'Banana']
```

# JavaScript Loops

JavaScript has 5 main types of loops:
- `for`
- `while`
- `do...while` 
- `for...in`  <- not needed (only remember name)
- `for...of`  <- not needed (only remember name)

## JavaScript for Loop

```js
for (let i = 0; i < 4; i++) {
 console.log(i);
}
```

## JavaScript while Loop

```js
let i = 0;
while (i < 6) {
  console.log(i);
  i++;
}
```

## JavaScript do-while Loop

```js
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 6);
```

## JavaScript for-in Loop  (only remember name)

```js
const obj = {a: 1, b: 4, c: 7};

for (let prop in obj) {
  console.log(prop + ': ' + obj[prop]);
}
// output
a: 1
b: 4
c: 7
```

## JavaScript for-of Loop  (only remember name)

```js
const arr = [1, 2, 3];

for (let val of arr) {
  console.log(val);
}
// output
1
2
3
```

# JavaScript Date Objects

creates a date object with the **current date and time**:

```js
const d = new Date();
```

```js
// custom date
const d = new Date("2022-03-25");
```

### Date Get Methods

|Method|Description|
|---|---|
|getFullYear()|Get **year** as a four digit number (yyyy)|
|getMonth()|Get **month** as a number (0-11)|
|getDate()|Get **day** as a number (1-31)|
|getDay()|Get **weekday** as a number (0-6)|
|getHours()|Get **hour** (0-23)|
|getMinutes()|Get **minute** (0-59)|
|getSeconds()|Get **second** (0-59)|
|getMilliseconds()|Get **millisecond** (0-999)|
|getTime()|Get **time** (milliseconds since January 1, 1970)|
# JavaScript Random

```js
Math.random();
```

## math.floor()
```js
let num = 2.34564
Math.floor(num)
// 2
```
## Generating Random Numbers

```js
// Returns a random integer from 0 to 9:  
Math.floor(Math.random() * 10);

// Returns a random integer from 0 to 10:  
Math.floor(Math.random() * 11);

// Returns a random integer from 0 to 100:  
Math.floor(Math.random() * 101);

// Returns a random integer from 1 to 100:  
Math.floor(Math.random() * 100) + 1;
```

# JavaScript Classes

### Syntax
```
class ClassName {  
  constructor() { ... }  
}
```

## Create Class and object

```js
class Emp {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
}

const emp = new Emp("Aman", "25 years");   // create object
console.log(emp.name);
console.log(emp.age);
```


Basic Questions

# 1. session and cookie [link](https://www.geeksforgeeks.org/difference-between-session-and-cookies/)

## Session

- A session is like a temporary "conversation" between your browser and a website.
- It starts when you visit a website and ends when you close the browser or log out.
- It stores information about you (e.g., your login status or items in your shopping cart) on the server.
- Sessions are usually tracked using a session ID, which is sent to your browser and stored temporarily.

## 2. Cookie

- A cookie is a small piece of data stored directly on your browser by the website.
- It remembers information about you, like your preferences, login details, or activity.
- Cookies can persist even after you close your browser, depending on their expiration date.
- They help websites "remember" you between visits, like keeping you logged in or personalizing content.

# pass by value and pass by reference

## pass by value

```js
let a = 10;
let b = a;

a = 20;

console.log(a); // Outputs: 20
console.log(b); // Outputs: 10
```

## pass by reference

```js
let obj1 = { value: 10 };
let obj2 = obj1;

obj1.value = 20;

console.log(obj1.value); // Outputs: 20
console.log(obj2.value); // Outputs: 20
```