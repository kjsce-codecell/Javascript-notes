# DOM
When a webpage is loaded, the browser creates a **D**ocument **O**bject **Mo**del, as in it creates a tree to represent and access all the contents easily.
Here's an example-
![The DOM](https://www.w3schools.com/js/pic_htmltree.gif)
Anyone with basic html knowledge, can relate to this diagram, the html being the root element, and all the other elements or objects lying under it.
So, basically, the DOM is a **BIG** object which represents the whole HTML page, to see it live in action, press- Ctrl + Shift + J, which shall open the console tab, now type in- document in the tab, and press enter, and check the output !
*PS: If you know how to imagine trees using bracket syntax, this will be much easier*

Now, once you know all this, Javascript enables us to interact with all these elements, using javascript we can -
- change HTML elements
- change HTML attributes
- change CSS attributes
- even remove HTML elements
- also add new HTML elements
- even react to HTML events

So, let's try to do some magic on HTML using outr knowledge of Javascript
There are basically two types of stuff you can do while manipulating the DOM
- you can either alter the structure of the DOM
- or make changes to the exisiting structure. 

First of all, to make changes to an object from the DOM, you need to select that object, there are 3 basic ways to select an object or an element of the DOM-
- by tag name, example: div,p,a, selects all the elements having that tag
- by class name, selects all the elements with that class
- by ID name, selects the unique element having that ID

| Method | Selects By |
| ------ | ---------- |
| document.getElementById(*id*) | selects by ID |
| document.getElementsByTagName(*name*) | selects by tag name |
| document.getElementsByClassName(*name*) | selects by class name |

Also, if you know how to select elements by CSS, you can use these 2 syntaxes as well, where **.classname**, selects by class name, **#id_name** selects by id, and **tag_name** selects by tag.
This is particularly helpful when you need to use a combination of those selectors, so back to the syntax for these:
- document.querySelector(*query*), returns a single first element, matching the query or null
- document.querySelectorAll(*query*), returns a list of elements matching the query or null

Now once you have selected an HTML element, you can make a whole lot of changes to it, by selecting a certain attribute or property and changing it's value, example:
- element.attribute = new value
- element.setAttribute(attribute, value)
- element.style.property = new style

These were all to change the CSS or appearance related to that element, now, if you want to change the contents of that element, you can do:
- element.innerHTML =  new html content

Now, that we have delt with changing the appearances of the elements, let's see how to change the appearances of the DOM, as in create or remove objects from the DOM:
- document.createChild(element)
- document.appendChild(element)
- document.removeChild(element)

Here is how one can write hello world in html, with dom manipulation onyl, you can try this in a new blank tab, by going to- about:blank and typing out the following code-
![hello_world_html](https://image.prntscr.com/image/osE0GMuMQYCvKOcV-7E4xw.png)
For the lazy:
``` javascript
//inspect the dom
document
var body = document.body
var heading = document.createElement("h1")
body.appendChild(heading)
//inspect the dom again, h1 added !
document
document.querySelectorAll("h1").innerHTML="Hello World"
//inspect the dom, and hello world added !
document
```
Now, to make the heading red, you can type -
``` javascript
heading.style.color="red"
```

Now that we have looked into, changing properties of DOM objects and changing the structure of the DOM as whole, let's delve a little into interacting with the DOM objects, this can be achieved by event handlers.

So, what is an event?
As the name suggests, event is something that happens or take place, with respect to DOM, events can be clicking on the button, or hovering over a heading, these were a few of the events.
Now, to handle these events there are event listeners, which bind the selected DOM object to the event, and the function that takes place when that event is encountered. Example -

``` javascript
element.addEventListener("click", function(){ alert("Hello World!"); });
```
The above piece of code, alerts "Hello World!" anytime the particular selected element is clicked.
Basic syntax of it is -
``` javascript
element.addEventListener(event, function, useCapture);
```
Where-
- event, is the aprticular event, which needs to be handled, example hover, click
- function, is the action that takes place once the event is triggered
- useCampture, is an optional parameter, and a little advanced too, it is a boolean to specifiy whether to allow event bubbling or event capture

The above example, we could have wrote as-
``` javascript
function sayHello(){
    alert("Hello World!");
    };
element.addEventListener("click", sayHello);
```
Here we are explicitly defining a function, whereras above, we used anonymous functions.
Anonymous functions are use when you don't need to reuse the same function, so you just write the function in place.
Whereas, when you need to use the same function again and again, we define the function explicitly, and then use it.

Also, a single event on a single element, can trigger multiple functions, but need to state event handler for each function, example -
``` javascript
element.addEventListener("click",sayHello);
element.addEventListener("click",sayHelloAgain);
```
Here, both sayHello and SayHelloAgain will be triggered. 