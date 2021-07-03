---
layout: post
title:      "React Re-renders"
date:       2021-07-02 20:39:16 -0400
permalink:  react_re-renders
---

### Lifecycle Methods
In React, there are many methods that allow classes to run when a component mounts and unmounts. These methods are called Lifecycle Methods. Among the myriad of Lifecycle Methods, one of the most important is `render()`. Interestingly enough, it is the only required method for Component Classes to run, as it is what allows your JSX to be visible in your program. 

### shouldComponentUpdate()
In production, you may notice your application re-rendering often. This is due to another lifecycle method called `shouldComponentUpdate()`. This method takes in two arguments (nextProps and nextState) and assesses any changes to the component's props and state to determine if the component should update as it's name implies. By default this method returns true, allowing your component to be re-rendered whenever there is a change in props or state.

According to the React Documentation, this method exists only for Perfomance Optimization 'to minimize the number of costly DOM operations required to update the UI'. This lifecycle method is part of what makes React so efficient in mounting and unmounting elements . It compares the props and state on the DOM with the props and state on the virtual DOM. If they are the same, `shouldComponentUpdate()` will return false and no re-render will occur. However, if they are different, `shouldComponentUpdate()` will return true, and the re-render will occur. 

Read more about React Component Lifecycle [here](https://reactjs.org/docs/react-component.html)
