<h1 align = "center">Modular JavaScript</h1>
<h2> Why modules?</h2>
<p style = "text-indent: 10%">You might have heard, "Anyone can write code that machines can understand, good programmers write code that humans can understand".</p>

>You can write a working code easily, but you want to understand it later even after a month or an year.

>You also want other people to understand it easily.

>Also you don't want any other future code to break your previously written precious code.

>And you want to use your code more than once. Won't be good if you rewrite the same logic again and again.

>In enterprises many people work on the same project. One part of code can interfere with others.

<h2>How can modules help?</h2>

<p style = "text-indent: 10%">Modules are an independent part of code that can be reused and is easily understandable. The "independent" part is important. This definition assures that modules do not interfere with each other and can be reused if required. Following are paradigms of modular code.</p>

>*	Modules are self-contained
>*	One module must perform only one task
>*	Separation of concerns
>*	DRY (Don't Repeat Yourself) code
>*	Efficient usage of processing
>*	Prevention of memory leaks

<h4>Self-Contained?</h4>

<p style = "text-indent: 10%">This means every thing a module needs must be inside the module. That means a module should not access values from outside of it's scope. Well.. This puts an end to our favorite "global variables".</p>

<h4>1 task per module..</h4>

<p style = "text-indent: 10%">This one is pretty clear, if a module does more than one task, it must be split. But what is a task? Well, it depends a lot on the use case of the code. You should think what are the tasks that are independent and try to break them into small pieces, so that they can be reused and can be debugged easily.</p>

<h4>Separation of concerns..</h4>

<p style = "text-indent: 10%">This means a clear division and grouping of each line of code with respect to the functionality of that line. Code that performs same type of task should be written together. We are already doing that at task level, by making modules. Now we need to do that with each line of code.</p>

<h4>DRY code:</h4>

<p style = "text-indent: 10%">As mentioned earlier breaking our code into smaller modules can be helpful as this independent part of code can now be used anywhere. So use it if it is available.</p>

<h4>Efficient usage of processing</h4>

<p style = "text-indent: 10%">Many times we require to do same processing in the same module many times, like searching the DOM for some element. Such processing must be done only once and it should be reused.</p>

<h4>Prevention of Memory Leaks</h4>

<p style = "text-indent: 10%">Removing global variables solves this problem to some extent, but there are other type of memory allocated for a module, such as event listeners, etc. These are not deleted even after the object of the module is deleted. This can cause memory leaks. So a good module must unbind every listener tied to it before killing an object.</p>

<h2> How to write modules in JavaScript?</h2>

<p style = "text-indent: 10%">Unlike Java and other famous languages JavaScript does not provide inbuilt support for modular programming. Don't be upset, there are some workarounds that can be used to write modular code in JavaScript.</p>

>*	Object Literal Pattern
>*	Revealing Module Pattern
>*	Pub/Sub Pattern
>*	Classical Inheritance
>*	Prototypal Inheritance
