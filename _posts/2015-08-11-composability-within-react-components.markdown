---
layout: post
title: Composability within React Components
---

When building a complex React component, it’s important to keep in mind what makes a component maintainable, testable, reusable.

<!--more-->

It's helpful to think of React components as functions. When functions gets too large, it makes sense to refactor and think about how it can be broken down to a composition of smaller functions.

Some of the benefits of breaking down the `render` method of a React into smaller components are:

  * Separation of concerns/responsibilities per component
  * Input/output per component is well-defined  
  Think of a function’s parameters and return value. If the responsibility of a function is constrained, it needs to know less parameters and its return value is easier to reason about.
  * Testing is easier  
  This follows when input/output is well-defined. Test cases are easier to write. Less setup and teardown logic.
  * The render method is more readable  
  Each component’s render method is shorter. Setup logic for rendering is kept close to actual render logic.

Don’t these items sound familiar? They should, because it’s the same reasons behind refactoring large functions into smaller functions.

Related references:

  * <http://programmers.stackexchange.com/questions/166884/should-i-extract-specific-functionality-into-a-function-and-why>
  * <http://stackoverflow.com/questions/250284/best-practices-many-small-functions-methods-or-bigger-functions-with-logical-p>
