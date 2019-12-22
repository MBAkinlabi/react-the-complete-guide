# Exports and Imports
- You may create a file where you want to expert the property, method or class from it.
- Okay below is a the file for example:
**person.js**
```js
const person = {
    name: 'Max'
}

export default person;
```

**utility.js**
```js
export const clean = () => {
    ...
}

export const baseData = 10;
```
- Here are some examples of `import` syntax
**app.js**
```js
import person from './person.js'
import prs from './person.js'

import { baseData } from './utility.js'
import { clean } from './utility.js'
```
- The `default` keyword means that if we `import` from that file, it'll always be our `default export`
- By using `default` it means that we can name `person` whatever we want, which is why the instructor printed it twice in the example.
- In the `utility` file because we have two things we can import, we have to use their names. This is called named import. We didn't mark anything as default.
- You can also do something like this. It's called assigning an alias. It allows you to freely choose the name you want to use.
```js
import { smth as Smith } from './utility.js'
```
- You can also use the `*` to import everything as an object. So whatever you import would be like properties.
```js
import * as bundled from './utility.js'
```