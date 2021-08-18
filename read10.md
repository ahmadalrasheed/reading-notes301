## Understanding the JavaScript Call Stack

![](https://miro.medium.com/max/638/1*CCHexfHNCNo-f8aw3rbRew.jpeg)

### What is a ‘call’?
***function invocation***
### How many ‘calls’ can happen at once?

***It is `single-threaded`. Meaning it can only do one thing at a time.***

### What does LIFO mean?
***When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.***

### Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

**HERE IS THE EXAMPLE BELOW**

>function firstFunction(){
  console.log("Hello from firstFunction");
}
function secondFunction(){
  firstFunction();
  console.log("The end from secondFunction");
}
secondFunction();

![](https://cdn-media-1.freecodecamp.org/images/oEp65Ec9CD4CnL7t0uSPoyzrkA1i1BR-Ij1n)
### What causes a Stack Overflow?

***A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.***

Here is an example:

>function callMyself(){
  callMyself();
}
callMyself();

***The callMyself() will run until the browser throws a “Maximum call size exceeded”. And that is a stack overflow.***

## JavaScript error messages
![](https://www.tutsmake.com/wp-content/uploads/2020/05/Types-of-Errors-In-JavaScript.jpeg)
### What is a ‘refrence error’?

***This is as simple as when you try to use a variable that is not yet declared you get this type os errors.***

>`console.log(foo) // Uncaught ReferenceError: foo is not defined`


### What is a ‘syntax error’?

***I know it’s in the name of the errors, but like it says itself, this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.***

>`JSON.parse( {'foo': 'bar'} ) // Uncaught` `SyntaxError: Unexpected token o in JSON at` `position 1`

### What is a ‘range error’?

***Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.***

>`var foo= []`
`foo.length = foo.length -1` // Uncaught `RangeError: Invalid array length`
### What is a ‘tyep error’?

***Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.***

### What is a breakpoint?

***The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.***

### What does the word ‘debugger’ do in your code?


***The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.You can run the debugger by pressing F5 or pressing the green play button.***
