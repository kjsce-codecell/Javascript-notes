<h1 align = "center">Object Literal Pattern</h1>
<h2> Introduction: </h2>
<p style = "text-indent: 10%">JavaScript has support for javascript objects. We can use them to write our modules. An object has a property name and a value. We can name our functions and variables as a key and store their values.</p>

<h2> Example: </h2>

<p style = "text-indent: 10%">Consider a module named Dog. It has a property breed can perform two operations, bark and run.
A simple javascript to implement the above will include functions and a global variable for the property.</p>
Like,

```js
var breed = "pug";

function bark() {
	
    // Bark Code Here

}

function run() {
	
    // Run Code Here
    
}

```

<p style = "text-indent: 10%">Suppose we want to add another dog with different bark method, we will have to change name of functions and variables.</p>

Using objects, it can be written as:

```js

var dog = {

	breed : "pug",
    
    bark: function() {
    	
        // Bark Code Here
        
    },
    
    run: function() {
    
    	// Run Code Here
        
    }

};

var dog2 = {
	
    breed : "bull dog",
    
    bark: function() { 
    	// Some other Bark Code Here 
    },
    
    run: function() { 
    	// Some Other Run Code Here 
    }
};

dog.bark();
dog2.bark();

```

<p style = "text-indent: 10%">Here we were able to write both bark function without changing the names of the function. Naming is important as it makes the code readable and easy to understand.</p>

<h2> How helpful is it? </h2>

>No global variables
>
>One module one task
>
>Separation of concerns
>
>DRY code
>
>Efficient usage of processing: We can store the processed values in a key so that we do not have to do the same processing again.
>
>Prevent memory leak: We can make a function that unregisters all listeners when the object is killed.

Example:
```js

var efficientCode = {
	
    aDOMObject : document.getElementById('myObject'),
    
    printObject: function() {
    
    	console.log(this.aDOMObject);
        // Use the saved value
        
    },
    
    clickFunc: function(e) {
    
    	console.log("clicked");
        
    },
    
    addListener: function() {
    
    	this.aDOMObject.addEventListener('click', this.clickFunc);
        
    },
    
    destroy: function() {
    	this.aDOMObject.removeEventListener('click', this.clickFunc);
        // Remove the listeners when destroyed to avoid memory leak
    }
};

```

<h2> One Problem..</h2>

We can very well implement our modules using this pattern. But what if we do not want other people to access all our inner variables? Here anyone can change your module variables from outside. This can lead to security breaches. We will see how this is fixed in next pattern (Revealing Module Pattern).
