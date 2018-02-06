# JAVASCRPIT
JavaScript is a widely used web-based programming language that powers the dynamic behavior on most websites, including this one.

## Console
The console is a tool that developers use to record the output of their JavaScript programs.
The console.log() command is used to print, or log, text to the console. Consider the following example:
```javascript
console.log("Hello!");
```
In this example, Hello! is logged to the console. Notice, we denote the end of the line with a semicolon. Although your code will usually run as intended without a semicolon, it is best practice to always include one to ensure your code works as expected in situations when it does need one.
## Data types
Data types are the building blocks of all languages and essential pieces of any program.

•**Strings** — Any grouping of keyboard characters (letters, spaces, numbers, or symbols) surrounded by single quotes ('Hello') or double quotes ("World!"). In the example above, 'New York City' is a string.

•**Numbers** — Any number, including numbers with decimals: 4, 1516, .002, 23.42. In the example above, 40.7 is a number.

•**Booleans** — Either true or false, with no quotations. In the example above, true is a boolean.

•**Null** — Can only be null. It represents the absence of value.

An instance, string has additional information attached to it.
Every string instance has a property called length that stores the number of characters in it. You can retrieve property information by appending the string with a period and the property name:
```javascript
console.log('Hello'.length);
```
In the example above, the value saved to the length property is retrieved from the string, ‘Hello’. The program prints 5 to the console, because ‘Hello’ has five characters in it.

## Math Operators
JavaScript supports the following math operators:

|No.|	Operator      |	 Syntax                                | 
|---|---------------|----------------------------------------|         
|1. |	Add: +	      |	 ```console.log(3 + 4); // Equals 7``` | 
|2. |	Subtract: -	  |	 ```console.log(5 - 1); // Equals 4 ```|
|3. |	Multiply: *	  |	 ```console.log(4 * 2); // Equals 8``` |
|4. |	Divide:/	    |	``` console.log(9 / 3); // Equals 3``` |

## Built-in Methods
Built-in methods are called, or used, by appending an instance with a period, the name of the method, and opening (() and closing ()) parentheses. Consider the examples below:
```javascript
console.log('Hello'.toUpperCase()); // 'HELLO'
console.log('Hey'.startsWith('H')); // true
var str = 'Hello'
console.log(str.slice(0,3); // 'HEL'
console.log('    Remove whitespace   '.trim()); //'Remove whitespace'
```
[Check out this link for more Built-in methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/prototype)

## Libraries
Libraries contain methods that you can call without creating an instance.
One such collection contains mathematical methods, aptly named the Math library.
Math.random generates a random number between 0 and 1.
```javascript
console.log(Math.random() * 100); //25..06447789557669
```
Then, Math.floor rounds the number down to the nearest whole number
```javascript
console.log(Math.floor(Math.random() * 100) ); //48
```
Then, Math.ceil returns the smallest integer greater than or equal to a decimal number.
```javascript
console.log(Math.ceil(43.8)); //44
```
Then, Math.pow(x,y) returns value x^y.
```javascript
console.log(Math.pow(2,3)); //8
```
[Check out this link for more Libraries methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

## Comments
There are two types of code comments in JavaScript:

* A single line comment will comment out a single line and is denoted with two forward slashes // preceding a line of JavaScript code.
```javascript
// The first 5 decimals of pi
console.log('Pi is equal to ' + 3.14159);
```
* A multi-line comment will comment out multiple lines and is denoted with /* to begin the comment, and */ to end the comment.
```javascript
/*
console.log('All of this code');
console.log('Is commented out');
console.log('And will not be executed);
*/
```
