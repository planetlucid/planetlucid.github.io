---
layout: post
title:      "Thoughts on React / Redux"
date:       2020-07-07 18:15:58 -0400
permalink:  thoughts_on_react_redux
---


These are the notes that I studied to help me grasp a greater understanding of React Redux.


## State vs Props

Both hold info that influences the UI in the browser.

What’s the Difference between State vs Props?

- Properties are the way we get Data into a components
- Props can be compared to html attributes like `<img src="dog.jpg" alt="dog">`
- Props is how the data get’s where it needs to go. Like a ‘bus or a car’..
- State is where the data lives. State is the data’s ‘home’.

 
## Props

    - how properties are passed down
    - props short for properties, is the optional input that your component can accept.
    - how does data get anywhere? Props.
    - It also allows the component content to be dynamic.
    - example - function parameters 

## State
 
    - Object that Lives in (parent) component - holds data that itself needs and that it children needs
    - managed within the component /
        - object that is privately maintained within a component
    - variables declared in the function body
    - can be changed within component
    - ex. setState is used in class components to change state
    - React ‘Reacts’ to the changes and updates the page.



## Connect
    - connects global store to component that is connected - this example `app`.
        - connects `app` to your global store and it gives access to global store value through `mapStateToProps`
    - if you wish to dispatch any action creator you’d have access through those in that component through `mapDispatchToProps`



## Global store
- contains states
- A store holds the whole state tree of your application. The only way to change the state inside it is to dispatch an action on it.
- A store is not a class. It's just an object with a few methods on it. To create it, pass your root reducing function to `createStore`.


----------
## Action vs Reducer
- Actions are payloads of information that send data from your application to your store. They are the only source of information for the store. You send them to the store using `store.dispatch()`.

- Reducers specify how the application's state changes in response to actions sent to the store. Remember that actions only describe what happened, but don't describe how the application's state changes.


----------
## Thunk
- Redux Thunk middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch` and `getState` as parameters.
----------


## Redux

We use redux through the global store. 

In my `index` - “import provider from react redux “. Redux gives us this provider component which we’re able to wrap app within. Provider allows us to give global access to everything within app.  Since everything lives within App component, we’ve given access to the global store everywhere.



## React Redux Flow


1. React component triggers something to happen
2. This trigger hits Action creator
3. The Action creator then hits middleware `thunk` 
4. Then `thunk` will dispatch an action to the reducer
5. The `reducer` depending upon the action it receives will then update that particular slice of state 
6. Which then gets pushed to global store
7. Which triggers a re-render to the component that references that slice of state.
    1. When the global store gets updated, that will trigger components that use that part of state to be re-rendered 
    2. Those components will React to changes in state.

## MapStateToProps
- gives access to state
- As the first argument passed in to `connect`, `mapStateToProps` is used for selecting the part of the data from the store that the connected component needs.


## MapDispatchToProps
-  is used for dispatching actions to the store.
- `dispatch` is a function of the Redux store. You call `store.dispatch` to dispatch an action. This is the only way to trigger a state change.


---

# Vanilla JS


## Promises
- Promise - 
    - Promises in JavaScript are an object representation of an asynchronous computation. You can think of a promise as a placeholder for a value that hasn't been computed yet. 
    - However, there's no way to get a promise's value from the promise directly - you need to call the `then()` function to register a callback that JavaScript will call when the value is computed.
        
- Chaining - 
    - Promise chaining is one of the key reasons why promises are so useful. The `then()` function returns a promise `p`, and if your `onFulfilled()` function returns a promise `q`, `p` will adopt the state of `q`.
