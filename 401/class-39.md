# React 3

## What is React Context, and how does it help in managing state and data sharing in a React application?

React Context is a feature in React that allows data to be passed down the component tree without the need to pass props manually at each level. It provides a way to share data between components without the need for intermediate components to pass data down explicitly.

Context helps in managing state by providing a global state accessible by all the components that subscribe to it. This eliminates the need for props drilling, which can make the code cleaner and more maintainable. 

Context API can be used with a `Provider` and a `Consumer`. The `Provider` component is used to wrap the components that need access to the context data. The `Consumer` component is used to access the context data from within any child component of the `Provider`. 

Using props drilling: 

```javascript
export default function App({ theme }) {
  return (
    <>
      <Header theme={theme} />
      <Main theme={theme} />
      <Sidebar theme={theme} />
      <Footer theme={theme} />
    </>
  );
}

function Header({ theme }) {
  return (
    <>
      <User theme={theme} />
      <Login theme={theme} />
      <Menu theme={theme} />
    </>
  );
}
```

using React Context:

```javascript
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="test">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  return (
    <UserContext.Consumer>
      {value => <h1>{value}</h1>} 
      {/* prints: test */}
    </UserContext.Consumer>
  )
}
```

## Explain the useContext Hook and how it can be used to access data from a React Context within a functional component.

With the `useContext` Hook from React, we can allow functional components to access data from a React Context without the need for a consumer component by directly accessing the context object created by the `Provider` component.

First, we create a `Context` using the `createContext` method, can be done in a separate or the same file. 

Then, we create a `Provider` component using the `Provider` property of the `Context` object and pass any data that needs to be shared to it through the value prop.

Last, in the functional component where the data is needed, we use the `useContext` Hook to access that data directly from the `Context` object. 

```javascript
import React, { useContext } from 'react';

const MyContext = React.createContext();

function ParentComponent() {
  return (
    <MyContext.Provider value="Hello, World!">
      <ChildComponent />
    </MyContext.Provider>
  );
}

function ChildComponent() {
  const contextValue = useContext(MyContext);
  return <div>{contextValue}</div>;
}


```

## Describe the purpose of Next.js, and provide an example from the Vercel Next.js Examples reading on how it can be used to build a scalable web application.

Next.js is a framework built on top of the React framework. Next.js gives you the posibility of rendering on the client side, server side or both. 

Aside from this fact, there are more than 50 complex built in components and libraries that can help with streamlining and building a scalable web application. 

One example is the built in `blog-starter` files and components such as a `post-body.tsx`, `intro.tsx` and `header.tsx`

```javascript
// Built in header.tsx
import Link from 'next/link'

const Header = () => {
  return (
    <h2 className="text-2xl md:text-4xl font-bold tracking-tight md:tracking-tighter leading-tight mb-20 mt-8">
      <Link href="/" className="hover:underline">
        Blog
      </Link>
      .
    </h2>
  )
}

export default Header

// Built in post-body.tsx
import markdownStyles from './markdown-styles.module.css'

type Props = {
  content: string
}

const PostBody = ({ content }: Props) => {
  return (
    <div className="max-w-2xl mx-auto">
      <div
        className={markdownStyles['markdown']}
        dangerouslySetInnerHTML={{ __html: content }}
      />
    </div>
  )
}

export default PostBody

// Built in intro.tsx
import { CMS_NAME } from '../lib/constants'

const Intro = () => {
  return (
    <section className="flex-col md:flex-row flex items-center md:justify-between mt-16 mb-16 md:mb-12">
      <h1 className="text-5xl md:text-8xl font-bold tracking-tighter leading-tight md:pr-8">
        Blog.
      </h1>
      <h4 className="text-center md:text-left text-lg mt-5 md:pl-8">
        A statically generated blog example using{' '}
        <a
          href="https://nextjs.org/"
          className="underline hover:text-blue-600 duration-200 transition-colors"
        >
          Next.js
        </a>{' '}
        and {CMS_NAME}.
      </h4>
    </section>
  )
}

export default Intro
```

## Things I want to know more about

- How to efficiently use the built in vercel/next.js libraries and customize them to my liking.

- I would like to dive deeper into why Next.js is prefferred over React.js

>References
>
>[NextJs](https://nextjs.org/learn/basics/getting-started)
>
>[React Context for Beginners](https://www.freecodecamp.org/news/react-context-for-beginners/)
>
>[Why I’m using Next.js in 2020](https://www.youtube.com/watch?v=rtgbaKBhdkk)
>
>[Learn useContext In 13 Minutes](https://www.youtube.com/watch?v=5LrDIWkK_Bc)
>
>[Next.js Examples](https://github.com/vercel/next.js/tree/canary/examples)