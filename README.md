# ReferenceError-x-is-not-defined

When JavaScript engine can't parse the file because I made an error in my code.  It cannot even make it past the creation phase.  

More specifically, I forgot to define the variable _r_ before declaring it.
When this occurs, JavaScript will show its displeasure by throwing this error, indicating that the referenced object was not previously defined.

I first came across this error studying the concepts of declaration and definition. 

I expect this error will be a real pain becuase the message isn't very helpful.  It tells me there's something missing, but always tells me it's at the end of the file.
I'll have to go back through the WHOLE FILE to find where I made my mistake.

___

## Code where I first found the error

```js
r = 'r'

// comments
```


___

## The Fix

Well, just had to define it before initialising.

Possible solutions:

```js
var r = 'r';
```

```js
let r = 'r';
```

```js
const r = 'r';
```

___

## Messages from different runtimes

 * Google Chrome (V8 Engine)
  Actually, no message, because I did not activate 'strict mode'
  
  However, it did throw an error using [PythonTutor](http://www.pythontutor.com/javascript.html#code=r%3D'r'&curInstr=1&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
 
___

## More instances

```js
let x = 0;
	{
	  x++;
	  let x = 0;
	  x++;
  }
```
statements inside block scope cannot 'reach' global scope's parameters.
[PythonTutor](http://www.pythontutor.com/javascript.html#code=let%20x%20%3D%200%3B%0A%7B%0A%20%20x%2B%2B%3B%0A%20%20let%20x%20%3D%200%3B%0A%20%20x%2B%2B%3B%0A%7D&curInstr=2&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)

ongoing.  (almost) every time you come across it, copy-paste the code into this repo. if the code is long you can put it in a separate file.

___

## helpful links

[Airbrake.io](https://airbrake.io/blog/javascript-error-handling/referenceerror-x-is-not-defined)

___

## review

I learned that I should define a variable first and then initialise it. Some JS Engines actually 'dodge' this problem by defining it for us, but on 'strict mode' it throws this error.

