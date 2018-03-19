---
title: "Passing functions as parameters to Ember.js components"
date: 2017-11-12T16:12:12-06:00
slug: 'passing-functions-as-parameters-to-ember-js-components'
tags: ['Ember.js', 'Javascript', 'Programming']
---

When you pass arguments to components, these are usually values, i.e.  numbers,
strings, Ember Data models, etc... However, Ember.js does not really care what
type of object a computed property computes. Nothing prevents it from being a
function instead of a value.

This means that the following is perfectly fine.

    // components/outer-component/component.js

    export default Component.extend({
      widthAsFunction: computed(function() {
        return () => {
          return this.element.offsetWidth;
        }
      })
    });

    // components/outer-component/template.hbs
    {{inner-component
        widthAsFunction=widthAsFunction
    }}

and

    // components/inner-component/component.js

    export default Component.extend({
      width: computed('widthAsFunction', function() {
        return this.get('widthAsFunction')();
      })
    });

    // components/inner-component/template.hbs
    {{width}}

Why would you want to do this? There are certainly disadvantages to passing
functions instead of values:

1. Computing the function with `this.get('widthAsFunction')()` has the same
   syntax as invoking an action. As the semantics are very different, this can
   quickly lead to confusion.
2. It's against the conventions.
3. The function can return anything and can also have side-effects. So it's
   pretty easy to write spaghetti code that is hard to maintain.

The cases where you should use this are are rare but I found myself having to do
this when I wanted to delay the computation of the width in `inner-component`
until the value was actually needed. Imagine you would pass it as a value as in
the following:

    // components/outer-component/template.hbs
    {{inner-component
        width=element.offsetWidth
    }}

The value of the parameter `width` would be set once at the initialization of
`inner-component` and never updated. Indeed, `element.offsetWidth` is a normal
property on an object and not a "smart" Ember.js computed property. So when the
width of `outer-component` changes, the `width` property on `inner-component`
still keeps its value. By passing the width as a function, its value is not set
during initialization. Instead, it allows me to compute it exactly when I need
it during the lifetime of `inner-component`.

It's not a pretty pattern and it should be avoided when possible. However, in
some rare situations, it can provide a solution without too much extra code.
