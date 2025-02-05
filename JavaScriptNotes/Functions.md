# Functions in JavaScript

**Syntax of a Function:**

Here is the basic syntax of a JavaScript function.
```JavaScript
function nameOfFunction (parameters) {
    // Code goes here
    return value;
}
```
**Example Code:**

```JavaScript
function favoriteAnimal(animal) {
    return animal + " is my favorite animal!";
}

console.log(favoriteAnimal('Goat'));
```

In JavaScript, **parameters** are the items listed between the parentheses () in the function declaration.
Function **arguments** are the actual values we decide to pass to the function.

![Parameters vs. Arguments](param_args.png)


## Default Parameters

If a function is called, but an argument is not provided, then the corresponding value becomes `undefined`.

If you're writing a function and want to support optional parameters, you can specify default values by adding `=` after the name of the parameter, followed by the default value:

```js
function hello(name = "Chris") {
  console.log(`Hello ${name}!`);
}

hello("Ari"); // Hello Ari!
hello(); // Hello Chris!
```

## Alternative Default Parameters

Sometimes it makes sense to assign default values for parameters at a later stage after the function declaration.

We can check if the parameter is passed during the function execution, by comparing it with `undefined`:

```js
function showMessage(text) {
  // ...

  if (text === undefined) { // if the parameter is missing
    text = 'empty message';
  }

  alert(text);
}

showMessage(); // empty message
```

…Or we could use the `||` operator:

```js
function showMessage(text) {
  // if text is undefined or otherwise falsy, set it to 'empty'
  text = text || 'empty';
  ...
}
```

## Anonymous functions

We can create a function that does not have a name.
These type of functions are called **Anonymous functions**.

```js
(function () {
  alert("hello");
});
```

Anonymous functions are used when a function expects to receive another function as a parameter.
In this case, the function parameter is often passed as an anonymous function.

**Anonymous function example:**

Consider this block of code:
```js
function logKey(event) {
  console.log(`You pressed "${event.key}".`);
}

textBox.addEventListener("keydown", logKey);

```

Instead of defining a separate `logKey()` function, you can pass an anonymous function into `addEventListener()`:

```js
textBox.addEventListener("keydown", function (event) {
  console.log(`You pressed "${event.key}".`);
});
```

## Arrow functions
If you pass an anonymous function like this, there's an alternative form you can use, called an arrow function. Instead of `function(event)`, you write `(event) =>`:

```js
textBox.addEventListener("keydown", (event) => {
  console.log(`You pressed "${event.key}".`);
});
```
## Important concepts

**Local Variables**

A variable declared inside a function is only visible inside that function.

```js
function showMessage() {
  let message = "Hello, I'm JavaScript!"; // local variable

  alert( message );
}

showMessage(); // Hello, I'm JavaScript!

alert( message ); // <-- Error! The variable is local to the function
```
**Outer Variables (Global Variables)**

A function can access an outer variable as well, for example:

```js
let userName = 'John';

function showMessage() {
  let message = 'Hello, ' + userName;
  alert(message);
}

showMessage(); // Hello, John
```

If a same-named variable is declared inside the function, then it shadows the outer one.

**Return Statement**

It is possible to use `return` without a value. That causes the function to exit immediately.

```js
function showMovie(age) {
  if ( !checkAge(age) ) {
    return;
  }

  alert( "Showing you the movie" ); // (*)
  // ...
}
```

## Function expressions

There is another syntax for creating a function that is called a Function Expression.

It allows us to create a new function in the middle of any expression.

For example:

```js
let sayHi = function() {
  alert( "Hello" );
};
```

We can copy the value of a function into another variable.

```js
function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```

Let us look at an example to understand function expressions more
clearly.

```js
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

function showOk() {
  alert( "You agreed." );
}

function showCancel() {
  alert( "You canceled the execution." );
}

// usage: functions showOk, showCancel are passed as arguments to ask
ask("Do you agree?", showOk, showCancel);
```

The arguments `showOk` and `showCancel` of ask are called **callback functions** or just **callbacks**.

We can use Function Expressions to write an equivalent, shorter function:

```js
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);
```
The functions here have no name, and so are called *anonymous*.
