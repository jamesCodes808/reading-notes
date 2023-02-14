# State And Props

## React Lifecycle

- Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?

The render phase happens first before componentDidMount

- What is the very first thing to happen in the lifecycle of React?

Mounting is the first thing to happen in the component lifecycle. Mounting includes the constructor, getDerivedStateFromProps, render, React updates DOM and refs, then componentDidMount.

- Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates

constructor, render, react updates, componentDidMount, then componentWillUnmount

- What does componentDidMount do?

After a component is mounted, componentDidMount() is invoked. In componentDidMount(), we use anything that uses a network request(API Request), initalizes the DOM and sparingly setState. We can set up 'subscriptions' in here and unsubscribeusing componentWillUnmount(). 

## React State Vs Props

- What types of things can you pass in the props?

They are like arguments to a function, we can pass things we want to initialize our component to such as initial counters, titles, values.

- What is the big difference between props and state?

With props you pass it into the component and it is handled/updated outside of the component,

state is handled inside of the component and updated inside.

When state changes inside of application, its going to re-render that component of your application.

- When do we re-render our application?

We want to re-render the application when something needs to change based on user input.

- What are some examples of things that we could store in state?

Some examples are counters, forms, input elements and things that need to be updated by the user.

>References
>
>[React: Component Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)
>
>[React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)
>