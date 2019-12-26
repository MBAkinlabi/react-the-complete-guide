# Destructuring
- Destructuring allows you to easily extract array elements or object properties and store them in variables
- For array, it works like this:
```js
[a, b] = ['Hello', 'Max'];
console.log(a) // Hello
console.log(b) // Max
```
- Object destructuring works like this:
```js
{name} = {name: 'Max', age: 28};
console.log(name) // Max
console.log(age) // undefined
```
- Here're more examples for you:
```js
const numbers = [1, 2, 3];
[num1, num2] = numbers;
console.log(num1, num2); // Outputs 1 and 2

const numbers = [1, 2, 3];
[num1, ,num3] = numbers;
console.log(num1, num3); // Outputs 1 and 3
```