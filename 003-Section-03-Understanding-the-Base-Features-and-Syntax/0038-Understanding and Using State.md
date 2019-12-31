# Understanding & Using State
- https://github.com/MBAkinlabi/my-app/commit/166337c04e0325fbea0a54a82dbe12ffbb8f1171
- In the last lecture we looked at `props`. 
- Now sometimes, you don't want to get some information from the outside. But you want to have it inside the component and change it from inside there too. 
-  For example in our `App.js` file. Let's say we also want to add a `button`, which if we click it, it switches one of the names we used here. So we put a caption of `Switch Name`
```js
return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
        <p>This is really working!</p>
        <button>Switch Name</button>
        <Person name="Max" age="28" />
        <Person name="Manu" age="29" >My Hobbies: Racing</Person>
        <Person name="Stephanie" age="26" />
      </div>
```
- Well we'll come to handling the click event in the next lectures. But first of all, we need to define names like `Max`, `Manu` and `Stephanie` in a non-hand-coded way. 
- Right now it's hard to code it into our JSX code. It's okay here, but if we later want to change it, we have to store it in some variable or something like that. 
- And this actually is a class. (Instructor was referring to the this: `class App extends Component {`)
- Class has properties. It's not just the case in JS, but in other programming languages too.
- You can think of a property as a variable of a class.
- So, in normal JS code, you'll simply write it like this:
```js
class App extends Component {
  var something = someValue;
```
- This doesn't work in a class.
- There you could write something like this:
```js
class App extends Component {
  something = "some value";
```
- Author removed the changes made.
- In the end, you could say there are the same.
- There's a special property that you can find in any component which `extends Component`
- So, you can do it in person.
- You can define properties inside the `Person.js` file anyways because that's a normal function.
- In there, you would have to use some const or some variables like this: shorting it though:
```js
const person = (props) => {
    const
```
- Author removed the changes made.
- What we're about to do only works in components, created by extending the Component class.
- There we can define a special property name `state`
- Where `props` are passed from outside like `name` and `age` into the `Person` component,  `state` is managed from inside the component. 
- Note that `state` is only available in components that extend the `component` class.
- Actually with React 16.8 a new feature was released called React Hooks, on which there's a whole module towards the end of the course. Which is also going to be introduced in this module here a little later.
- And with that feature you can manage state and function components. For now, we'll now use this though, we'll talk about this later.
- Therefore, we'll add `state` here in this class-based component, which is the default way of adding it.
- Still you should use function components, like we did on `Person.js` as often as possible. Because you should use state with care. 
- Because having `state` in all your components and manipulating it from anywhere in your app makes your app quickly unpredictable and hard to manage as it grows.
-  Of course, it doesn't mean you shouldn't use it at all.
- It makes perfect sense in this case we're about to use it.
- We initalize it by assigning a value. And this value is a JS object.
```js
class App extends Component {
  state = {
    
  }
```
- Again, `state` is a reserved word. We should use it if we want to manage some component internal data.
- So now the `state` could have some `persons`.
- And this could be an array. And you can set up any kind of data you want in this state object.
```js
class App extends Component {
  state = {
    persons: []
  }
```
- You could set up a name property if you want, which is `some name` 
```js
class App extends Component {
  state = {
    persons: [],
    name: 'some name'
  }
```
- Author removed the some name property and its value.
- You can really manage whatever you want. 
- Here we want to manage an array of `persons`
- And now this `persons` array is an array of JS objects, where each object has a name, maybe `Max` and an age, maybe `28`. The 28 is a number. Not a string. 
- And instructor added more for `Manu` and `Stephanie`
```js
class App extends Component {
  state = {
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ]
  }
```
- Now, what we just added are our `state`
- We can now access a property like `state` (well, that's true for any property)
- In our render method by simply outputting something dynamic with single curly braces and then we use the `this` keyword. Note that's inside the first `Person` and the using the `name` attributes. 
```js
<Person name={this} age="28" />
```
- Note that `this` refers to the class due to the ES6 syntax we're using. 
- And on our class, we have a `render` method we could call. We shouldn't do that though. React does that for us.
- And then we can use the `this.state` then access `state`. and on the `state` access my persons array `this.state.persons[0]` there maybe the first element by using index 0 and then the name. It becomes `this.state.persons[0].name`
```js
<Person name={this.state.persons[0].name} age="28" />
```
- Instead of hand coding it, we're now accessing it from this property in the object, in the persons array and on the state property.
- Copy that code you just wrote and replace the age with it too. Remember to replace `name` at the end with `age`
```js
<Person name={this.state.persons[0].name} age={this.state.persons[0].age} />
```
- Replicate the process for the remaining persons `Manu` and `Stephanie`
```js
        <Person name={this.state.persons[0].name} age={this.state.persons[0].age} />
        <Person name={this.state.persons[1].name} age={this.state.persons[1].age} >My Hobbies: Racing</Person>
        <Person name={this.state.persons[2].name} age={this.state.persons[2].age} />
```
- If you go back to the application, you'll see the same output as the last time, but this time using the `state` property. 
- I said `state` would be a special property. Thus far, we don't use it in a special way though.
- We can change it. If it changes, it'll lead React to update the DOM. 
- So if we change the name of `Max` in the `state` for example, it'll lead to the name of the first person being re-rendered. 
- Let me prove it to you and also show you how to listen to events by clicking on the `Switch State` `button` which we haven't touched. In the next video (perhaps)
```js
<button>Switch Name</button>
```
