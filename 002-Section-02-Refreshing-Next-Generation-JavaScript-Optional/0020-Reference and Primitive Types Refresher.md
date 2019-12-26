# Reference and Primitive Types Refresher
- The author created this:
```js
const number = 1;
```
- Now author created another copy like this:
```js
const num2 = number;
console.log(num2); // outputs 1
```
- Numbers, strings, booleans are primitive types. Whenever you store a variable into another variable like we did above, it'll copy the value. 
- But `objects` and `arrays` are reference types though.
- Here's what the author mean:
- If you create a person object, which just has a name here:
```js
const person = {
  name: 'Max'
}
```
- And if you create a `secondPerson` and assign `person` as a value here, and `console.log` `secondPerson`
```js
const secondPerson = person;

console.log(secondPerson);

/*
Outputs:

[object Object] {
  name: "Max"
}

*/
```
- It'll return the same value as the first person, but it wouldn't have copied the `person`
- `person` the object is stored in memory. And the `const person`, we store a pointer to that place.
- If we then assign `person` to `secondPerson`, that pointer would be copied. 
- If we change `person.name` after copying it, with that you would expect to print `Max`, but you would still see the name `Manu` even though we've already copied it before changing the name. The name also changed for the `secondPerson` even though we've copied `person` before changing the value of the `name`
```js
const person = {
  name: 'Max'
}

const secondPerson = person;

person.name = 'Manu';

console.log(secondPerson);

/*
Outputs:

[object Object] {
  name: "Manu"
}
*/ 
```
- If we change `name` on `person` we automatically change it for `secondPerson`
- That's important to keep in mind. It's the same for arrays.
- It's important to keep this mind as you learn React.
- You'll learn how to copy in immutable ways, which means we copy by copying the object and not just the pointer. 
- For this, we can use the spread operator.
```js
const person = {
  name: 'Max'
}

const secondPerson = {
  ...person
};

person.name = 'Manu';

console.log(secondPerson);
```
- Using the spread operator like the above will pull out the property and the value of the property and add it to the newly created object at `const secondPerson`
- By running it, you'll still print this:
```js
/*
Outputs:

[object Object] {
  name: "Max"
}
*/
```
- Even though you changed the name to `Manu`, it's printing `Max`. That's because you've just created a real copy. 
- Keep in mind that in JavaScript, objects and arrays are reference types. 
- If you reassign them, you're copying the pointer, not the value. 