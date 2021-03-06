# Closures

### From MDN:
A closure is the combination of a function bundled together (nested) with references to its surrounding scope. 
In other words, a closure gives you access to an outer function’s scope from an inner function.

How do the concepts of scope and higher-order functions relate to closures in JavaScript?
* nested function 

## Why use closures?
We can use closures to create hidden (private) data

## Examples
- Secret message
```js
function outer(){
  let message = "I am the imposter!";

  return function(){
    console.log(message)
  }
  
}

//how do we get access to 'message' from out here

//a copy of the inner function
let anotherFunction = outer();
anotherFunction();
```

- ID (counter) generator


- Create a counter or *multiple counters*
 - every time to invoke
 - re-creating and reclarding those variables 

```js

function counterCreator(noun){
  let id = 1; //NOT globally scoped

  return function (){
    console.log(`${id} ${noun}`); //is accessible here
    id += 1;
  }
}

//returning a function
let annsCounter = counterCreator("bird");


// return another copy of that function 
let reubensCounter = counterCreator("pony");


//return a third copy of that function
let mayaCounter = counterCreator("dog");




```

- Pre-setting a variable