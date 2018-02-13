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

• **Strings** — Any grouping of keyboard characters (letters, spaces, numbers, or symbols) surrounded by single quotes ('Hello') or double quotes ("World!"). In the example above, 'New York City' is a string.

• **Numbers** — Any number, including numbers with decimals: 4, 1516, .002, 23.42. In the example above, 40.7 is a number.

• **Booleans** — Either true or false, with no quotations. In the example above, true is a boolean.

• **Null** — Can only be null. It represents the absence of value.

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
### Variable: var
The variable statement declares a variable, optionally initializing it to a value.
```javascript
var x = 1;
```
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

### Variable: let
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
## Loops
JavaScript loops are used to repeatedly run a block of code - until a certain condition is met. When developers talk about iteration or iterating over, say, an array, it is the same as looping. JavaScript offers several options to repeatedly run a block of code, including while, do while, for and for-in.
### While Loop
```javascript
var sum = 0;
var number = 1;
while (number <= 50) {  // -- condition
  sum += number;        // -- body
  number++;             // -- updater
}
alert("Sum = " + sum);  // => Sum = 1275
```
The condition is first evaluated. If true, the block of statements following the while statement is executed. This is repeated until the condition becomes false. 
### For Loop
```javascript
var sum = 0;
for (var i = 1; i <= 50; i++) {
   sum = sum + i;
}
alert("Sum = " + sum);    // => Sum = 1275
```
It consists of three parts, separated by semicolons. The first is the initializer (var i = 1) which initializes the loop and is executed only once at the start. The second is a test condition (i <= 50). When a conditional expression evaluates to true, the body of the loop is executed. When false, the loop terminates. The third part is an updater (i++) which is invoked after each iteration. The updater typically increments or decrements the loop counter.
## Conditional Statements
Very often when you write code, you want to perform different actions for different decisions. You can use conditional statements in your code to do this.

In JavaScript we have three conditional statements:

1) if statement - use this statement if you want to execute a set of code when a condition is true
2) if...else statement - use this statement if you want to select one of two sets of lines to execute

### If 
The if statement is the fundamental control statement that allows JavaScript to make decisions and execute statements conditionally.
```javascript
if (expression){
   Statement(s) to be executed if expression is true
}
```
### If Else
The 'if...else' statement is the next form of control statement that allows JavaScript to execute statements in a more controlled way.
```javascript
if (expression){
   Statement(s) to be executed if expression is true
}

else{
   Statement(s) to be executed if expression is false
}
```
Here JavaScript expression is evaluated. If the resulting value is true, the given statement(s) in the ‘if’ block, are executed. If the expression is false, then the given statement(s) in the else block are executed.
## Arrays
The Array object lets you store multiple values in a single variable. It stores a fixed-size sequential collection of elements of the same type. An array is used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type.
```javascript
var fruits = [ "apple", "orange", "mango" ];
```
### ForEach
Apply the passed function to each element in the list or any iterable for that matter.
```javascript
var array1 = ['a', 'b', 'c'];
array1.forEach(function(element) {
  console.log(element);
});
//a
//b
//c
```
## Functions
A function is a group of reusable code which can be called anywhere in your program. This eliminates the need of writing the same code again and again. It helps programmers in writing modular codes. Functions allow a programmer to divide a big program into a number of small and manageable functions.
### Function Definition
Before we use a function, we need to define it. The most common way to define a function in JavaScript is by using the function keyword, followed by a unique function name, a list of parameters (that might be empty), and a statement block surrounded by curly braces.
```javascript
function functionname(parameter-list)
      {
         statements
      }
```
### Return Statement
A JavaScript function can have an optional return statement. This is required if you want to return a value from a function. This statement should be the last statement in a function.
```javascript
function concatenate(first, last)
         {
            var full;
            full = first + last;
            return full;
         }
         
         function secondFunction()
         {
            var result;
            result = concatenate('Donald', 'Duck');
            document.write (result );
         }
```
