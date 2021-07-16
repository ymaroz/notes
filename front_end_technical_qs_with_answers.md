# Front End developer Technical Interview Questions

1.  Can you explain what happens from the time a user sends a request in a browser (by typing url on address bar and pressing enter) to the timewhen the page finish loading.
    Assume the page you are visiting is a RoR back end with a React SPA on the client side using GraphQL to obtain data. The Page you are navigating to shows a list of customers
2.  What is a Promise in Javascript? Why do they exist?
3.  Find a duplicate within an array.
4.  Using the following screenshots,
    - Please explain how you would break the screen down into React components?
    - And, where should the state reside if we use component state rather than Redux/Central/Context state manager?
      - If candidate Knows GraphQL ask about the placement of Queries and Mutations on the screen.
    - Follow Up questions:
    - How can we prevent a child component from re-rendering when its parent will re-render?
      - _Answer_. We use the lifecycle ShouldUpdate method, or use Pure/Memoized Components (these only re render if own state or props change). The first option is the one everyone should know
    - What is the difference between a class component and a function component
      - _Answer_. A class component allow us to add state and lifecycle functions to our component but it forces us to mix logic and rendering, so using functional components with HOC or hooks is preferred because allow us to separate concerns. Bonus. if he knows recompose library or can speak to react hooks
    - What is a HOC (High Order Component)?
      - _Answer_. It's a pure function (no side effects, always returns same result to same arguments) that allow us to inject logic into a component (through props)

![Second Screenshot][pic2]

[pic2]: ./assets/front_end_technical_qs_2.png
