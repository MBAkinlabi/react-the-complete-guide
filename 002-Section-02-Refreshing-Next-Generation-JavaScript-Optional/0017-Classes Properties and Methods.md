# Classes, Properties and Methods
- Properties are like "variables attached to classes/objects"
- Methods are like "functions attached to classes/objects"
- We write this in `ES6`
```js
constructor() {
    this.myProperty = 'value';
}
```
- But the way we write that in `ES7` is even better
```js
myProperty = 'value';
```
- We write methods like this in `ES6`
```js
myMethod() {...}
```
- Now, we write it like this in `ES7`
```js
myMethod = () => {...}
```
- The above is using an arrow function. You have no problem with the `this` keyword.
- Things are different in `ES7`. It's more modern. Now you can write all what we wrote earlier like this:
```js
class Human {
  gender = 'male';

  printGender = () => {
    console.log(this.gender);
  }
}

class Person extends Human {
    name = 'Max';
    gender = 'female';
  
  printMyName = () => {
    console.log(this.name);
  }
}

const person = new Person();
person.printMyName();
person.printGender();
```
- And it works just fine.
- This is the next generation JavaScript, which we would use. 