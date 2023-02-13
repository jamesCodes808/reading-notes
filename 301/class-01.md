# Introduction to React and Components

## Component-Based Architecture

- What is a "component"?

Components are modular, portable, replaceable and reusable sets of well-defined functionality that encapsulates its implementation and exports it as a higher-level interface. They are like javascript functions that have reusable, independent pieces of UI. They can accept arbitrary inputs, called 'props' and return React elements that describe what should appear on the screen. This is how to create a component: 

```javascript

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

```

- What are the characteristics of a component?

Reusability − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task.

Replaceable − Components may be freely substituted with other similar components.

Not context specific − Components are designed to operate in different environments and contexts.

Extensible − A component can be extended from existing components to provide new behavior.

Encapsulated − A A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any internal variables or state.

Independent − Components are designed to have minimal dependencies on other components.

- What are the advantages of using component-based architecture?

Ease of deployment − As new compatible versions become available, it is easier to replace existing versions with no impact on the other components or the system as a whole.

Reduced cost − The use of third-party components allows you to spread the cost of development and maintenance.

Ease of development − Components implement well-known interfaces to provide defined functionality, allowing development without impacting other parts of the system.

Reusable − The use of reusable components means that they can be used to spread the development and maintenance cost across several applications or systems.

Modification of technical complexity − A component modifies the complexity through the use of a component container and its services.

Reliability − The overall system reliability increases since the reliability of each individual component enhances the reliability of the whole system via reuse.

System maintenance and evolution − Easy to change and update the implementation without affecting the rest of the system.

Independent − Independency and flexible connectivity of components. Independent development of components by different group in parallel. Productivity for the software development and future software development.

## Props

- What is “props” short for?

"Props" is a keyword used in React and stands for properties.

- How are props used in React?

Props are used for passing data from one component to another. Like this:

```javascript

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}

```

- What is the flow of props?

The data flow with props are being passed in a uni-directional flow. This means that the data flows downwards from parent to child.

>References
>
>[Component-Based Architecture](https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm)
>
>[Components and Props](https://reactjs.org/docs/components-and-props.html)
>
>[What is “Props” and how to use it in React?](https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0)
>

## Things I want to know more about

- How to pass props amongst sibling components?

- Are props the same as variables and what are their natural scopes?