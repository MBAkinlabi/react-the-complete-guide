# Manipulating the State
- https://github.com/MBAkinlabi/my-app/commit/a071b167d5c8f72f136beef2afbe3134ac40df60
- In the last lecture, we executed the `switchNameHandler` upon a click. Now, we want to manipulate the state upon the click.
- Inside the `switchNameHandler` comment out the console.log line.
```js
 switchNameHandler = () => {
    // console.log('Was clicked!');
  }
```
- Now simply do `this.state.` reaching out to the state property inside the `App` class. and continue with `this.state.persons[0].name = 'Maximilan`. What we did here is change the name of first person.
```js
 switchNameHandler = () => {
    // console.log('Was clicked!');
    this.state.persons[0].name = 'Maximilan';
  }
```
- Save it and let's see what happens when we execute this code. We already get a warning, but let's ignore it for now and just click `Switch Name` button
- Nothing changes and we still see `Max` here instead of `Maximilan`
- As I said we did get a warning about this.
- We shouldn't mutate, that means `state` directly like we've done above. React wouldn't recognize that and it'll not pick up the change.
- Comment out the code and write `` in front of the code.
```js
switchNameHandler = () => {
    // console.log('Was clicked!');
    // DON'T DO THIS: this.state.persons[0].name = 'Maximilan';
    
  }
```
- Instead, use a special method React gives you.
- You also access it with `this.setState`
We haven't define this method `setState`, but remember that we extend Component on the `App` class.
- The `Component` object happens to have the `setState` method. It's a method that allows us to update the special `state` property in the class. And it will then ensure that React gets to know about this update and updates the DOM.
```js
switchNameHandler = () => {
    // console.log('Was clicked!');
    // DON'T DO THIS: this.state.persons[0].name = 'Maximilan';
    this.setState()
  }
```
- `setState` takes an object as an argument, and it'll merge whatever we define in the `setState` with our existing `state`
- So, if we set `persons` to an updated array, it'll merge it with existing data.
```js
  switchNameHandler = () => {
    // console.log('Was clicked!');
    // DON'T DO THIS: this.state.persons[0].name = 'Maximilan';
    this.setState({persons: })
  }
```
- So, if we have `otherState` with value of `some other value` inside the `state` property below the `persons` array.
- The `otherState` won't get touched even if we only update persons.
```js
class App extends Component {
  state = {
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ],
    otherState: 'some other value'
  }

  switchNameHandler = () => {
    // console.log('Was clicked!');
    // DON'T DO THIS: this.state.persons[0].name = 'Maximilan';
    this.setState({persons: })
  }
```
- Not clear what I mean? Let me show you.
- Copy persons and add it into the `setState` where you're about to change it anyway.
- Inside the `setState` where we update the `persons`, where we only change the first person's name to `Maximilan` and change the third person (Stephanie) age to 27.
```js
this.setState({
      persons: [
        { name: 'Maximilian', age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    } )
```
- Now, what React would do for us is look at our `state` and see which part of it was overriden or changing persons.
- It'll not discard the `otherState` but it'll simply merge the old state with the new one.
- It'll leave `otherState` untouched, but it'll not discard it which is a good thing. You don't want to update everything since you only want to change only a tiny piece of code.
- Let's see what happens when we save this file.
- Now, click the `Switch Name` button and you'll see that both persons will get automatically updated.
- The DOM was updated.
- There are many things which lead React to update the DOM.
-  There are actually two. Changing state and props.
- We changed `state` and that's nice. Keep in mind that what we actuallt output for each person is defined in the person component inside the `Person` folder and `Person.js` file.
- In that file we don't use `state`. Although we could use it with React Hooks. I'll introduce you to React Hooks soon.
- But for now we're not using `state` in here in the `Person.js` but our class based components instead.
- Here in the `Person.js` we use `props` and that's the other thing React watches out for.
- If state changes or props changes, it basically analyze the code you already rendered to the DOm and the code it'll now render if it were to render everything.
- And it updates the existing DOm and all the places it needs to updated to reflect your new state and props. 
- Use `state` in `App.js` (class-based components) and use `props` in `Person.js` (function-based components )