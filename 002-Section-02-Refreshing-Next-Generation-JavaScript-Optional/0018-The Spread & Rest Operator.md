# The Spread & Rest Operator
- Spread - is used to split up array elements OR object properties
```js
const newArray = [...oldArray, 1, 2];
const newObject = { ...oldObject, newProp: 5 };
```
- Rest - is the same `...` operator but used differently.
- It's used to merge a list of function arguments into an array
```js
function sortArgs(...args) {
    return args.sort();
}
```
- Here's an example of where we use the spread operator
```js
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4];

console.log(newNumbers);
```
- It will print out `[1, 2, 3, 4]`
- Here's how you use it with objects:
```js
const person = {
  name: 'Max'
};

const newPerson = {
  ...person,
  age: 28
}

console.log(newPerson);
```
- Using Rest:
```js
const filter = (...args) => {
  return args.filter(el => el === 1);
}

console.log(filter(1, 2, 3));
```