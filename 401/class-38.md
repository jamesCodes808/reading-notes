# React 2

## How does lifting state up in a React application help with managing data flow and what are the benefits of using this approach?

Lifting state up is a useful technique in React that involves moving the state from a child component to its parent component. This approach helps to simplify the management of data flow in a React application by reducing the complexity of state management and making it easier to share data between components.

For example, let's say we have two components, Parent and Child, and we want to pass data from the Child component to the Parent component. We can achieve this by lifting the state up from the Child component to the Parent component.

```javascript
// Child component
function Child(props) {
  const [name, setName] = useState('');

  const handleNameChange = (event) => {
    setName(event.target.value);
    props.onNameChange(event.target.value);
  };

  return (
    <div>
      <input type="text" value={name} onChange={handleNameChange} />
    </div>
  );
}

// Parent component
function Parent() {
  const [name, setName] = useState('');

  const handleNameChange = (newName) => {
    setName(newName);
  };

  return (
    <div>
      <h1>Hello {name}!</h1>
      <Child onNameChange={handleNameChange} />
    </div>
  );
}


```

## Explain the concept of conditional rendering in React and provide an example of how to implement it in a component.

Conditional rendering in React refers to the practice of rendering different parts of a component based on a certain condition. This allows us to display different content to the user based on the state of the application or the user's actions. 

For example, a login form may display a "login" button when the user is not logged in, and a "logout" button when the user is logged in.

To implement conditional rendering in a React component, developers can use conditional statements such as `if` and `else`.

```javascript
import React, { useState } from 'react';

function App() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  const handleLogin = () => {
    setIsLoggedIn(true);
  };

  const handleLogout = () => {
    setIsLoggedIn(false);
  };

  return (
    <div>
      {isLoggedIn ? (
        <button onClick={handleLogout}>Logout</button>
      ) : (
        <button onClick={handleLogin}>Login</button>
      )}
    </div>
  );
}

export default App;

```

## What are the main principles behind “Thinking in React” and how do they guide the process of designing and building a React application?

- Build an interface by breaking it apart into components
When building an interface in React, it's important to break it apart into smaller, reusable components. This involves identifying the different parts of the interface that can be abstracted into separate components, and building each component with its own set of props and behaviors. By breaking the interface apart into components, we can create a more modular and maintainable codebase that is easier to reason about and update over time. Each component should be built with the single responsibility principle.

- Describe the different visual states of each component
it's important to describe the different visual states of each component to ensure that the user interface remains consistent and intuitive. This involves breaking down each component into its individual states, and considering how it will look and behave in each state. For example, a button component may have different visual states for "hovered," "pressed," and "disabled," and it's important to design each state to be visually distinguishable and easy to understand.

- Connect the components together so data flows seemlessly through them
Additionally, it's important to connect the components together so that data flows seamlessly through them. This involves establishing clear data flows between components, and using React's props and state to manage and pass data between them. For example, a parent component may pass data down to a child component using props, and the child component may update the parent component's state using callbacks. By establishing clear data flows between components, we can create a well-organized and efficient React application that is easy to maintain and update.

## Things I want to know more about

- Nothing at the moment, other than lifting state through functional components and hooks

>References
>
>[React - Conditional Rendering](https://reactjs.org/docs/conditional-rendering.html)
>
>[React - Lists & Keys](https://reactjs.org/docs/lists-and-keys.html)
>
>[React - Forms](https://reactjs.org/docs/forms.html)
>
>[React - Lifting State](https://reactjs.org/docs/lifting-state-up.html)
>
>[React - Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
>
>[Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
>
>[React - Comprehensive Guide](https://tylermcginnis.com/reactjs-tutorial-a-comprehensive-guide-to-building-apps-with-react/)
>
>[Heroicons](https://heroicons.com/)
