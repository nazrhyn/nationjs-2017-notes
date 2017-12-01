# NationJS 2017
blah blah blah

## Kung Fu Moves for the Front-End Hero
1. Prevent regressions with Git hooks
   * Block commits when analysis errors are present
   * Do something simple; must execute quickly
1. Manage code complexity
   * jscomplexity.org evaluates cyclomatic complexity
   * Cyclomatic complexity is how many execution paths exist in the code
   * `cr -f plain file.js`
   * Consider maintenance/future readers when writing code
1. Monitor and track code coverage
   * Istanbul (NYC) for tracking coverage
   * Karma test runner has easy-to-enable coverage
   * Many online tools can consume the coverage report and track it over time
   * Coverage should be part of the ci/build system
   * Pull/merge requests should integrate with coverage and alarm/inform upon coverage decrease
1. Run quick smoke tests with evergreen browsers
   * Appveyor can easily run tests on windows
   * Chocolatey is a windows package manager
1. Test your downstream projects
   * Verify that changes don't break packages that depend on you

Parallelize when possible!

## The Variable Crimes We Commit Against JavaScript
### scope
* No `var`/`let`/`const` assigns to `window`/`global`
* Functions create a new scope
  * Child functions have a scope that inherits from the parent scope
* `var` only scopes to functions while `let`/`const` scopes to _blocks_

### types of functions
* function statement (named function)
* function expression

### hoisting
* `var` definitions are hoisted to the top of their scope
  * As `var thing = 5;`, it's split into hoisted definition (`var thing;`) and in-place assignment (`thing = 5`)
* Function statements (named functions) are hoisted to the top of the scope

### closure
(Nowhere near enough detail on this.)

### arrays & objects
* Objects and arrays are dealt with by reference

### es6
* `let`/`const` to array/object makes a constant reference, not a constant array/object
* `let`/`const` scope to _blocks_, including for-loop variables
* It is possible to create an anonymous block

## Building a Chat Bot With API.ai
API.ai is now called Dialogflow.

* "Intent Mapping" translates natural language into "what to do"
* Top-level entity is "agent"
* Several one-click integrations with various services
* Intents have several properties
* Does **not** do natural language evaluation, actually. Derp.
* Basically just lets you configure input-to-output mapping

## I Didn't Know the Browser Could Do That!
### Speech API
* `window.speechSynthesis`
* `SpeechSynthesisUtterance(...)`
* `synth.speak(utterance)`
* `synth.getVoices(...)`

### Speech Recognition API
* `SpeechRecognition` instance
  * `interimResults` keeps updating
* callbacks
* Chrome only

### Geolocation API
* `navigator.geolocation.getCurrentPosition(...)`

### Notifications API
* Native notifications where possible
* `Notification.requestPermission(cb)`
* `not = new Notification(...)`
* `not.onclick` handler

### Push Notification API
* Uses a service worker
* add listener for `'push'` and do stuff

### Battery Manager API
* Detects charge amount, charging
* callbacks

### Media Recorder API
* `getUserMedia({ video: boolean, audio: boolean }): Stream`
* `new MediaRecorder(stream)`
  * `ondataavailable`, `onend`, `.start()`

### Web Audio API
* Create sounds by pitch, tone, etc.
* `new AudioContext()`
* `ctx.createOscillator()`
* `osc.connect(ctx.destination)`

### Vibration API
* `navigator.vibrate(ms|ms[])`

### Device Orientation API
* `window` event `deviceorientation`

### Others
* Payment API
* Bluetooth API
* Web USB API

## Building Microservices in NodeJS
Small, independently developed services that perform specific tasks. Should be small enough to be torn down and rewritten completely within 1-2 sprints.

### Advantages
* Separation of concerns
* Smaller, faster deployments
* Technological heterogeneity
* Resilience

### Common Stumbling Blocks
1. **Infrastructural Complexity**   
   Large number of services with heterogeneous stacks becomes a devops issue.
   * Pick a CI/CD tool
   * Pick a good platform service with good APIs for quick build-up/tear-down
   * Containerization technologies (Docker, etc.)
     * Build once, run everywhere; single image used in all environments
   * kubernetes (container orchestration platform) for monitoring, management (automatic scaling, etc.), service discovery, logging
1. **Microservice Overhead**   
   How to deal with standardization and tooling across all service repositories.
   * NodeBootstrap helps to create new microservices using templates and code generation
   * Some kind of scaffolding tool to help with the problem of bootstrapping, maintenance, tooling, etc.
1. **Lock-step Deployments**   
   How to deal with all the insane interdependencies in deployment.
   * Eliminate lock-step deployment by attempting to ensure that services are autonomous and have minimal interdependencies.
   * Domain-driven design can be used to ensure that all domains are correctly and comprehensively defined.
   * Eventstorming (from "brainstorming"). Get everyone together and figure out all events possible and then organize them visually. Use post-it notes. Where are the boundaries?
   * When dependencies exist, implement changes from leaf to root.
1. **Inside vs. Outside**   
   Differentiate between internal use and external use; conflating the two into one service means they both have to change at the same time.
   * Create discrete microservices for external APIs so that they can change independently.
     * These act as a facade for access to the internal APIs.

### People and the Organization
* Employees/teams have to move to this pattern conceptually/mentally.
* Engage the whole company to figure out what the impacts are and what the whole picture is for the change.

## Vue.js in Practice: Hybridizing Objects and Functions
**Reactive Programming**   
Data changes in a top-down flow, allowing components to react to state hierarchically.

* Vue has computed properties
* `:prop` = `ng-attr-prop`
* `@click` = `ng-click`
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

## Gun.js: A Real-time Graph Database in Plain JS
### What is Gun?
A real-time, decentralized, offline-first graph database engine.

### Graphs
The web of data and relationships of a single or aggregate entity.

* Basic building block is "vertex"/"node" with key/value, reference to other node)
* List of references is called "set"
* Gun can create/traverse/read/update data in graph format

### Offline First


### Real-time
### Decentralized

## Front End Resilience

## Logging Off: Improving Low-Connectivity Experiences on the Web

## JavaScript: What's Sticking Around?

## The Browser and the Brain