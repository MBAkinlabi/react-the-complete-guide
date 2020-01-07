# Adding Two Way Binding
- https://github.com/MBAkinlabi/my-app/commit/029a67cca74ef3730d62c81236e6df29e8fa116d
- We add an input and we can change the name in the field where the person `nameChangedHandler` was add without issue. We type and the name is changing as we do that. Cool stuff. The name won't change for persons who we didn't add the `nameChangedHandler` to. 
```js
# person.js
const person = (props) => {
    return (
        <div>
            <p onClick={props.click}>I'm {props.name} and I am {props.age} years old!</p>
            <p>{props.children}</p>
            <input type="text" onChange={props.changed} />
        </div>
    )
};
```


```js
#App.js

nameChangedHandler = (event) => {
    this.setState({
      persons: [
        { name: 'Max', age: 28 },
        { name: event.target.value, age: 29 },
        { name: 'Stephanie', age: 26 }
      ]
    } )
  }

```

```js
#App.js

  <Person 
          name={this.state.persons[0].name} 
          age={this.state.persons[0].age} />
        <Person 
          name={this.state.persons[1].name} 
          age={this.state.persons[1].age} 
          click={this.switchNameHandler.bind(this, 'Max!')} changed={this.nameChangedHandler} >My Hobbies: Racing</Person>
        <Person 
          name={this.state.persons[2].name} 
          age={this.state.persons[2].age} />
      </div>
```

```js
#person.js

<p>{props.children}</p>
            <input type="text" onChange={props.changed} value={props.name} />
        </div>

```