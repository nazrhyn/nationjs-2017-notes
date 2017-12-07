# NationJS 2017
These are my notes for each session.

## [Kung Fu Moves for the Front-End Hero](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/01-kung-fu-moves-for-the-front-end-hero.md)
<sup>Ariya Hidayat ([@ariyahidayat](https://twitter.com/ariyahidayat) | [/ariya](https://github.com/ariya))</sup>   
After you built an awesome app using React and integrated its Mocha tests with Jenkins, what should you do next? To reach the highest app quality and to move yourself to the next level, there is a few more skills you need to master: leverage Git hooks, manage code complexity, monitor code coverage, run smoke tests with evergreen browsers, and track the downstream projects.

## [The Variable Crimes We Commit Against JavaScript](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/02-the-variable-crimes-we-commit-against-javascript.md)
<sup>Julka Grodel ([@jgrodel](https://twitter.com/jgrodel))</sup>   
Have you ever put a value into a JavaScript variable, and then been unable to use it where you needed it? Or created it and unintentionally overridden something you thought wouldn't be effected? JavaScript has an unusual way of handling where variables are available, we call this "where" a scope. In this talk, we'll go over how JavaScript variables 'bubble' up into higher scopes, how to restrict them to just where you want them, and how this effects variables in your functions.

Scopes in JavaScript are a misunderstood aspect by many developers and can create frustration when troubleshooting code. This talk doesn't require any knowledge of JavaScript specifically, but a proficiency in some programming language is helpful.

## [Building a Chat Bot with API.ai](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/03-building-a-chat-bot-with-apiai.md)
<sup>Erin Page ([@erinmpage](https://twitter.com/erinmpage) | [/erinpagemd](https://github.com/erinpagemd))</sup>   
A "new" way of communicating with your computer/devices is on the rise: VOICE. How do we make a program understand our determinations with words? Enter API.ai, a platform for mapping intents. Attendees will git a quick rundown of API.ai and see it used in a live chatbot. A more complicated chatbot made with Ruby will be demonstrated to show the some of the more advanced usages of API.ai. There are a lot of tools out in the market that attempting to resolve similar issues as API.ai. Let's start learning about these new class of tools. Limitations and alternatives to API.ai will be discussed.

## [I Didn’t Know the Browser Could Do That!](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/04-i-didnt-know-the-browser-could-do-that.md)
<sup>Sam Bellen ([@sambego](https://twitter.com/sambego))</sup>   
Everyday, you’re working with a web-browser, but do you know all of it’s capabilities? These wonderful pieces of software are much more powerful than they appear. This talk will take you through some of the lesser know but definitely double as cool browser api’s.

## [Microservices in Node.js: Practices, Pitfalls, and Prevention](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/05-microservices-in-nodejs.md)
<sup>Justin Bachorik ([@justinbach](https://twitter.com/justinbach) | [/justinbach](https://github.com/justinbach))</sup>   
Microservice architecture is growing in popularity at a rapid pace — and for good reason. When implemented correctly, the use of microservices can confer huge technological and organizational advantages. All too often, though, microservices are sold as a panacea that will solve whatever problems your team might have, and due consideration is not given to the tradeoffs involved in adopting a microservice-oriented approach. In this talk, Justin Bachorik will provide an introduction to the advantages and potential drawbacks of microservice architecture and will present a number of Node.js-oriented solutions for avoiding common issues.

## [Vue.js in Practice: Hybridizing Objects and Functions](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/06-vuejs-in-practice.md)
<sup>Betsy Haibel ([@betsythemuffin](https://twitter.com/betsythemuffin) | [/bhaibel](https://github.com/bhaibel))</sup>   
Vue.js isn't the new kid on the block any more. It's something we write for actual money nowadays. We also read and extend other people's Vue code for actual money. It's time to start looking at what design patterns are useful in large-scale Vue apps, to help keep the framework elegant and comprehensible as complexity grows. Luckily, the framework itself can be our inspiration. Part of Vue's "secret sauce" is its elegant blend of functional and object-oriented programming paradigms: instead of demanding purity in one or the other, it hybridizes them to create an easy-to-use developer experience.

In this talk, we'll look at methods both functional (partial application) and object-oriented (unmounted data-store components) and figure out when it's best to use which strategy – as well as when and how to blend them. You'll learn common gotchas, as well! Whether you use Vue or React or even Ember day-to-day, you'll come away with a better understanding of reactivity's blessings and pitfalls in larger applications.

## [Gun.js: A Real-time Graph Database in Plain JS](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/07-gunjs-a-real-time-graph-database-in-plain-js.md)
<sup>Spencer Jones ([@jones_spencera](https://twitter.com/jones_spencera) | [/sjones6](https://github.com/sjones6))</sup>   
Query data from client-side JS? Easy.

Real-time updates across a distributed system? A cinch.

Apps must be fast, highly-available, and run on any device. This talk will demonstrate how a resilient, distributed network can be easily created with Gun while solving common challenges like offline usability, real-time updates, and data replication. All this without needing anything but JavaScript!

## [Front End Resilience](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/08-front-end-resilience.md)
<sup>Ian Feather ([@ianfeather](https://twitter.com/ianfeather) | [/ianfeather](https://github.com/ianfeather))</sup>   
When building sites at BuzzFeed, our priority is always to create resilient front ends which are tolerant to failure of different kinds. We value an experience which is available no matter what device, browser or network connection the user is browsing with.

Accomplishing this isn’t easy but we’ve learnt a few tricks along the way which we would love to share! I’ll explain the principles behind our approach as well as detailing some of the solutions we have put in place: covering areas of automation, instrumentation and continuous testing in production.

## [Logging Off: Improving Low-Connectivity Experiences on the Web](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/09-logging-off.md)
<sup>Valerie Woolard Srinivasan ([@valeriecodes](https://twitter.com/valeriecodes))</sup>   
We'll discuss why it's important to optimize our web sites and applications for people with bandwidth or connectivity constraints. This is crucial both for users of mobile devices and for users with unreliable internet connections due to geographic factors. I'll outline some of the principles of offline-first development and the tools that are available to help developers build a good offline experience. I'll also go through some of the web design guidelines for low bandwidth and share pointers for making sites friendlier to users with limited bandwidth, such as clearly signaling large downloads, scaling down images, and limiting the size of pages.

Attendees should have some familiarity with making web pages and will leave with many useful tools for improving experience for users with connectivity constraints.

## [JavaScript: What's sticking around?](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/10-javascript-whats-sticking-around.md)
<sup>John K Paul ([@johnkpaul](https://twitter.com/johnkpaul) | [/johnkpaul](https://github.com/johnkpaul))</sup>   
A new framework, library or hammer-looking-for-nail comes out every 24 hours. Most talks consider if you should be swiping left or swiping right, but I want to talk to you about what will matter regardless of your specific technology choices.

In this sea of the bleeding edge, there are islands of stability. There are core ideas, debugging techniques, software design tenants, classic study skills and human fundamentals that won’t change with or without React 17 dropping like it’s hot. Debugging and coping with the subsequent frustration, for example, will last you the rest of your career.

We will walk through examples of steadfast techniques and tools for how you can build better software, most notably JavaScript applications on the server or the client. I expect everyone to walk away with a calm serene feeling of contentment, regardless of what legacy system they have to maintain or “better" technology decision they weren’t able to make.

## [The Browser and the Brain](https://github.com/nazrhyn/nationjs-2017-notes/blob/master/sessions/11-the-browser-and-the-brain.md)
<sup>Jenna Zeigen ([@zeigenvector](https://twitter.com/zeigenvector) | [/jennazee](https://github.com/jennazee))</sup>   
Computers and brains are often used as metaphors for one another, but how does a web browser compare to the human brain? We’ll compare elements of browsers, such as parsers and interpreters, the event loop, and rendering, with aspects of cognition, like language processing, attention, and vision.
