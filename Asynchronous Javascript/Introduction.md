<h1 align="center"> Asynchronous JavaScript</h1>

## What is Asynchronous JavaScript?

 The difference between synchronous code and asynchronous code is that synchronous code executes from the top of a code block to the bottom in a sequencial order in which it was written.

 Consider the following block of code:

 ```JavaScript
console.log('Hello!'); // Prints Hello!
console.log('World'); // Prints World
 ```

This block of code prints out the string 'Hello!' and then the string 'World' which is the same order in which it was written.

Now consider this code:
```JavaScript
// Say "Hello."
console.log("Hello.");
// Say "Goodbye" two seconds from now.
setTimeout(function() {
        console.log("Goodbye!");
}, 2000);
// Say "Hello again!"
console.log("Hello again!");
```

If you are only familiar with synchronous code, you might expect the code above to behave in the following way:

Say "Hello".
Do nothing for two seconds.
Say "Goodbye!"
Say "Hello again!"

But setTimeout does not pause the execution of the code. It only schedules something to happen in the future, and then immediately continues to the next line.

Say "Hello."
Say "Hello again!"
Do nothing for two seconds.
Say "Goodbye!"

This code needs to be asynchronous because **requesting data from the server could take a considerable amount of time**. As such we do not want such a slow operation to block the execution of our entire script when we could probably be doing other things in the meantime **(in our case we checked the if any other code was left and we printed World as soon as the requesting part was given to handle by the server)**.

*To get asynchronous behavior for Javascript. **AJAX** is used*.

## AJAX and It's benefits

>AJAX stands for Asynchronous JavaScript And XML.
>AJAX is not a programming language.
>AJAX is a misleading name. AJAX applications might use XML to transport data, but it is equally common to transport data as plain text or JSON text.

*AJAX just uses a combination of:*
- A browser built-in XMLHttpRequest object (to request data from a web server)
- JavaScript and HTML DOM (to display or use the data)

AJAX allows web pages to be updated asynchronously by exchanging small amounts of data with the server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

Classic web pages, (which do not use AJAX) must reload the entire page if the content should change.

#### *Benefits*

- Speed
Reduce the server traffic in both side request. Also reducing the time consuming on both side response.

- Interaction
AJAX is much responsive, whole page(small amount of) data transfer at a time.

- Asynchronous calls
AJAX make asynchronous calls to a web server. This means client browsers are avoid waiting for all data arrive before start the rendering.

- Form Validation
This is the biggest advantage. Form are common element in web page. Validation should be instant and properly, AJAX gives you all of that, and more.

- Bandwidth Usage
No require to completely reload page again. AJAX is improve the speed and performance. Fetching data from database and storing data into database perform background without reloading page.
