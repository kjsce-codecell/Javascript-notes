<h1 align = "center">Classical Inheritance</h1>
<h2> Introduction: </h2>
<p style = "text-indent: 10%">Prototypal inheritance is just like Classical Inheritance. Here, instead of using functions we use objects to create modules. And we use Object.create function to create an object.</p>

<h2>Example</h2>
<p style = "text-indent: 10%">Lets take the previous example.</p>

```js
var Animal = {

	// This is definition for saySpecies
	saySpecies: function() {
    	console.log(this.species);
    }
    
}

var Dog = Object.create(Animal);
Dog.species = "Dog";
Dog.saySpecies(); // Dog

Dog.sayBreed = function() {
	console.log(this.breed);
}

var Pug = Object.create(Dog);
Pug.breed = "Pug";
Pug.sayBreed(); // Pug

// We can instantiate a Dog using Animal and a Breed using Dog.
// But we have to set species and breed from outside.
// A better way is to create a constructor inside the object
```
Constructor Example:
```js

// The Animal Module
var Animal = {

	// This function creates an instance of this object and adds the properties provided
	constructor: function(values) {
    
    	// Make an instance of Animal class
    	var instance = Object.create(this);
        
        // Add all the key attributes to the object instance
        Object.keys(values).forEach( function(key) {
        	instance[key] = values[key];
        });
        
        // Return the instance
        return instance;
    },
    
    // Say Species
    saySpecies: function() {
    	console.log(this.species);
    }
};

// Create a Dog object with species as Dog. Note we can give more properties, but we just require the species property.
var Dog = Animal.constructor({species: "Dog"});
Dog.saySpecies();

// Add constructor to Dog module so that we can make instances of Dog module
Dog.constructor = function(values) {
	var instance = Object.create(this);
    Object.keys(values).forEach( function(key) {
    	instance[key] = values[key];
    });
    return instance;
};

// Add its own function to Dog module
Dog.sayBreed = function() {
	console.log(this.breed);
};

// Call the constructor to make an instance of Dog module
var Pug = Dog.constructor({breed: "Pug"});
Pug.sayBreed();

```

This is a lot cleaner way to do instantiation and inheritance in javascript. Here also, we can override some previous defined methods.

So these were the techniques to do modular programming in javascript.
