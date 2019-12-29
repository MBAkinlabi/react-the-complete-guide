# JSX Restrictions
- https://github.com/MBAkinlabi/my-app/commit/e55d245e5d0d4bf7b6598b6a582b986944b4e3dc
- Let's talk about some of the restrictions we face.
- `class` can't be used because it's a reserved word in JS. that's why we use `className` to assign CSS in the `App.js` file. 
- When we use `div` for example, in fact, we're not using the real `html` text. These are provided by the React library. React is converting them behind the scenes. 
- We can't add another `h1` tag outside the `div` in the below example:
```js
render() {
    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
      </div>
      <h1>Another heading</h1>
    );
```
- JSX expressions must have one root element. With React 16, this is kind of loosened. It's the best practice to wrap everything inside one root element. It makes sense for styling. 
```js
render() {
    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
      </div>
    );
```
- Keep in mind that the return span multiple lines to help us structure our code better and you should always do that.
- Let's add a `p` to the `div`
```js
render() {
    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
        <p>This is really working!</p>
      </div>
    );
    // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Does this work now?'));
  }
```
- If you go to the browser, you'll see that the paragraph has been added to the `div` and it's showing nicely. Wow!