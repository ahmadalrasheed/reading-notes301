## React: Component Lifecycle Events

![lifecycle](https://miro.medium.com/max/2000/0*pqn5ljaOw4kWrUdF)

### What are component lifecycle events?
***React lets you define components as classes or functions. The methods that you are able to use on these are called lifecycle events. These methods can be called during the lifecycle of a component, and they allow you to update the UI and application states.***

![figure](https://miro.medium.com/max/2000/0*0saPKFiTUk6W3FYp)

#### Mounting
***When an instance of a component is being created and inserted into the DOM it occurs during the mounting phase. Constructor, static getDerivedStateFromProps, render,componentDidMount, and UNSAFE_componentWillMount all occur in this order during mounting.***

***Updating Anytime a component is updated or state changes then it is rerendered. These lifecycle events happen during updating in this order.***

> static getDerivedStateFromProps shouldComponentUpdate,render getSnapshotBeforeUpdate, componentDidUpdate UNSAFE_componentWillUpdate, UNSAFE_componentWillReceiveProps Unmounting
The final phase of the lifecycle if called when a component is being removed from the DOM. componentWillUnmount is the only lifecycle event during this phase.
constructor()
The constructor for a React component is called before it is mounted.If the component is a subclass you should call super(props), or the props will be undefined. constructors can be used to assign state using this.state or to bind event handle methods to an instance. Let’s take a look at some example code.
class FishTableRow extends React.Component {
constructor() {
super(props); //gives us access to props
//Don’t call this.setState() here
this.state = { //intitialize local state
showDescription: false
}; }
static getDerivedStateFromProps()
This method exists for rare cases where the state relies on changes in props over time.
render()
Render is the only required method in a class component. It will examine this.props and this.state when called. The render function should not modify the component state because it would cause a lot of bugs by changing the state every time it rerenders. I also should not directly interact with the browser. render will not be invoked if shouldComponentUpdate() returns false. Here is an example of using render.



## React Bootstrap
![bootstrap](https://blog.templatetoaster.com/wp-content/uploads/2019/09/What-is-Bootstrap-Facebook.png)
### Rebuilt with React
***`React-Bootstrap` replaces the Bootstrap JavaScript. Each component has been built from scratch as a true React component, without unneeded dependencies like `jQuery`.***

***As one of the oldest React libraries, React-Bootstrap has evolved and grown alongside React, making it an excellent choice as your UI foundation.***

***Bootstrap at its core Built with compatibility in mind, we embrace our bootstrap core and strive to be compatible with the world's largest UI ecosystem.***

***By relying entirely on the Bootstrap stylesheet, React-Bootstrap just works with the thousands of Bootstrap themes you already love.***

