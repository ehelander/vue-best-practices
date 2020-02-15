# Innofied

- [Top 10 Vue.js Best Practices](https://www.innofied.com/top-10-vus-js-best-practices/)
  1. Use data property on component
     - Use `data` property as a function which returns an object, rather than a property as a simple object.
       - When it's an object, it's shared across all instances of the component.
  2. Use kebab-case
     - Use kebab-case when writing any custom event name.
       - Event names are automatically changed to kebab-case internally.
       - Note: Example of sharing data between parent & child via event `$emit`.
  3. Rule for directive
     - Always use `:key` attribute with a `v-for` directive.
       - Used to check uniqueness of each of the list items.
  4. Rule for key attribute
     - Always use a unique ID (other than the index of the array) for `:key`.
       - Arrays are mutable, so the index of an item could be changed due to adding/removing items from the array.
  5. Rule for V-
     - Do *not* use `v-if` with `v-for`.
       - `v-for` has a higher priority than `v-if`.
     - Instead, compute (inside `computed: { computedList: function () { return computedList }}`) the list before rendering.
  6. Use of component properties
     - Use computed properties instead of method invocations for data changes.
       - Computed properties (inside `computed: {}`) are cached based on dependencies: They are only re-evaluated when their dependencies have changed.
       - A method invocation (inside `methods: {}`) will always run the function whenever a re-render happens.
  7. Use of multiple v-conditions
     - Do not use multiple `v-if` conditions to render multiple consecutive elements. Instead, wrap the elements in a `<template>` tag.
  8. Use key property
     - Use the `key` property to differentiate between instances of the same reusable element.
  9. Detection of changes in an array
     - Vue cannot detect changes within an array or an object. So, instead of setting these values directly, do one of the following:
       - Arrays:
         1. `Vue.set(vm.values, index, newValue)`
         2. `vm.values.splice(index, 1, newValue)`
         3. `vm.$set(vm.values, index, newValue)`
       - Objects:
         1. `Vue.set(vm.profile, 'lastname', "Doe")`
         2. `vm.$set(vm.profile, 'lastName', "Doe")`
  10. Use of shorthands
      - Either always or never use shorthands for directives.
        - `:`: `v-bind`
        - `@`: `v-on`
        - `#`: `v-slot`
