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

## Gun.js: A Real-time Graph Database in Plain JS
### What is Gun?
A real-time, decentralized, offline-first graph database engine.

### Graphs
The web of data and relationships of a single or aggregate entity.

* Basic building block is "vertex"/"node" with key/value, reference to other node)
* List of references is called "set"
* Gun can create/traverse/read/update data in graph format

### Offline First
* Always stores data locally
* Syncs when online

### Real-time
* Uses pub/sub for synchronization

### Decentralized
* Each network/instance/node is fully operational

## Front End Resilience
Function in a hostile environment. The browser is "hostile" -- differing capabilities, settings, network conditions, etc.

### How Can Systems Fail?
* 3rd party availability
* Internal bugs
* The network
* User's privilege to alter experience (content blocker, rewriter, etc.)

### How Do We Handle It?
* Design for failure!

### Designing for Failure
* Prioritize critical parts of the page
* Make errors a first class citizen; design for the failure paths
  * Something broke; should I tell the user? Could they do anything about it?
* Report your errors back home

### Mitigate Risk
* Build in redundancy
* Serve stale content
  * With CDNs/cache, only expire after TTL when source is still available
  * Service worker can add another "local" CDN/cache to ensure that customized error behavior occurs

## Logging Off: Improving Low-Connectivity Experiences on the Web
* Types of limited connectivity: intermittence, slowness, limited bandwidth, sporadic
* aptivate.org has guidelines for data optimization

### Offline First
Treat being offline as part of the process rather than the error case.

## JavaScript: What's Sticking Around?
* Bikeshedding
* Programming
* Javascript
* Node.js
* Frustration
> "Every error is an opportunity to learn, almost always about yourself."
* "Legacy" code
* The need to ask for help
  * When to ask for help
    * How long has it been since you've made progress?
    * When pride's been swallowed
  * How to ask for help
    * Try first
    * Search, and research
    * Narrow down your problem
    * Keep and open mind
    * Overthank
* The compulsion to get complicated
* There is never a universally correct answer

## The Browser and the Brain
### Understanding
#### Programming Languages
* Define vocabulary with patterns and syntax with grammars
* Parsers read code and interpret with lexical and syntactic analysis by a lexer and a parser, respectively
* HTML is not context free and so it can't be parsed by a regular parser
* CSS _is_ a context-free language
* Both parsers generate a tree representing what they parsed

#### Natural Languages
* Have a lexicon and syntax that cannot be described by a context-free grammar
* Human language contains a lot of ambiguity
* **Steps**
  1. Break the unbroken speech stream into words
  1. The minds match the sounds to words in the mental lexicon
  1. Once we have access to the word, we have access to its meaning and its syntactic and thematic roles
  1. Then we can parse the sentence, but it's unclear how that works...
     * Modular View: the phrases involved occur separately in different modules
     * Interactive View: all available information can be used at once in parsing the sentence
     * Does this happen in serial or parallel?
* Humans are forgiving of syntax errors
* Receptive language processing occurs in the dominant hemisphere of the brain, in Wernicke's area  

### Visualizing
How does the human visual system paint a picture of the world; how does the browser render pictures to the screen?

#### Humans
1. Visible light goes into the eye via cornea and lens
1. Retina turns light into neural signals using rods and cones
1. Neural signals are sent to the brain
1. They are combined in the optic chiasm
1. Most signals are sent to the lateral geniculate nuclei
1. Signals end up at the primary visual cortex
1. Signals get sent to higher visual processing centers to perceive what is seen

#### Browsers
1. Evaluate langage to get the trees
1. DOM and CSSOM trees combined to form the render tree
1. Browser traverses render tree, calculating location and size of all elements
1. Browser traverses render tree, creating layers of bitmaps
1. Bitmaps sent to the GPU for compositing
1. Do it over and over, optimally 60 FPS

### Task Management
Can the human mind and the browser multitask?

#### Humans
* attention ... as a filter, as a spotlight, as control (blocking unwanted distractions and automated processes)
* attention ... as threads?
* Humans are bad at multitasking
  * inattentional blindness
  * dichotic listening task
  * shadowing

#### Browsers
* JavaScript doesn't multitask; it's single threaded
* Javascript can call out to APIs to _effectively_ multitask