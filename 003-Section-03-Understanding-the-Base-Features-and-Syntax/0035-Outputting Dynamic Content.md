# Outputting Dynamic Content
- https://github.com/MBAkinlabi/my-app/commit/3e475168e35e68be21182c6a26b6f9718936b28b
- Let's talk about how to output some dynamic content in react
- Inside the `Person.js` file in the `Person` folder, let's say that we want to return something like this:
```js
const person = () => {
    return <p>I'm a Person and I am X years old!</p>
};
```
- Now `X` in the return above would actually be a random number.
- We can replace `X` with `Math.random()` to get a random number between zero and 1. And maybe mutiply it by 30.
- And also you should use `Math.floor()` to round it down.
```js
const person = () => {
    return <p>I'm a Person and I am Math.floor(Math.random() * 30) years old!</p>
};
```
- If you save that code, well, you'll see that it outputs as a text. It's not doing what we want it to do.
- How would React know to execute this as JS?
- If we have some dynamic content in our JSX part, which we want to run as JS code and not interpret as text, we have to wrap it in single curly braces.
```js
const person = () => {
    return <p>I'm a Person and I am {Math.floor(Math.random() * 30)} years old!</p>
};
```
- Now, if you reload it, you'll see that it's generating dynamic results. That's some random numbers there for us as we continue to reload.
- This is super important.
- We can't define JS class or something like that within that return of course. But we can execute one line expressions. It's easy for us to do that.
- We can do simple one-line calculations or function calls on those one line returns.
- We can call a function on that line and that function can then do some complex stuff.
- Now that we can output dynamic content, why don't we take it to the next level and make our component more dynamic?
- So that we can leave out outputting some dynamic content like person and a random number.
- Instead, we can do something else.
- For example, we can pass some configuration on the `App.js` file. Maybe some `html` attributes we passed to `person` to configure what we want to output for each usage of the person component. 