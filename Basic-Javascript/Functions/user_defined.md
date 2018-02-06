<h1 align="center">User Defined Functions</h1>

### Defining a Function

>To define a JavaScript function, use the function keyword, followed by a name, followed by a set of parentheses ().The code to be executed by the function is placed inside curly brackets {}.

**Example**

```
function hello() {   
  //code to be executed
}
```

### Calling a Function

>To call a function, start with the name of the function, then follow it with the arguments in parentheses.

**Example**

```
function hello() {
  alert("Hello World!");
}

hello();
//Alerts "Hello World!"
```

### Function Parameters

>Function parameters are the names listed in the function's definition.

**Syntax**

```
functionName(param1, param2, param3) {
   // some code
}
```
>If a function is called with missing arguments (fewer than declared), the missing values are set to **undefined**, which indicates that a variable has not been assigned a value.

### Function Return

>Use the return statement to return a value.

**Example**

```
function add(a, b) {
   return a + b;
}

var x = add(5, 6);
// x equals 11
```

>If you do not return anything from a function, it will return **undefined**.
