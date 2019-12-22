# Understanding "let" and "const"
- `let` and `const` are different ways of creating variables
- `var` still works but you're encouraged to use `let` and `const`
- Use `let` if you want to create a variable that is really a variable
- Use `const` when you want to create something you assign once and never changes
- Instructor is using JS Bin for practice
- For example:
```js
var myName = "Max";
console.log(myName);
```
- The above code outputs `"Max"` and that shouldn't surprise you of course.
- And if you do the below again to change the value of `myName`
```js
var myName = "Max";
console.log(myName);

myName = "Manu";
console.log(myName);
```
- It should now return `"Manu"`
- If you change `var` to `let`, nothing would change.
- If you use `const` though, it would output `"Max"`, and throw an error because you try to reassign the const variable.
```js
const myName = "Max";
console.log(myName);

myName = "Manu";
console.log(myName);
```