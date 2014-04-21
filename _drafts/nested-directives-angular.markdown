---
layout: post
title: Exposing Options in Nested Directives in AngularJS
---

Ever thought of using a directive within a directive?
How would you expose the options of the nested inner directive on the outer directive?

Example:
I want to use the datepicker directive in UI bootstrap in my own directive. Say a time range picker:

Wrap into two time pickers:
- Directive's template has two time pickers

What if let's say now, I want to add an option such as no picking a weekend for the start date?

### Meh solution

Add a new scope variable bound to an attribute

Here's what it'll look like:

### What's wrong with meh solution?

What if you want to add another option now? What if there were many options on the time picker directive? Adding a scope variable etc. is a lot of trouble.

- Also consider the case of this: default options. You need default options for the scope variable even if the thing isn't set?
- Setting up default options can be a lot of code
- Need default option of each variable
- Dirty

Or if you update the timepicker and need a new attribute?
Does this solution scale? No.

### Attributes on demand

- Options are specified through attributes
- Why not add attributes only if they're needed?
- Use a prefix to pipe options from the parent directive to the child directive
- Determine if an option is used on the compile step. On the compile step, the template is already available.
- Add the option on compile.
- Create a watcher on linking to link value to the sub-directive.

See how this looks:

Pros:
- No need to handle default options
- Any option in the child directive can be used as an option on the parent directive
- Customizable through the prefix

Cons:
- Prefix creates a layer of abstraction/convolution.
  Reader has to understand that the prefix refers to the underlying child directive
- Introduce coupling and hidden dependency
