# Stateless vs Stateful Components
- No commit made
- Every component receives props.
- You can manage state in every component
- Prior to the last lecture, you could only manage state in class-based components
- Example is this: Okay i get it
```js
class App extends Component {
  state = {
```
- If you're creating with the class keyword or with the functional component,
- Example is this:
```js
const app = props => {

  const [ personsState, setPersonsState ] = useState({
```
- If you're managing state even with the state property taught prior to the last lecture, or with the React `useState` hook,
- No matter the approach you're using, you can differentiate your component in stateful and stateless component.
- A stateful component is a component that manages state no matter if it's using the `useState` hook or the class-based approach with the `state` property.
- A component like the `person` component inside the `person.js` file is a stateless component because it has no internal state management
- And it's good to create as many of these stateless components (or call them presentational components)
- Have as many as possible. It's good.
- So components that are class based with state or functional based which uses `useState` state are also called smart components or container components
- You only want to have a couple of these smart components. Although that depends on the size of your app.
- If you want to have an app with thousands of components, you'll also have multiple containers.
-  The idea is that you restrict yourself to a setup where you have way more functional presentation components (or stateless) that stateful components (or containers that use state)
- It makes your app easier to maintain and manage
- You have a clear flow of data and it's very clear where your main logic sits or your data changes and then distribute it to the rest of your app.
- So if anyone ever needs to change something about the app, it's clear where to make that change.
- If every component in your app manages its own state, you quickly end up with spaghetti code where everyone is doing everything
- That can make your app very hard to read and maintain and so on
- Keep those terms used in this lecture in mind.
