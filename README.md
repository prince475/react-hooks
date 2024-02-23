# React Hooks

Hooks are one of the programmatic react features. They are used to access different React features from your component.
This concept is also extended to React Dom where the React-dom contains specific Hooks for web application which run the browser DOM environment.
In this lesson we will examine and focus on the React Hooks

```txt
    - Hooks in react start with the term "use" this includes any function stating with use or variables.
    - Hooks are special functions that are only available while React id rendering and they let you "hook into" react features.
    - Hooks or functions starting with use can only be called at the top level of your component similar to 
      how you "import" modules at the top level of your file.
```

## Definition by Usage

Hooks allow a developer to use different React features from a given component.

There are of two different types:

1. Built-in React Hooks
2. Custom React Hooks

## Built-in React Hooks

The built-in React Hooks can be categorized further by the different parts of the application they access as well as the use case.
Build-in React Hooks Categories are:

- State Hooks
- Context Hooks
- Ref Hooks
- Effect Hooks
- Performance Hooks
- Resource Hooks

## Custom React Hooks

Other than the built-in React Hooks, other times as a developer you might require a Hook for some more specific functionality: eg
fetching data, Keeping track of whether the user is online or offline in your application, or connecting to a chat-bot service.
Such hooks with these specific functionality might not be found in the Build-in React Hooks, but the good thing is that you can easily
create your own hooks to suit your application needs. That is where the term "Custom" derives from.

### State Hooks

In react a State Variable aids a component "to remember".

```txt
    State variables refer to a piece of data that is managed within a component and are used to store
    information that can change over time. These variables also drive the behavior and appearance of a 
    component.
```

Information that as a developer you might need your application to recall may include something like "User Input Value" or The index
of an image in a gallery.

React state can be added to a component using two hooks:

```txt
    - useState: This is used to declare a state variable that you can update directly.

    - useReducer: Declares a state variable with the update logic inside a reducer function.
```

`Below is an example of how useState is used in react. Here state is used to store the selected image index`

```js
    function ImageGallery() {
    const [index, setIndex] = useState(0);
    }
```

### useState Hook

This hook allows you as a developer to add a state variable to your components.
useState can be referred to as component specific memory used to update the application components when a user has interaction with the UI.
For example, when updating an input field when a user types into a form field.

The challenge encountered to make one consider using useState:

1. Local variables do not persist between renders
2. Changes to local variables won't trigger renders

```txt
    When updating a component with new data in react, you need to account for two things:
     - To attain an effective update data must be retained between renders and
     - A trigger action must be set to render the component with new data which 
       in other terms is called re-rendering. 
```

Therefore, the `useState` hook is used to as a remedy to this problem as:

- It allows a state variable to retain the data between renders.
- a function called a state setter function which updates the variable and triggers react to re-render the component.

### The process of adding a state variable to your react component.

- Import `useState` from React at the top level of your component.

    ```js
        import { useState } from 'react';
    ```

- Then write your state variable and like in our case:

    ```js
        const [index, setIndex] = useState(0);
    ```

- `index` is a state variable while `setIndex` is the setter function.

- `The curly braces syntax is called array destructuring which allows the developer to read values from an array.`

### `useState` Use Case Example: Moving Images in a Gallery 

Let's consider, we have a list of images (name, artist, and description), that we are displaying in the gallery 
screen of our application.

- We would like to have a button `Next` which when clicked loads the next image and its corresponding details.

- Sample execution code of this example look like:

```js
    import { useState } from 'react';
    import { imageList } from './data.js';

    export default function Gallery() {
        const[index, setIndex] = useState(0);

        function handleClick() {
            setIndex(index + 1);
        }

        let image = imageList[index];

        return(
            <>
                <button onClick={handleClick}>
                    Next
                </button>
                <h2>
                    <i>{image.name}</i>
                    by {image.artist}
                </h2>
                <h3>
                    ({index + 1} of {imageList.length})
                </h3>
                <img
                    src={image.url}
                    alt={sculpture.alt}
                />
                <p>
                    {image.description}
                </p>
            </>
        )
    }
```
### How useState Works

When `useState` is called, essentially you are commincating with React and telling it you want the component where the function is being called to remember a certain thing.
In our case: we would like React to remember `index`. 

```js
    const [index setIndex] = useState(0);
```  

In our example`useState` takes only one argument which is the initial value of the state variable and that value is set to 0 with useState(0). 
During our component re-render,`useState` provides us with an array containing two values namely:

- The state variable (`index`) with the vaule stored initially
- A state setter function (`setIndex`) that can update the state variable and trigger React to render the component again.
  - Our component renders the first time. Because we passed 0 to useState as the initial value for index, it will return [0, setIndex]. React remembers 0 is the latest     state value.
  - State updates: When a user clicks the button, it calls setIndex(index + 1). index is 0, so it’s setIndex(1). This tells React to remember index is 1 now and triggers another render. 
- React still sees useState(0), but because React remembers that you set index to 1, it returns [1, setIndex] instead.         

Giving a component multiple state variables 
In React your application can have as many state variables of as many types as you like in one component. This component has two state variables, a number index and a boolean showMore that’s toggled when you click “Show details”:

It is always a good idea to have multiple state variables if their state is unrelated, like index and showMore in this example. 
But if you find that you often change two state variables together, it might be easier to combine them into one. For example, if you have a form with many fields, it’s more convenient to have a single state variable that holds an object than state variable per field.
