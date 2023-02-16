# React and Forms

## React Forms

- What is a ‘Controlled Component’?

It is when we combine the managing of states in forms and components into one React state. So an input form element that has values controlled by React state. 

- Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.

Ideally we want to update the React state from the form as they type unless we want to specify not to store the users input until they submit. Mostly, we want to store the user input as they are typing/entering an input.

- How do we target what the user is entering if we have an event handler on an input field?

We can track what the user is entering with an event handler on an input field by using the 'onChange' attribute and assign it a reference to the event handler function like this.


```javascript

class NameForm extends React.Component {

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
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}

```

## The Conditional (Ternary) Operatory Explained


- Why would we use a ternary operator?

With ternary operators we can shorten if statements to one line of more readable code, this can be useful in anonymous callback functions and just shortening code. Ternary operators are single statements while if-else is a block of code making it faster.

- Rewrite the following statement using a ternary statement:

```javascript

if(x===y){
  console.log(true);
} else {
  console.log(false);
}

x === y ? true : false

```

>References
>
>[React Docs - Forms](https://reactjs.org/docs/forms.html)
>
>[JavaScript — The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)
>

## Things I want to know more about

- When an if-else code block should be used over ternary operators