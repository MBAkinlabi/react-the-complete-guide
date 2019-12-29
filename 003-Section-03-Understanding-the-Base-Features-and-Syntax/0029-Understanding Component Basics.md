# Understanding Component Basics
- [Nothing to commit but a lot of things were discussed.]
- Inside the `src` folder, go to `App.js`
- What do you see there?
- You see a React component.
- The `App` component, actually gets used in the `index.js` file where we render it with `ReactDOM.render()` into the place of the `root` element in the real `html` file. 
- Inside the `index.js` file and the `ReactDOM.render()` function, we could remove the `<App />` and replace it with an `<h1>`
```js 
ReactDOM.render(<App />, document.getElementById('root'));
```
- It becomes:
```js
ReactDOM.render(<h1>Test</h1>, document.getElementById('root'));
```
- If you save it, you'll see the `h1`. But then it means we're not renderering our own React component. We're rendering a normal `h1`
- That's not how you create a React app.
- Change it back to the `App` compoent:
```js 
ReactDOM.render(<App />, document.getElementById('root'));
```
- Back to the `App.js`.
- In the `App` component, in there, you would nest other components your app might need.
- And of course, these components can also be nested into each other.
- All the way up to the top, you only have on root one component. 
- You can also go back to the `index.js` file, reach out to multiple nodes in your `html` file and mount different root components for different react apps all in the same project. That would be possible.
- But let's stick to one general typical usage of react. 
- Go back to the `App.js` file, you can see one of the two ways of defining a React component. 
- You created a JavaScript class with the `class` keyword and we use the `extends` keyword to inherit from the `Component` class.
```js
class App extends Component {
```
- As you know the `Component` is imported from above in this way from the React library.
```js
import React, { Component } from 'react';
```
- Actually, we imported two things in this case.
- React, which is required for rendering anything to the DOM. We always have to import that file we we define a component.
- And the `Component` class itself
- I'll soon show you the a differernt way of creating components. 
- Now, this class has one method, the render method. It needs to have that because React we call that method to render something to the screen. 
```js
render() {
    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
      </div>
    );
  }
```
- There's an important job every React component has to do. It has to return or render some `html` code which can be rendered to the DOM or screen.
- You can do some other things in there to. Reach out to the internet and do some calculation. Listen to events.
- Then below the code, we then export the class as the default export of the `App.js` file. 
```js
export default App;
```
- One thing to quickly keep in mind is that we don't need to use the `.js` extension when we're importing. I believe you must have seen that.
- You might also see something like `App.jsx` instead of `.js`
- The reason for that is this code here:
```js
<div className="App">
    <h1>Hi, I'm a React App</h1>
</div>
```
- That's the code in the `render` function of the `component`
- The above code isn't `html`. It looks like it, but it is `JSX`
- It works both in `.js` and `.jsx` files. The conventional these days is to always use `.js` extensions.
- We can use it to write `html` in quotation marks, while in the end not writing it.
- You'll learn more in the next lecture. 