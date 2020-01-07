# Adding Styling with Stylesheets
- https://github.com/MBAkinlabi/my-app/commit/09130879a90a7419a0ab5e00315d3225b1f3bf8e
- Learned how to add CSS stylesheets to the project. 
```js
# person.js
onst person = (props) => {
    return (
        <div className="Person">
            <p onClick={props.click}>I'm {props.name} and I am {props.age} years old!</p>
```
-
```css
/* person.css */
.Person {
    
}
```
-
```css
/* person.css */
.Person {
    width: 60%;
    margin: 16px auto;
    border: 1px solid #eee;
    box-shadow: 0 2px 3px #ccc;
    padding: 16px;
    text-align: center;
}
```
-

```js
# Person.js
import React from 'react';

import './Person.css';
```

```js
#
```