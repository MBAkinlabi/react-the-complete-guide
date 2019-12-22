# Understanding Classes
- Example of a class in JavaScript
```js
class Person {
    name = 'Max';
    call = () => {
        ...
    }
}
```
- In the quick example above, `name` is a property and `call` is a method.
- This is how you instantiate a class in JS:
```js
const myPerson = new Person();
myPerson.call();
console.log(myPerson.name);
```
- JS class supports inheritance. A class can extend another classes. Meaning everything in the parent class is now available to the new class.
- You can add constructor to any class, which would be executed whenever you instantiate the class. Here's how it works:
```js
class Person {
  constructor() {
    this.name = 'Max';
  }
  
  printMyName() {
    console.log(this.name);
  }
}
```
- Now, we can use the class to store and instance in a constant
```js
const person = new Person();
person.printMyName();
```
- Again you can create another class
```js
class Human {
  constructor() {
    this.gender = 'male';
  }
  printGender() {
    console.log(this.gender);
  }
}
```
- Now the previous `Person` class can inherit from `Human` class.
```js
class Person extends Human {
  constructor() {
    this.name = 'Max';
  }
  
  printMyName() {
    console.log(this.name);
  }
}
```
- It means `Person` class has inherited the property `gender` and method `printGender` from class `Human`.
- Now it means we can do this too:
```js
person.printGender()
```
- But if we run it like that we would get an error.
- We must call the super constructor first.
- If you're extending from another class, you must add `super();` in the child class to inherit those properties and methods from the parent class.
```js
class Person extends Human {
  constructor() {
    super();
    this.name = 'Max';
  }
  
  printMyName() {
    console.log(this.name);
  }
}
```
- Now if you run it in JS Bin, it should now work. 
- In fact, inside the child class, you can still change the gender there to `female` if you want to.
```js
class Person extends Human {
  constructor() {
    super();
    this.name = 'Max';
    this.gender = 'female';
  }
  
  printMyName() {
    console.log(this.name);
  }
}
```
- Even though the example isn't 100% correct, you should still see `female`. Wow. We've changed it in the child class.