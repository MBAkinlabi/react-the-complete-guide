# Passing Method References Between Components
- https://github.com/MBAkinlabi/my-app/commit/33e026c28b159715291be75d54919a172bbdfbf9
- **Note that I changed it back to class-based component as recommended by the instructor. Class-based component is more established and many businesses use that. The functional component (stateful) was used to show example of using React Hooks `useState()`. So, we're back. Here's the commit showing the changes:**
- https://github.com/MBAkinlabi/my-app/commit/984180b1c673a3dc70740d05976162fa54545a96
- So now the lecture starts.
- Let's say we want to call the `switchNameHandler` not only when clicking the `Switch Name` button
```js
<button onClick={this.switchNameHandler}>Switch Name</button>
```
- But also when click any paragraph on the `person` component inside the `Person.js` file in the Person folder.
```js 
#person.js

const person = (props) => {
    return (
        <div>
            <p>I'm {props.name} and I am {props.age} years old!</p>
            <p>{props.children}</p>
        </div>
    )
};
```
- Let's say the paragraph that contains the person name and age inside the person component
- For that in the person component, we could add `onClick`
```js
# person.js

const person = (props) => {
    return (
        <div>
            <p onClick={}>I'm {props.name} and I am {props.age} years old!</p> // (changed)
            <p>{props.children}</p>
        </div>
    )
};
```
- We can't call that handler method in a different class in a different file.
- Well, we can actually pass a referrence to this handler as a property to our component. This isn't a fancy hack. It's a very common pattern
- We need to first re-structure this over multiple lines for these components rendered in the `App.js` file.
```js
# App.js

<div className="App">
        <h1>Hi, I'm a React App</h1>
        <p>This is really working!</p>
        <button onClick={this.switchNameHandler}>Switch Name</button>
        <Person name={this.state.persons[0].name} age={this.state.persons[0].age} />
        <Person name={this.state.persons[1].name} age={this.state.persons[1].age} >My Hobbies: Racing</Person>
        <Person name={this.state.persons[2].name} age={this.state.persons[2].age} />
      </div>
    );
```
- It's now re-structured to this:
```js 
# App.js

<div className="App">
        <h1>Hi, I'm a React App</h1>
        <p>This is really working!</p>
        <button onClick={this.switchNameHandler}>Switch Name</button>
        <Person 
          name={this.state.persons[0].name} 
          age={this.state.persons[0].age} />
        <Person 
          name={this.state.persons[1].name} 
          age={this.state.persons[1].age} >My Hobbies: Racing</Person>
        <Person 
          name={this.state.persons[2].name} 
          age={this.state.persons[2].age} />
      </div>
```
- Let's say that we don't even want to pass this into every component. Only this one:
```js
# App.js

<Person 
          name={this.state.persons[1].name} 
          age={this.state.persons[1].age} >My Hobbies: Racing</Person>
```
- So here we'll add a new property called `click`. The name is totally up to you. You can call it whatever you want to call it.
- Here, we'll pass a reference to `this.switchNameHandler`
```js
# App.js

<Person 
          name={this.state.persons[1].name} 
          age={this.state.persons[1].age} 
          click={this.switchNameHandler}>My Hobbies: Racing</Person>
```
- Basically, it's the same thing we did on the button there which has `onClick` but here we're passing it into the `click` property.
- Now we can use this `click` property in `Person.js` file.
- There, we can now call something called `props.click` because `click` is the name of the property we defined inside `App.js` file. 
```js
# Person.js

const person = (props) => {
    return (
        <div>
            <p onClick={props.click}>I'm {props.name} and I am {props.age} years old!</p>
            <p>{props.children}</p> // Changed
        </div>
    )
};
```
- And that would execute the function we passed as a referrence. 
- Save all the file and go to the browser.
- We can still click the button to change the name and age.
- But if you reload the page, we can also click the `I'm Manu and I am 29 years old!` and it'll also change the same thing on the page. 
- This is something important to understand. An important pattern.
- You can pass methods also as `props` so that you can call a method which might change the state in another component which doesn't have direct access to the state
- Maybe we also want to pass a value to our  function.
- Maybe here inside the `App.js` file, `switchNameHandler` should receive the `newName` so that when we, inside `this.setState` where we hand coded `Maximilian` as the new name, we actually, set `name` equal to `newName`
```js
# App.js

switchNameHandler = (newName) => { // changed
    // console.log('Was clicked!');
    // DON'T DO THIS: this.state.persons[0].name = 'Maximilan';
    this.setState({
      persons: [
        { name: newName, age: 28 }, // changed
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    } )
  }
```
- Now, how do we pass that data?
- There are two ways of doing that.
- The first is to call `bind`  this the outside the function binding it into the class. It might look strange to you. We can use `this` though, because we also want to pass another argument into `bind` and the new argument should be the `newName` which would be `Maximilian`
```js
# App.js

<div className="App">
        <h1>Hi, I'm a React App</h1>
        <p>This is really working!</p>
        <button onClick={this.switchNameHandler.bind(this, 'Maximilian')}>Switch Name</button> // changed. 
        <Person 
          name={this.state.persons[0].name} 
          age={this.state.persons[0].age} />
```
- To really see a difference, let's copy that bind code and let's also find it down where we pass the function as a referrence to a click prop. And let's change this to `Max!` so that we can see a difference depending on where we click.
```js
# App.js

<Person 
          name={this.state.persons[1].name} 
          age={this.state.persons[1].age} 
          click={this.switchNameHandler.bind(this, 'Max!')}>My Hobbies: Racing</Person> // changed
        <Person 
          name={this.state.persons[2].name} 
          age={this.state.persons[2].age} />
```
- If we know save this, and go to the browser, let's see what happens when we click the `Switch Name` button.
- Wow, it changes the name to Maximilian. And if we click on the `I'm Manu and I am 29 years old!` Maximilian would change back to `Max!`
- So this is a way of passing an argument. It's not the only way though. I'll leave one of the two codes with `bind` to show you how this works.
-  I'll also show you an alternative syntax though. Leave the second one on `I'm Manu...` paragraph and use the one on the `Switch Name` button.
- This new syntax looks different. Here on the button, `onClick` we actually execute an arrow function, which takes no argument, though it'll receive an event object although I wont use that here. 
- As a function body return this function call.
```js
# App.js

<p>This is really working!</p>
        <button onClick={() => this.switchNameHandler()}>Switch Name</button> // changed
```
- I shouldn't call this. It's not getting called immediately. The function will be executed on a click. 
- This approach is useful because we can now easily pass our data or argument `Maximilian!!` You'll notice that it has two exclamation marks.
```js
# App.js

<p>This is really working!</p>
        <button onClick={() => this.switchNameHandler('Maximillian!!')}>Switch Name</button> // changed
```
- If you now save this and you click the `Switch Name` button, it should return `Maximillian!!`
- This is a very convenient syntax but it can be inefficient. React can re-render certain things in your app too often. So I don't necessary recommend using the second if you don't have to. Use the `bind` first method instead. Be aware that the first one can be inefficient. 