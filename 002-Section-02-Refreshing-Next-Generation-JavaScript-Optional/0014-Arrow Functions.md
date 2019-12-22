# Arrow Functions
- This is the way you write a normal JavaScript function:
```js
function myFunc() {
    ...
}
```
- And this is how you write arrow functions
```js
const myFnc = () => {
    ....
}
```
- The arrow function is shorter. It omits the `function` keyword
- It also resolves the issue with the `this` keyword in JavaScript. It doesn't work the way you might have expected it to work when you use the normal `function` keyword.
- Write this function. And call and pass an argument into it.
```js
function printMyName(name) {
  console.log(name);
}

printMyName("Max");
```
- It would outputs "Max" to the console.
- You can write the same thing using an arrow function. You can assign it `const` if you don't plan on reassigning the variable.
```js
const printMyName = (name) => {
  console.log(name);
};

printMyName("Max");
```
- It should still output "Max"
- Let me show you another way of writing arrow functions.
- For example, if you only receive one argument, you can omit the parentheses.
```js 
const printMyName = name => {
  console.log(name);
};

printMyName("Max");
```
- If you have a function, which don't receive an argument, here's how you write it:
```js
const printMyName = () => {
  console.log("Max");
};

printMyName();
```
- If you have more than one arguments, then you'll need parentheses:
```js
const printMyName = (name, age) => {
  console.log(name, age);
};

printMyName("Max", 28);
```
- Sometimes, you just want your function to return something. Below is an example:
```js
const multiply = (number) => {
  return number * 2;
};

console.log(multiply(2))
```
- Instead of writing it like the above, you can just create it in one line and it's pretty simple and fast.
```js
const multiply = (number) => number * 2;

console.log(multiply(2))
```
- The above is a very short version of writing the long version. 
- It gets even shorter if you remove the parentheses around the arguments
```js
const multiply = number => number * 2;

console.log(multiply(2))
```
- You don't have to remember everything right now. 
