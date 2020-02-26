# Intro to Vue.js

## [1. The Vue Instance](https://www.vuemastery.com/courses/intro-to-vue-js/vue-instance)

- Vue dev tools (Chrome or FireFox)
  - Can see structure of application, as well as data, props, etc.
  - Must check `Allow access to file URLs`.
- Simplest Vue application:
  - ![simple-vue-app](img/2020-02-15-15-34-45.png)

## [2. Attribute Binding](https://www.vuemastery.com/courses/intro-to-vue-js/attribute-binding)

- `v-bind`
  - Dynamically binds an attribute to an expression.
  - ![v-bind](img/2020-02-15-15-45-32.png)
  - ![v-bind-example](img/2020-02-15-15-46-14.png)
  - Fully syntax:
    - `v-bind:alt="description"`
  - Shorthand:
    - `:alt="description"`

## [3. Conditional Rendering](https://www.vuemastery.com/courses/intro-to-vue-js/conditional-rendering)

- Conditional directives: `v-if`, `v-else-if`, `v-else`
  - ![conditional-directives](img/2020-02-15-15-54-39.png)
  - `v-if` will actually add or remove this element from the DOM.
    - If we're dealing with an element that will be being shown and hidden frequently, `v-show` can be more performant. Rather than adding or removing it from the DOM, it toggles `display: none;`.
    - ![v-show](img/2020-02-15-15-57-02.png)

## [4. List Rendering](https://www.vuemastery.com/courses/intro-to-vue-js/list-rendering)

- `v-for`: Loops over each item in an array
  - ![v-for](img/2020-02-15-16-18-29.png)
  - It's highly recommended to use a `key` so Vue can keep track of the element.
    - ![key](img/2020-02-15-16-21-22.png)

## [5. Event Handling](https://www.vuemastery.com/courses/intro-to-vue-js/event-handling)

- `v-on`: Listens for specified event, then performs the attached expression.
  - ![v-on](img/2020-02-15-16-25-58.png)
  - ![v-on_method](img/2020-02-15-16-27-58.png)
  - Shorthand: `@`
  - ![v-on_parameter](img/2020-02-15-16-30-14.png)
    - Can also use shorthand (though some browsers may not support it):
      - ![method-shorthand](img/2020-02-15-16-31-21.png)
- Event examples:
  - `@click`
  - `@mouseover`
  - `@submit` (on a `<form>`)
  - `@keyup.enter`
    - Note that `.enter` is a modifier.

## [6. Class & Style Binding](https://www.vuemastery.com/courses/intro-to-vue-js/class-&-style-binding/)

- Style binding
  - ![style-binding](img/2020-02-15-16-48-17.png)
  - Can use camelCase (because it's in an object); can also use kebab-case, but the property must be wrapped in quotation marks.
    - ![style-binding_kebab-case](img/2020-02-15-16-50-17.png)
  - Can also bind to a style object. This is often preferable.
    - ![style-binding_object](img/2020-02-15-16-51-09.png)
  - The styles from multiple objects can be added via an array.
    - ![style-binding_array](img/2020-02-15-16-52-13.png)
- Class bindings
  - ![class-binding](img/2020-02-15-16-56-25.png)
    - This *adds* classes: Any classes that are directly assigned to the element are still present.
  - This assigns the `.disabledButton` class (from the style sheet) whenever `inStock` is falsy:
    - ![class-binding](img/2020-02-15-16-55-03.png)
  - We can also bind an object of classes:
    - ![class-binding_object](img/2020-02-15-17-00-28.png)
  - We can also add an array of classes:
    - ![class-binding_array](img/2020-02-15-17-01-25.png)
  - We can also apply classes conditionally:
    - ![class-binding_conditional](img/2020-02-15-17-03-43.png)

## [7. Computed Properties](https://www.vuemastery.com/courses/intro-to-vue-js/vue-computed-properties)

- `computed` properties:
  - ![computed-properties](2020-02-25-19-59-23.png)
  - The computed property is cached and updates each time its dependencies change.
    - So it's more efficient to use a computed property than a method.
  - Approach 1: Updating image through method.
    - ![update-image_method](2020-02-25-20-01-26.png)
  - Approach 2: Updating image through computed property.
    - ![update-image_computed](2020-02-25-20-03-38.png)

## [8. Components](https://www.vuemastery.com/courses/intro-to-vue-js/components)

- Register a component via `Vue.component('componentName', {})`
- Options object
  - `template`
    - Template literal uses backticks.
      - [7 Ways to Define a Component Tempmlate in VueJS](https://medium.com/js-dojo/7-ways-to-define-a-component-template-in-vuejs-c04e0c72900d)
    - Template must return a single root element (e.g., wrapping `div`).
    - `data`: A function that returns a data object.
      - So that each instance of the component can have its own data.
    - `props`
      - In order to receive props, a component must explicitly declare which props it expects to receive in a `prop` array.
        - ![props](2020-02-25-20-12-02.png)
      - Recommendation: Use a `prop` object instead, with prop validation.
        - ![prop-validation](2020-02-25-20-13-33.png)
      - ![passing-prop](2020-02-25-20-16-42.png)
    - `methods`
    - `computed`

## [9. Communicating Events](https://www.vuemastery.com/courses/intro-to-vue-js/communicating-events)

- Emitting an event
  - `this.$emit('event-name')`
  - ![emitting-an-event](2020-02-25-20-24-39.png)

## [10. Forms](https://www.vuemastery.com/courses/intro-to-vue-js/forms)

- The `v-model` directive gives us two-way data binding.
  - ![v-model](2020-02-25-20-36-37.png)