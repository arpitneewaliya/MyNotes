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
If you're writing a function and want to support optional parameters, you can specify default values by adding `=` after the name of the parameter, followed by the default value:

```js
function hello(name = "Chris") {
  console.log(`Hello ${name}!`);
}

hello("Ari"); // Hello Ari!
hello(); // Hello Chris!
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
