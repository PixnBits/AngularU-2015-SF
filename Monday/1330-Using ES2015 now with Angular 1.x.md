Using ES2015 now with Angular 1.x
=================================

* ES6 is final (as of last week)
* ES7 is now under development :)
* build tool support
* features to spped dev time
* adoption
* current (for **now**)
    * i.e.: web assembly
* transpile
    * Babel
        * pronounce at your own risk :)
        * speaker prefers the JS output
    * Traceur
* build tools
    * SystemJS & JSPM
        * universal module loader
        * plugin system
        * JSPM uses SystemJS internally
        * JSPM package manager
            * fetches from github, npm, bower
            * auto-configs...somthing (came back to type)
    * webpack
        * loads & bundles modules
        * larger plugin ecosystem (again, for now :)
        * easy setup
* Classes for Controllers
    * components --> `class`es
    * `class` sugar syntax
    * gotchas
        * add deps to the context
* modules
    * are awesome
    * `import`, `export`
    * CSS file?
        * no var name --> added to DOM automatically
            * [[dependent on module loading system employed?]]
    * gotchas
        * not everything is copacetic
        * no conditional imports
        * must be at the top (run first)
        * no interpolation (for module names)
* Arrow Functions
    * A.K.A. "fat arrow"
    * contextual `this`
    * shortcut for `function() {}`
    * functions created are anonymous
    * single arg doesn't require parenthesis
    * gotchas
        * unexpected side-effects, ex: in controllers and services
            * good example (code) `TODO: add link`
* Object property/method shortcuts
    * can use variable name as key in Object
    * true for named functions as well
    * gotchas
        * transpiler support is shakey
            * may not be spec compliant
            * ex: recursion
* destructuring
    * [[especially helpful with modules]]
    * related to Object property/method shortcuts
    * gotchas
        * **dont use with DI**
            * angular uses regex
        * doesn't work with arrow functions/fat arrow
* decorators
    * `@name`
    * experimental
    * gotchas
        * still a proposal
        * only classes
        * check transpiler support
* `let` & `const`
* (others, fast slides)
* "use ES2015 nows"
    * "before the other thing comes out"