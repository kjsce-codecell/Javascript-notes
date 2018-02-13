<h1 align = "center">Object Literal Pattern</h1>
<h2> Introduction: </h2>
<p style = "text-indent: 10%">Revealing Module Pattern is implemented using self evaluating functions in javascript. Self evaluating functions are anonymous functions that are executed right after they are declared.</p>

<h2>Example:</h2>

<p style = "text-indent: 10%">Consider the example from the previous pattern. Let us say we do not want anyone to edit breed of the dog.

```js

var dog = ( function() {
	var breed = "pug";
    
    // This function returns the value of breed variable
    var getBreed = function() {
    	return breed;
    }
    
    var bark = function() {
    	// Bark Code Here
    }
    
    var run = function() {
    	// Run Code Here
    }
    
    // Now no one can access any of the variables from outside.
    
    // But we want then to be able to access functions but not the breed variable
    
    // So we simply return functions to which we want to provide access from outside
    
    return {
    	getBreed: getBreed,
        bark: bark,
        run: run
    };
   	
})();

// Now we can do,

dog.bark();
dog.run();
dog.getBreed();

// But no one can change the value of breed

dog.breed = "bull dog";
// This will not change the actual value of breed

dog.getBreed(); // Still gives pug

```

Here we tackled the problem of invalid access.

<h2>Exercise: </h2>
Write two modules, one that has a function that alerts hello and the other that has a button which tells the first module to alert hello.

Simple Enough?
```js
var hello = ( function() {

	var sayHello = function() {
    
    	alert("hello");
        
    }
    
    return {
    
    	sayHello: sayHello
    
    }
    
})();

var button = ( function() {

	var button = document.getElementById('button');
    
    button.addEventListener('click', function(e) {
    
    	hello.sayHello();
        
    });
})();

// This will alert hello when the element with id 'button' will be clicked

```

Okay, Now assume there are a 100 modules who want to perform 100 different tasks when the button is pressed. For this the button module should know about all the 100 modules and should execute all functions required from the 100 modules. This is not ideal as we will write 100s of lines of code and also our module become interdependent on each other, if button does not call hello.sayHello(), it will not work.

To solve this problem we use a pattern called as Pub/Sub pattern.
