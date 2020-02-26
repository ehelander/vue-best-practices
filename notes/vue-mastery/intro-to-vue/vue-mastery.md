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
  - ![computed-properties](img/2020-02-25-19-59-23.png)
  - The computed property is cached and updates each time its dependencies change.
    - So it's more efficient to use a computed property than a method.
  - Approach 1: Updating image through method.
    - ![update-image_method](img/2020-02-25-20-01-26.png)
  - Approach 2: Updating image through computed property.
    - ![update-image_computed](img/2020-02-25-20-03-38.png)

## [8. Components](https://www.vuemastery.com/courses/intro-to-vue-js/components)

- Register a component via `Vue.component('componentName', {})`
- Options object
  - `template`
    - Template literal uses backticks.
      - [7 Ways to Define a Component Template in VueJS](https://medium.com/js-dojo/7-ways-to-define-a-component-template-in-vuejs-c04e0c72900d)
    - Template must return a single root element (e.g., wrapping `div`).
    - `data`: A function that returns a data object.
      - So that each instance of the component can have its own data.
    - `props`
      - In order to receive props, a component must explicitly declare which props it expects to receive in a `prop` array.
        - ![props](img/2020-02-25-20-12-02.png)
      - Recommendation: Use a `prop` object instead, with prop validation.
        - ![prop-validation](img/2020-02-25-20-13-33.png)
      - ![passing-prop](img/2020-02-25-20-16-42.png)
    - `methods`
    - `computed`

## [9. Communicating Events](https://www.vuemastery.com/courses/intro-to-vue-js/communicating-events)

- Emitting an event
  - `this.$emit('event-name')`
  - ![emitting-an-event](img/2020-02-25-20-24-39.png)

## [10. Forms](https://www.vuemastery.com/courses/intro-to-vue-js/forms)

- The `v-model` directive gives us two-way data binding.
  - ![v-model](img/2020-02-25-20-36-37.png)
- `number` in `v-model.number` is a modifier that casts `rating` to a number.
  - ![number-modifier](img/2020-02-25-20-48-38.png)
- The `.prevent` modifier prevents the default behavior (in this case,  the page from refreshing when the form is submitted).
  - ![prevent-modifier](img/2020-02-25-20-50-15.png)
- ![on-submit-method](img/2020-02-25-20-51-36.png)
- Sending our `productReview` object up to our parent:
  - ![product-review](img/2020-02-25-20-53-27.png)
  - ![add-review](img/2020-02-25-20-54-00.png)
  - ![reviews](img/2020-02-25-20-54-48.png)
  - ![show-reviews](img/2020-02-25-20-57-15.png)
- Can use HTML5 `required` attribute for required fields.
  - ![required](img/2020-02-25-20-58-07.png)
- Custom validation
  - Building an errors array:
    - ![errors](img/2020-02-25-21-00-08.png)
    - ![submission](img/2020-02-25-21-02-12.png)
- Resources:
  - [Modifiers](https://vuejs.org/v2/guide/forms.html#Modifiers)
  - [Event Modifiers](https://vuejs.org/v2/guide/events.html#Event-Modifiers)
  - [Custom Validation](https://vuejs.org/v2/cookbook/form-validation.html#Another-Example-of-Custom-Validation)

## [11. Tabs](https://www.vuemastery.com/courses/intro-to-vue-js/tabs)

- ![active-tab-class](img/2020-02-25-21-12-01.png)
- ![reviews-prop-validation](img/2020-02-25-21-15-45.png)
- ![v-show](img/2020-02-25-21-14-37.png)
- But ProductReview is now a grandchild of Product (through ProductTabs). So `addReview` is not defined.
  - We'll define a new global Vue `eventBus` instance
    - ![define-event-bus](img/2020-02-25-21-18-49.png)
    - ![emit](img/2020-02-25-21-19-39.png)
    - As soon as the Product component is mounted to the DOM, listen for the `review-submitted` event.
      - ![listen](img/2020-02-25-21-20-49.png)
- Resources
  - [Real World Vue.js](https://www.vuemastery.com/courses/real-world-vue-js/real-world-intro/) for life cycle hooks, Axios, routing, etc.
  - [Vuex](https://vuex.vuejs.org/) for more advanced state management
