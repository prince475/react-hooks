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


