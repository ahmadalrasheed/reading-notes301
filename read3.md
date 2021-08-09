## Lists and Keys
![lists](https://i.ytimg.com/vi/0sasRxl35_8/maxresdefault.jpg)
***Given the code below, we use the map() function to take an array of numbers and double their values. We assign the new array returned by map() to the variable doubled and log it:***

>const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);
console.log(doubled);
This code logs [2, 4, 6, 8, 10] to the console.

***In React, transforming arrays into lists of elements is nearly identical.***

### Rendering Multiple Components
***You can build collections of elements and include them in `JSX` using curly braces {}.***

***Below, we loop through the numbers array using the JavaScript map() function. We return a <li> element for each item. Finally, we assign the resulting array of elements to listItems:***

>const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);

***We include the entire listItems array inside a `<ul>` element, and render it to the DOM:***

`ReactDOM.render(`
  `<ul>{listItems}</ul>,`
  `document.getElementById('root')`
`);`


***This code displays a bullet list of numbers between 1 and 5.***

### Basic List Component
![listcomponent](https://cdn.educba.com/academy/wp-content/uploads/2020/06/template-73.jpg)
***Usually you would render lists inside a component.***

***We can refactor the previous example into a component that accepts an array of numbers and outputs a list of elements.***

`function NumberList(props) {`
  `const numbers = props.numbers;`
  `const listItems = numbers.map((number) =>`
    `<li>{number}</li>`
  `);`
 ` return (`
   ` <ul>{listItems}</ul>`
  `);`
`}`

const numbers = [1, 2, 3, 4, 5];

`ReactDOM.render(`
 ` <NumberList numbers={numbers} />,`
  `document.getElementById('root')`
`);`

***When you run this code, you’ll be given a warning that a key should be provided for list items. A “key” is a special string attribute you need to include when creating lists of elements. We’ll discuss why it’s important in the next section.***


### Keys
***Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:***

`const numbers = [1, 2, 3, 4, 5];`
`const listItems = numbers.map((number) =>`
  `<li key={number.toString()}>`
    `{number}`
  `</li>`
`);`
***The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys:***

`const todoItems = todos.map((todo) =>`
 ` <li key={todo.id}>`
   ` {todo.text}`
  `</li>`
`);`
***When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort:***

`const todoItems = todos.map((todo, index) =>`
  `// Only do this if items have no stable IDs`
  `<li key={index}>`
    `{todo.text}`
  `</li>`
`);`
***We don’t recommend using indexes for keys if the order of items may change. This can negatively impact performance and may cause issues with component state. Check out Robin Pokorny’s article for an in-depth explanation on the negative impacts of using an index as a key. If you choose not to assign an explicit key to list items then React will default to using indexes as keys.***


## Spread Operator

![spread](https://i.morioh.com/2019/11/19/580be7d831c1.jpg)
***The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.***

### What is the spread operator?
***InJavaScript, spread syntax refers to the use of an ellipsis of three dots `(…)` to expand an iterable object into the list of arguments.***
> “When ...arr is used in the function call, it ‘expands’ an iterable object arr into the list of arguments.” — JavaScript.info

***The spread operator was added to JavaScript in ES6 (ES2015), just like the rest parameters, which have the same syntax: three magic dots ….***

### What it is used for?

Take trying to find the largest number in an array with Math.max():

>Math.max(1,3,5) // 5
Math.max([1,3,5]) // NaN

Trying to pass an array to a JavaScript function expecting separate arguments does not work. In this case it produces a NaN result. Enter …:

>Math.max(...[1,3,5]) // 5

### What else can do?

***The spread operator is useful for many different routine tasks in JavaScript, including the following:***
* Copying an array
* Concatenating or combining arrays
* Using Math functions
* Using an array as arguments
* Adding an item to a list
* Adding to state in React
* Combining objects
* Converting NodeList to an array

