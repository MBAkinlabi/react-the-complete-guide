# Understanding JSX
- https://github.com/MBAkinlabi/my-app/commit/cf5dde955d86a91b32108e1b218b2b98cb3c7ee3
- Now let's talk about this JSX thing. 
- Comment out the current `return` we have in the render function in the App component.
```js
class App extends Component {
  render() {
    // return (
    //   <div className="App">
    //     <h1>Hi, I'm a React App</h1>
    //   </div>
    // );
  }
}
```
- Let's return something here.
- We can import the `React` class we imported and call a method on it `createElement`. This is another reason why we have to import the React class itself. In fact, the code we just commented out is always compiled into the `createElement` method. That works in the background of course.
```js
class App extends Component {
  render() {
    // return (
    //   <div className="App">
    //     <h1>Hi, I'm a React App</h1>
    //   </div>
    // );
    return React.createElement()
  }
}
```
- The createElement method takes three arguments. Actually it takes an infinite amount of arguments. But at least, three.
- The first argument is the element we want to render to DOM. This can be a `div`. It can be a normal `html` element.
- We can render any component we are importing. 
- the second argument is actually the configuration for this first one. We can pass a JS object. It's optional. We can also pass `null`, and we'll do that for now.
- The third argument is any amount of children. We can have multiple children separated by commas.
- Children means what's nested inside this `div`
- Let's add an `h1` and as another argument, let's add this text `"I'm a React App"`
```js
class App extends Component {
  render() {
    // return (
    //   <div className="App">
    //     <h1>Hi, I'm a React App</h1>
    //   </div>
    // );
    return React.createElement('div', null, 'h1', 'Hi, I\'m a React!!!');
  }
}
```
- We have four arguments.
- If you go back to the application in the browser, you'll see `h1Hi, I'm a React!!!`
- If you inspect it in the Developers tools in the Chrome, you'll see we have a `div` with two elements inside. `h1` which is a text and `Hi, I'm a React!!!`
- This is the default behavior. The `h1` is a text not a real `html` `h1`
- If we want to render another element inside the `div`, we have to replace the third argument with another call to `React.createElement()` to create a new `html` element.
```js
return React.createElement('div', null, React.createElement());
```
- Inside it, we'll now pass `h1`, `null` as configuration, and the text we want to render. Let's use `Does this work now?` as the third argument here.
```js
class App extends Component {
  render() {
    // return (
    //   <div className="App">
    //     <h1>Hi, I'm a React App</h1>
    //   </div>
    // );
    return React.createElement('div', null, React.createElement('h1', null, 'Does this work now?'));
  }
}
```
- If you go back to the application, you'll see it shows in the browser. And if we inspect, we can see that it's `h1` we created is wrapped inside the `div`
- Now, we can't see the css class being added.
- You'll notice in the commented out code, we use `className` instead of `class`. I'll come back to why we do that. 
- Now in the real parent `div` `createElement`, we can rermove the `null` and pass a JS object.
- There we can define a className and assign any CSS class we want to add. For example `App`
```js
return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Does this work now?'));
```
- Now, save it and it should reload. Now you should see that the style has been updated. The text is now centered. The CSS class has been applied. 
- If you check inspect in the Dev tool, you should see the CSS class being applied. 
- It's very important to keep this in mind. The code we just wrote here is the exact equivalent JSX code we commented out. 
- That's the reason why we have to import `React` into the file. Because it's working to compile this in the background for us. 
- Writing the code with `createElement` is really cumbersome. You don't want to do that. Especially as you add and nest more and more elements. 
- That's why we use the code we actually commented out. Because it's so easy. But it's super important to understand what happens in the background, which is why I showed you in this video.
- Now uncomment the JSX code and comment out the code we just wrote. You should have the below:
```js
class App extends Component {
  render() {
    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
      </div>
    );
    // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Does this work now?'));
  }
}
```
- While it looks like `html` it isn't. 