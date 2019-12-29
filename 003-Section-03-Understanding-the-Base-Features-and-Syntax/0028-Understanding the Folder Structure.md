# Understanding the Folder Structure
- Link here: https://github.com/MBAkinlabi/my-app/commit/1d6cb5cd9bc26e95f8abd06ec2eefa8c93fe28c9
- Now we now open the folder that was created. You can see everything there.
- We've got a couple of configuration files on the root level.
- The lock files can be ignored.
- Inside the `package.json.`, you can see three dependencies and they're all created by `create-react-app` 
- As you can see we import `react`, `react-dom` and `react-scripts`. The latter offers all those build, workflow, the next-gen JS features and more. 
- There're also a couple of scripts in the `package.json` file. 
- You can run those scripts with `npm run` and the name.
- The `start` command happens to start the development server, watch our code, compile our code, optimize -- do all these things. 
- Once you're ready to deploy your app, run `build` to optimize it even more, not launch the development server, get your optimized code stored in a folder.
- Before running `build` you won't see your compiled code anywhere. Everything happens in memory. We'll come back to deploying the code later.
- On the root folder, the `node_modules` folder holds all the dependencies and sub-dependencies of our project. For example, `react-scripts` has a lot of other dependencies. All those little build tools which compile code and so on. 
- Don't add anything in the `node_modules` folder. It's generated automatically.
- The public folder is a little more interesting. It's the root folder that gets served by the server in the end
- The script files are added into the `src` folder. 
- The `index.html` is an important file you should know. 
- We'll never add more `html` pages in this project.
- But if you're creating multi-page project, you'll create multiple projects using the `create-react-app`, you wouldn't add more `html` files here. 
- This example is a single page where our scripts would get injected by the build workflow. 
- You can edit this file, but we won't write any `html` code here. 
- The author highlighted the `div` with the `id` of `root`. That's where you'll mount your react application. 
- But if you want to add some `<link>` imports to some `css` libraries or you want to add some `<meta>` tags you can do that at the top as usual in the `html` file. 
- You could also add more `html` but you definitely want to do that in react.
- The `manifest.json` file is there because `create-react-app` gives us a progressive web app out of the box. 
- A very basic one there.
- You can define some meta data about our application.
- The `src` folder is an interesting one. Inside the folder are the files we would actually work with. It's actually the react application.
- The `indext.js` file is probably the most important one.
- It gets access to the `root` element of our `DOM` `html` file.
- That root is of course, the `root` I show you earlier in the public's `index.html` file.
- As you can see it renders the `App` which it imports from the `./App` file with the render method. 
- If you look at the `App.js` file, this is where you see the first and only `React` component we have in this starting project.
- Here you'll see some `JSX`. I'll tell you more about that later.
```js 
<div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
```
- Remove all the content in that wrapping `div`
- This:
```js
class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}
```
- **Becomes this**
```js
class App extends Component {
  render() {
    return (
      <div className="App">
        
      </div>
    );
  }
}
```
- In between the `div` simply add this `H1`
```js
class App extends Component {
  render() {
    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
      </div>
    );
  }
}
```
- It should automatically reload the page in the browser and you should see the change.
- In the `src` folder you can also remove the `logo.svg` file because we no longer use it in our project.
- Now, we have kind of a leaner `src` folder. 
- The `create-react-app` also gives us the `App.css` file, which gives us some CSS styling we use. 
- Go to that file and remove everything except the `.App` style definition. 
```css
.App {
  text-align: center;
}
```
- We also have a `index.css` file, which also applies styles globally.
- The `registerServiceWorker.js` file is for registering a service worker. It pre-cache our script files.  We don't need to configure anything there. 
- And in the `App.test.js` file, we would dive into testing later. It allows us to create unit tests for different units. Example is components in our application.  
- This is the general set up. For the majority of this course, we would work in `App.js` file or other new components we create.
- Inside the `App.js` file, get rid of the logo import because we've removed that. 
```js
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';
```
- Now becomes this:
```js
import React, { Component } from 'react';
import './App.css';
```
