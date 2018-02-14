<h1 align="center"> Asynchronous JavaScript</h1>

## Understanding Asynchronousity
Before diving into the code to implement asynchronous javascript. It is very important to understand some concepts which will help in understanding what is happening behind the scenes.

![image](https://cdn-images-1.medium.com/max/1000/1*FA9NGxNB6-v1oI2qGEtlRQ.png)

The example image above is the representation of Chrome’s JavaScript environment.

JavaScript is popularly known to be a **single-threaded non-blocking asynchronous** concurrent language with a call stack, event loop, a callback queue and some APIs. But from the above figure it can be seen that V8(The JavaScript Engine only seems to have only has a call stack and a heap).

As it turns out, the JavaScript runtimes (like V8) only have a heap for memory allocation, and a stack for sequencial execution. The other things are the **Web APIs in the browser, for instance the setTimeout, AJAX, DOM etc.** 

But still the biggest question is how can Javascript be single threaded and perform more than one tasks(asynchronously) at a same time. 

>The answer of the asynchronous behavior lies in the figure above


*Lets Understand the important components present in the figure above:* 

#### *Runtime Engine(Call Stack and Memory Heap)*
So let’s start with the call stack. What is this? Well, as we already know by now, JavaScript is single-threaded, which means it has a single call stack, which in turn means that it can do **one thing at a time.** Stack is used because the call stack is fundamentally a data structure which keeps a record of where in the program is the execution going on. **When the execution steps into a function, it is pushed on to the stack, and when a function returns after completion, it is popped off the stack, so we have to get back to the place from where this function call was made.** Thus naturally, a stack data structure makes complete sense. Anyway, getting back to JavaScript, it’s the same thing, and whenever the program throws some error, we can see the call stack in the browser console i.e The function calls still present in the stack to figure out where the code went wrong. Heap is used for memory management and doesn't play much of vital role in asynchronous behavior.

#### *Web API's*
DOM requests , ajax requests and Timeout requests are some of the API's provided by the browser which runs the request given to them and pass it on to the callback queue once the request has been processed.

#### *Callback Queue and Event Loop*
Callback queue consists of all the requests that has been processed by the API's. Once the call stack gets empty and there are no actions being performed, event loop takes the first event from callback queue and pass it on to the call stack.

#### *Example using setTimeout*

Consider the following example:

```JavaScript
console.log('Hi');

setTimeout(function cback() {
    console.log('Rabbit!');
}, 3000);

console.log('Tortoise!');
```

Let's see what happens in this code through visualization:

1. Step into the console.log('Hi'); function, so it’s pushed onto the call stack

2. console.log('Hi'); returns, so it is popped off the stack **(Hi is printed)**
3. Step into the setTimeout function, so it’s pushed onto the call stack
**setTimeout is a part of the Web API, so the Web API handles that and sets a timer for 3 seconds**
4. The script continues, stepping into the console.log() function in line 7, pushing it onto the stack 
5. console.log() of line 7 returns, so it’s popped off **(Tortoise! is printed)**
6. The 3 second timer completes, so the callback cback() moves to the callback queue
7. The event loop checks if the call stack is empty. If it were not empty, it would wait. But because it is empty, the cback() is pushed from the callback queue onto the call stack.
8. console.log() of line 4 is defined in cback(), so it is pushed onto the stack and when it returns, it’s popped off the call stack.**(Rabbit! is printed)**

*Note:* 
setTimeout with the second argument as 3000 doesn’t mean that the callback function will be called after 3 seconds. It means that it will be called whenever the call stack is empty after 3 seconds, which can also be never. So, it kind of means that 3000 seconds is the minimum amount of time in which it would be called.

This being a very basic example of asynchronous Javascript it might still be difficult to grasp the importance of asynchronous Javascript because in this example the increase in the efficiecy of the system would be very negligible but in case of bigger systems, the amount of requests would be really high. So instead of javascript call stack handling all the requests alone , the Web API's would be a big help for the call stack to carry out only those tasks which Web API's won't be able to do. Thereby , providing user a Fluid UI and faster loading of page and handling of requests.