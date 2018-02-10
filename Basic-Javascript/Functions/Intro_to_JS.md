# JavaScript
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

## Variables
Programmers use variables to write code that is easy to understand and repurpose.
Variables allow us to assign data to a word and use the word to reference the data.
### Variable: const
Const, short for constant, is a JavaScript keyword that creates a new variable with a value that cannot change.
Let us take an example:
```javascript
const myName = 'Arya';
console.log(myName);
// Output: Arya
```
Here "myName" is the variable's name. Notice that the word has no spaces.
'Arya' is the value assigned (=) to the variable myName.
Now if following is added:
```javascript
myName='Charya';
```
This code throws the following error when you run your code:
```TypeError: Assignment to constant variable.```
JavaScript threw an error because you assigned a new value to a constant variable. Constant variables, as their name implies, are constant — you cannot assign them a different value.

### variable: let
However unlike variable const ,variable let can be reassigned.
Let us take an example:
```javascript
let meal = 'Enchiladas';
console.log(meal);  // output: Enchiladas
meal = 'Tacos';
console.log(meal);  // output: Tacos
```
### Undefined
What happens if you create a variable, but don't assign it a value?
JavaScript creates space for this variable in memory and sets it to undefined. JavaScript assigns the undefined data type to variables that are not assigned a value.
```javascript
let notDefined;
console.log(notDefined); //output: undefined
```
