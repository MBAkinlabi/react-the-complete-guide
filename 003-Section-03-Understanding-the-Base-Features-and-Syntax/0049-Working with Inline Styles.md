# Working with Inline Styles
- https://github.com/MBAkinlabi/my-app/commit/b2fac546e559593ba4ab25a168bd2fe674a3be0f
- Working with inline styles in JavaScript

```js
# App.js
render() {
    const style = {
      backgroundColor: 'white',
      font: 'inherit',
      border: '1px solid blue',
      padding: '8px',
      cursor: 'pointer'
    };
```

```js
# App.js
<button 
        style={style}
        onClick={() => this.switchNameHandler('Maximillian!!')}>Switch Name</button>
```

```css
/* Person.css */
button {
    
}
```