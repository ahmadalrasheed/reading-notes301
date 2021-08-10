## Forms
![](https://res.cloudinary.com/practicaldev/image/fetch/s--KpQnReJ9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://i1.wp.com/blogreact.com/wp-content/uploads/2020/03/forms.jpg%3Ffit%3D750%252C393%26ssl%3D1)
***HTML form elements work a bit differently from other DOM elements in React, because form elements naturally keep some internal state. For example, this form in plain HTML accepts a single name:***

`<form>`
  `<label>`
    `Name:`
  `  <input type="text" name="name" />`
`  </label>`
  `<input type="submit" value="Submit" />`
`</form>`

***This form has the default HTML form behavior of browsing to a new page when the user submits the form. If you want this behavior in React, it just works. But in most cases, it’s convenient to have a JavaScript function that handles the submission of the form and has access to the data that the user entered into the form. The standard way to achieve this is with a technique called “controlled components”.***

### Controlled Components
***In HTML, form elements such as `<input>`, `<textarea>` and `<select>` typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().***



***For example, if we want to make the previous example log the name when it is submitted, we can write the form as a controlled component:***

>class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  handleChange(event) {
    this.setState({value: event.target.value});
  }
  handleSubmit(event) {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }
  render() {
    return (
     ` <form onSubmit={this.handleSubmit}>`
        `<label>`
        `  Name:`
         ` <input type="text" value={this.state.value} onChange={this.handleChange} />`
        `</label>`
       ` <input type="submit" value="Submit" />`
     ` </form>`
   ` );`
 ` }`
`}`



Try it on CodePen

***Since the value attribute is set on our form element, the displayed value will always be this.state.value, making the React state the source of truth. Since handleChange runs on every keystroke to update the React state, the displayed value will update as the user types.***


### The textarea Tag
In HTML, a `<textarea>` element defines its text by its children:

`<textarea>`
  Hello there, this is some text in a text area
`</textarea>`
In React, a `<textarea>` uses a value attribute instead. This way, a form using a `<textarea>` can be written very similarly to a form that uses a single-line input:

>class EssayForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: 'Please write an essay about your favorite DOM element.'
    };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  handleChange(event) {
    this.setState({value: event.target.value});
  }
  handleSubmit(event) {
    alert('An essay was submitted: ' + this.state.value);
    event.preventDefault();
  }
  render() {
    return (
      `<form onSubmit={this.handleSubmit}>`
       ` <label>`
        `  Essay:`
          `<textarea value={this.state.value} ``onChange={this.handleChange} />`
        `</label>`
      `  <input type="submit" value="Submit" />`
      `</form>`
    );
  }
}


***Notice that this.state.value is initialized in the constructor, so that the text area starts off with some text in it.***

### The select Tag
***In HTML, `<select>` creates a drop-down list. For example, this HTML creates a drop-down list of flavors:***

`<select>`
  `<option value="grapefruit">Grapefruit</option>`

  `<option value="lime">Lime</option>`

  `<option selected value="coconut">Coconut</option>`

  `<option value="mango">Mango</option>`

`</select>`
***Note that the Coconut option is initially selected, because of the selected attribute. React, instead of using this selected attribute, uses a value attribute on the root select tag. This is more convenient in a controlled component because you only need to update it in one place. For example:***

>class FlavorForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: 'coconut'};
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  handleChange(event) {
    this.setState({value: event.target.value});
  }
  handleSubmit(event) {
    alert('Your favorite flavor is: ' + this.state.value);
    event.preventDefault();
  }
  render() {
    return (
      `<form onSubmit={this.handleSubmit}>`
        `<label>`
         ` Pick your favorite flavor:`
         ` <select value={this.state.value} onChange={this.handleChange}>`
            `<option value="grapefruit">Grapefruit</option>`
            `<option value="lime">Lime</option>`
            `<option value="coconut">Coconut</option>`
            `<option value="mango">Mango</option>`
          `</select>`
        `</label>`
        `<input type="submit" value="Submit" />`
      `</form>`
    `);`
  `}`
`}`

Try it on CodePen
## The Conditional (Ternary) Operator
![](https://cdn.educba.com/academy/wp-content/uploads/2020/02/Ternary-Operator-JavaScript.jpg)

**example:**

`condition ? value if true : value if false`

Here’s what you need to know:
* The condition is what you’re actually testing. The result of your condition should be true or false or at least coerce to either boolean value.
* A `? `separates our conditional from our true value. Anything between the ? and the : is what is executed if the condition evaluates to true.
* Finally a `: `colon. If your condition evaluates to false, any code after the colon is executed.

**Example — Driver Age**
>let person = {
  name: 'tony',
  age: 20,
  driver: null
};
person.driver = person.age >=16 ? 'Yes' : 'No';

***The most important thing to note is the order of operations. Lets add some parenthesis to help you visualize the order in which code is executing:***

`person.driver = ((person.age >=16) ? 'Yes' : 'No';)`