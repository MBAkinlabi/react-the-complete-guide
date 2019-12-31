# Working with Props
- https://github.com/MBAkinlabi/my-app/commit/a8d2a073520ed6a7298638983d5fd6629537c735
- Now, we know how to output dynamic content, let's make our components flexible, configurable and dynamic.
- For normal `html` elements, we can pass attributes like `classname`, which we can then add to
- For example, inside the `App.js` file in the `src` folder.
- For `Person` it would be nice if we can pass these:
```js
<Person name="Max" age="28" />
<Person />
<Person />
```
- And in the second one, we may do this too:
```js
        <Person name="Max" age="28" />
        <Person name="Manu" age="29" />
        <Person />
```
- And for the third usage, we may want to do this too:
```js
        <Person name="Max" age="28" />
        <Person name="Manu" age="29" />
        <Person name="Stephanie" age="26" />
```
- Or, maybe we even want to take it further. And for `Person` `Manu` we even want to split it in a open and closing tag and also output some additional information like `My Hobbies`
```js
        <Person name="Max" age="28" />
        <Person name="Manu" age="29" >My Hobbies: Racing</Person>
        <Person name="Stephanie" age="26" />
```
- With all that in place, we want to change something in our `Person` component to handle that input. Although if we save it, and reload the app, our output is unchanged.
- Because we're not using this information. How would React know what to do with that?
- Go to the `Person.js` file
- Well, it's actually able to take these attributes, and gives us access inside our receiving component on object named `props`
```js
const person = (props) => {
```
- Actually, the name there is up to you. but you'll receive one argument in your function, which is passed into by default by React. Which is an object with all the properties of this component.
- And properties means the attributes you add on your components. In the React land, this is referred to as props. And that's why the instructor named the argument props.
- You should do so too so that everyone understands your code.
- Now, that we have `props`, we can get access to that name and age thing.
- You could write it like this:
```js
const person = (props) => {
    return <p>I'm {props.name} and I am {props.age} years old!</p>
};
```
- The author gave this as a sidenote when writing the above code.
- **When using class-based components, it's `this.props`** and here's how you write it:
```js
class Person extends Component {
    render() {
        return <p>My name is {this.props}</p>;
    }
}
```
- Now save it and see what happens in our React application. If it doesn't reload, reload it manually.
- Now you should see the information we passed into each `Person` usage. Wow.
- You should see `I'm Stephanie and I am 26 years old!` and others of course.
- Now we have a reusable component. Wow!
- Think about all the possibilities we can enjoy with this. Inside, the `App.js` we can now have different `Person` usages with different content. And the template is in the `Person.js` file.
- This is a big step towards building great reusable components. 
- But what about the `My Hobbies: Racing` in the below though? 
```js
<Person name="Manu" age="29" >My Hobbies: Racing</Person>
```
- Let's see how we can use content that's passed not as attributes, but between the opening and closing tags in the next lecture.