<h1 align = "center">Pub/Sub Pattern</h1>
<h2> Introduction: </h2>
<p style = "text-indent: 10%">A lot of times our modules want to interact with certain modules, like button press on one module should activate some function in other module. We previously saw that to do this we have to call the activating function of second module from the first module. This becomes tedious if we have 100s of activating functions from different modules. This is when the pub/sub pattern is used.</p>
<p style = "text-indent: 10%">Here, we make another module which acts as a mediator between the modules. It stores all the events. All the modules either emit/publish an event or subscribe to an event. When a modules subscribes to an event it adds a callback function which is called when the event is created. When a module emits an event the mediator module executes all the callbacks that the modules have registered by subscribing.</p>

![Pub/Sub Pattern](https://github.com/Ankit-22/Javascript-notes/blob/master/Modular-Javascript/pubsub.png "Working of Pub/Sub Pattern")

In the image you can see that one module is sending the event (emit) and others that have subscribed to the event get called by the pubsub module.

<h2> Code: </h2>
<p style = "text-indent: 10%">Below is an implementation of pubsub module.</p>

```js

	// This module serves as a mediator for all events
var pubsub = {

	// An event subscribes
	on: (eventName, func) => {

		// If events object is not defined, define it
		if(!this.events)
			this.events = {};

		//Add the function to event's list by the name of eventName
		this.events[eventName] = this.events[eventName] || [];
		this.events[eventName].push(func);
	},

	// An event unsubscribes
	off: (eventName, func) => {

		//If there is an event loop in its list and find the function and remove it
		if(this.events[eventName])
			for( var index in this.events[eventName] )
				if(this.events[eventName][index] === func) {
					this.events[eventName].splice(index, 1);
					break;
				}
	},

	// An event is published
	emit: (eventName, data) => {

		// If event is present loop through it and execute the functions on its list with the data.
		if(this.events[eventName])
			this.events[eventName].forEach( func => {
				func(data);
			});
	}
}

```

<h2>Example:</h2>
<p style = "text-indent: 10%">Try to convert the previous example in pubsub pattern. Try to do it on your own first.</p>

Solution:
```js

// Include the above pubsub code.

//Hello Module
var hello = ( () => {

	var sayHello = () => {
    
    	alert("hello");
        
    }
    
    // Subscribe to 'HelloEvent' and register the callback sayHello
    pubsub.on("HelloEvent", sayHello);
    
})();

// Button Module
var button = ( () => {

	var button = document.getElementById('button');
    
    //Add Listener
    button.addEventListener('click', e => {
    
    	// This emits the HelloEvent when button is pressed
    	pubsub.emit("HelloEvent");
        
    });
})();

```

In the above code if there are 100 modules that want to do something on HelloEvent, they can just subscribe by pubsub.on method and there is no need to write the callbacks in Button Module. There can be multiple events as well and same module can subscribe to many events.

<h2>There are more ways:</h2>
<p style = "text-indent: 10%">We made our modules.. Great.. But what if we want more copies of the same module? Ex: We made a human module which has walk() function, and we want to make a musician module which has all the properties of human and has some of its own methods like playMusic(). We want another module cricketer which has all properties of human and has its own methods like takeCatch().This type of hierarchy among modules is called inheritance. Also if we want to make 100 copies of the same module, we will have to rewrite every copy. This type of copying of a module is called as Instantiation. We cannot do this with previously seen patterns we will have to write same code again and again. To avoid this, we use classical inheritance pattern.</p>