<h1 align = "center">Classical Inheritance</h1>
<h2> Introduction: </h2>
<p style = "text-indent: 10%">We want to make multiple copies of the same module (Instances) and we also want to copy properties of one module in other modules (Inheritance). These features are provided by classical inheritance pattern. It uses functions and a javascript property called as prototype.</p>

<h2>Example</h2>
<p style = "text-indent: 10%">Make a module named animal, add saySpecies method and an attribute species name. Then make 3 animals with different species name.</p>

```js

var Animal = function(name) {
	this.name = name;
}

// The Animal function is used to set the value of name property in the objects that are created
// The Animal function is called constructor

// Now we want to add saySpecies method. We don't want to add the method to each object, so we use prototype property in javascript.
// The prototype property is just what variables or functions does an object contain.
// Currently our prototype is empty.

Animal.prototype.saySpecies = function() {
	console.log(this.name);
};

// Now we added the saySpecies function to Animal prototype.

var human = new Animal("Human");

console.log(human.name) // Prints Human

var cat = new Animal("Cat");

cat.saySpecies(); // Prints Cat

var dog = new Animal("Dog");

// Add it's own method to dog
dog.bark = function() {
	console.log("bow-wow");
};

dog.bark(); // New method
dog.saySpecies() // Old method

// But what if we want a Pug module to inherit from dog? We will have to convert dog into a module as well. This is Inheritance.

```

Here we made different instances of Animal module. Lets see inheritance.
Let us make a module Dog that inherits from Animal module.

```js

// We will use a function called as inherits.

function inherits (ctor, superCtor) {
	ctor.super_ = superCtor;
    ctor.prototype = Object.create(superCtor.prototype, {
    	constructor: {
        	value: ctor,
            enumerable: false,
            writable: true,
            configurable: true
        }
    });
};

// This function inherits module ctor from module superCtor.

// Let us define the Dog module

var Dog = function(breed) {
	
    // It calls the super constructor (The Animal Constructor) with 'this' object and species name
	Dog.super_.call(this, "Dog");
    
    // Breed is own property of the dog module.
    this.breed = breed;
}

// We call the inherits function to do inheritance

inherits(Dog, Animal);

Dog.prototype.sayBreed = function() {
	console.log(this.breed);
}

var pug = new Dog("Pug");
pug.saySpecies() // Prints Dog
pug.sayBreed() // Prints Pug


// Here we added methods of Animal module to Dog module.
```

We can also override the inherited method if we want.

```js

Dog.prototype.saySpecies = function() {
	console.log("Doggo");
}

var doggo = new Dog("Bull Dog");
doggo.saySpecies() // Prints Doggo


```

<h2>Next?</h2> This was one way to do Inheritance and Instantiation in javascript. There is one other way to do it. It is called Prototypal Inheritance.
