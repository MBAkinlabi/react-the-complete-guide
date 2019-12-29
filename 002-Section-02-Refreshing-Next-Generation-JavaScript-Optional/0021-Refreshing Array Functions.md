# Refreshing Array Functions
- You'll see a lot of array functions in this course
- We have more like to talk about
- Here's an array - of course, good old fashion
```js
const numbers = [1, 2, 3];
```
- Let's say we want to turn this into an array where each number is doubled. 
- We can use an array function for this.
- Take the array and call map. Map is a built-in array method. There are many of these methods. 
- They take a function as an input and then simply execute on each element in the array. Like in the above example, it's executed on 1, 2, and 3.
```js 
const doubleNumArray = numbers.map((num) => {
  
});
```
- You can name the argument whatever you want. In this example, I'm using `num`.
- What you have to do in the array depends on which array function you're using. In this case we're using `map`
- Check the `docs` at places like `MDN` to learn more about each array function or one before you use it.
- In the `map` function, we want to return the new value we want to turn the old one into. 
- The author returns `num * 2`
- Since it's executed on each element, it'll return 2, 4, and 6. And return them in a new array.
```js
const numbers = [1, 2, 3];

const doubleNumArray = numbers.map((num) => {
  return num * 2;
});
```
- The new array is stored in the `doubleNumArray`
- If you now console log both arrays
```js
console.log(numbers);
console.log(doubleNumArray);

/* Outputs
[1, 2, 3]
[2, 4, 6]
*/
```
- As you can see the old array is unchanged. And the new array is returned.