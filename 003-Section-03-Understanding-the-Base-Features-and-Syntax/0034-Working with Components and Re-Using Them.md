# Working with Components & Re-Using Them
- https://github.com/MBAkinlabi/my-app/commit/402819ac1dc8104ea80664fc68efc713b37e4028
- Creating are awesome because we can focus our code in each file and make it much more maintainable. 
-  We won't try to put everything into the `App.js` file which can get crowded for bigger apps.
- And the component is reusable and configurable. 
- Let's talk about the configuring part.
- Reusing it is simple We can simply copy it and paste it in multiple time as often as we want.
```js
return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
        <p>This is really working!</p>
        <Person />
        <Person />
        <Person />
      </div>
    );
```
- By doing that, we'll get the output multiple times in the browser.
- That's a super easy way of reusing it anywhere in our application.
- We can also configure it.
- Before we do that, let's change else about our react code. 
- In the `Person.js` file inside the `Person` folder, we still just have our static `html` content there.
- Often times, your JSX code should be dynamic. It should output different things depending on the state of your application or user input. 
- Let's do that in the next lecture. 