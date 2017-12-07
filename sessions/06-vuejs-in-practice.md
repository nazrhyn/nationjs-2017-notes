# Vue.js in Practice: Hybridizing Objects and Functions
**Reactive Programming**   
Data changes in a top-down flow, allowing components to react to state hierarchically.

* Vue has computed properties
* `:prop` === `ng-attr-prop`
* `@click` === `ng-click`
* Lots of talking that applies to any data binding framework
* **two-way data binding**
  * parsing/formatting
  * tracking the source of changes
  * state managers created to deal with problems
* **vuex** is a redux-style state manager for Vue
  * "mutation" === "action"
  * get <- use a computed property retrieving value from the state
  * set <- use a computed setter similarly
  * More stuff about vuex features
* Create models that are template-/head-less components rather than bare JS class models (`Vue.extend(..)`, `new Vue(...)`)
