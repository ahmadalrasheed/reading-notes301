## How would you break a mock into a component heirarchy?
![](https://blog.harveydelaney.com/content/images/2019/08/react.jpg)

***The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names. If you’re working with a designer, they may have already done this, so go talk to them! Their Photoshop layer names may end up being the names of your React components!***

***But how do you know what should be its own component? Use the same techniques for deciding if you should create a new function or object. One such technique is the single responsibility principle, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.***
![](https://reactjs.org/static/eb8bda25806a89ebdc838813bdfa3601/6b2ea/thinking-in-react-components.png)
***Since you’re often displaying a JSON data model to a user, you’ll find that if your model was built correctly, your UI (and therefore your component structure) will map nicely. That’s because UI and data models tend to adhere to the same information architecture. Separate your UI into components, where each component matches one piece of your data model.***


## What is the single responsibility principle and how does it apply to components?

***But how do you know what should be its own component? Use the same techniques for deciding if you should create a new function or object. One such technique` is the `single responsibility principle, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.***

## What does it mean to build a ‘static’ version of your application?
![](https://images.indepth.dev/images/2021/04/Building-a-react-static-site-generator-in--20-lines-of-code--4-dependencies-and-no-transpilers2.jpg)

***Now that you have your component hierarchy, it’s time to implement your app. The easiest way is to build a version that takes your data model and renders the UI but has no interactivity. It’s best to decouple these processes because building a static version requires a lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing. We’ll see why.***

***To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child. If you’re familiar with the concept of state, don’t use state at all to build this static version. State is reserved only for interactivity, that is, data that changes over time. Since this is a static version of the app, you don’t need it.***

## Once you have a static application, what do you need to add?
To make your UI interactive, you need to be able to trigger changes to your underlying data model. React achieves this with `state`.

### What are the three questions you can ask to determine if something is state?

**Let’s go through each one and figure out which one is state. Ask three questions about each piece of data:**

* Is it passed in from a parent via props? If so, it probably isn’t state.

* Does it remain unchanged over time? If so, it probably isn’t state.

* Can you compute it based on any other state or props in your component? If so, it isn’t state.

### How can you identify where state needs to live?

**For each piece of state in your application:*

* Identify every component that renders something based on that state.

* Find a common owner component (a single component above all the components that need the state in the hierarchy).

* Either the common owner or another component higher up in the hierarchy should own the state.

***If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.Let’s run through this strategy for our application:***

> ProductTable needs to filter the product list based on state and SearchBar needs to display the search text and checked state.
The common owner component is FilterableProductTable.
It conceptually makes sense for the filter text and checked value to live in FilterableProductTable
Cool, so we’ve decided that our state lives in FilterableProductTable. First, add an instance property this.state = {filterText: '', inStockOnly: false} to FilterableProductTable’s constructor to reflect the initial state of your application. Then, pass filterText and inStockOnly to ProductTable and SearchBar as a prop. Finally, use these props to filter the rows in ProductTable and set the values of the form fields in SearchBar.