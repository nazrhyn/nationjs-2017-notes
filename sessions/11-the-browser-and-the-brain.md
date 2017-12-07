# The Browser and the Brain
## Understanding
### Programming Languages
* Define vocabulary with patterns and syntax with grammars
* Parsers read code and interpret with lexical and syntactic analysis by a lexer and a parser, respectively
* HTML is not context free and so it can't be parsed by a regular parser
* CSS _is_ a context-free language
* Both parsers generate a tree representing what they parsed

### Natural Languages
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

## Visualizing
How does the human visual system paint a picture of the world; how does the browser render pictures to the screen?

### Humans
1. Visible light goes into the eye via cornea and lens
1. Retina turns light into neural signals using rods and cones
1. Neural signals are sent to the brain
1. They are combined in the optic chiasm
1. Most signals are sent to the lateral geniculate nuclei
1. Signals end up at the primary visual cortex
1. Signals get sent to higher visual processing centers to perceive what is seen

### Browsers
1. Evaluate langage to get the trees
1. DOM and CSSOM trees combined to form the render tree
1. Browser traverses render tree, calculating location and size of all elements
1. Browser traverses render tree, creating layers of bitmaps
1. Bitmaps sent to the GPU for compositing
1. Do it over and over, optimally 60 FPS

## Task Management
Can the human mind and the browser multitask?

### Humans
* attention ... as a filter, as a spotlight, as control (blocking unwanted distractions and automated processes)
* attention ... as threads?
* Humans are bad at multitasking
  * inattentional blindness
  * dichotic listening task
  * shadowing

### Browsers
* JavaScript doesn't multitask; it's single threaded
* Javascript can call out to APIs to _effectively_ multitask
