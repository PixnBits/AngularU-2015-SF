TypeScript and Angular 2.0
==========================

Johnathan Turner
Project Manager of TypeScript as Microsoft

* ES5
    * aka the JS of ~~today~~ yesterday
* ES6
    * the JS of today
    * "we can work with classes"
        * [[nope, `class` syntax yes, but there are still no classical classes]]
* ES7
    * the JS of tomorrow
    * decorators (annotations)
    * async/wait
* Types [[strictly-typed]]
    * benefits of types for tooling
        * compile-time checks
        * refactoring
        * code navigation [[??? doesn't require types]]
* Types horror stories
    * don't turn JS into Java
    * don't turn JS into Haskell
* "because we're in 2015 we can work with a modern type system"
    * [[careful, you're sounding "too smart"]]
    * type inference
        * demos of type inference via [typescriplang.org](http://www.typescriptlang.org/Playground)
    * gradual typing
        * "can turn type checking off by using the `any` type"
            * [[ripe for abuse, antipattern/code smell?]]
    * configurable type checking
* Angular 2's four main principles
    * future ready
        * rewritten using ES6
    * flexible development
        * works with any of ES5, ES6, TS
    * simple & expressive
        * rich templating system
        * works better with tools, like TypeScript
    * dependency injection
* converting a sample app from HTML5/JS --> Angular2/TS
    * `mv <*>.js <*>.ts`
    * `tsc *.ts` gives some errors
        * still generates the js files
            * [[which weren't deleted ;)]]
        * like a dial, can set close to 0
    * create a `tsconfig.json`
        * single file that stores all settings (config)
        * place in root of project
            * [[seems to work similar to `package.json`]]
    * some of the errors already go away
        * able to navigate to declarations
    * now we start adding info
        * casting some dom methods
    * found a spelling error (variable name)
        * [[linters are good at that, types not needed]]
    * no more errors, but dial still low
    * now we refactor to take advantage of ES6 features
        * like classes
            * [[facepalm]]
        * added a `class` declaration
        * renamed a member property
            * changed elsewhere
    * "JX"/pattern matching
        * `function amplify<T extends AudioFile>(file: T, gain:number) {...}`
    * no overhead in the runtime code
        * type info only for dev time
    * upping the dial [[turning some switches on]]
        * `noImplicitAny`
    * use ES6 modules
        * requires turning `--modules` on
        * tsconfig.json: `"module":"amd"`
        * `export` the ES6 way
        * must `import` types/interfaces/etc from other files
        * uses RequireJS
    * Angular2-ize
        * use class syntax for components
            * import angular
                * and tsd file for angular
                    * [["TypeScript Definition"]]
                    * (network is down)
                    * (pulls out cooked cake) TODO: link to spot in video
            * annotations
            * add type info to member properties
            * we don't get type checking in the template itself
                * great next step
    * github repo TODO: get link from slide

Questions
---------

* debugging compiled code
    * TypeScript generates mapfiles
    * use Uglify2
* type of `null` and `undefined`?
    * `any`
* will tsconfig support glob patterns
    * should be in soon-ish
* self hosting tsd repos?
    * its been a while since I saw the server code, but it was _simple_
    * have a look
* doing classes the ES5 way
    * [[ES6 doesn't have classes, only syntactic sugar]]
    * look at the compiler itself
        * written in closure style
    * use interfaces
        * this function has this
    * on-screen demo started
        * trick and a massage
        * "see me after"
* what do you think about the code looking uglier after adding the types in
    * anyone with Java-ish background will be skeptical about adding all sort of info for little bits of usefulness
    * I don't think there's a good answer
        * it's up to your project
    * Q: "I don't know that it's my choice"/using other libs
        * DefinitelyTyped
        * Q: "right, so it's like drugs" and "it looks like Java again"
            * it's up to you & your project
* ___? (typing, sorry)
    * the azure portal is written in TypeScript
        * some interviews with those guys [[videos?]]
* come from Java, learning JavaScript way, this looks more familiar to me, what is ___ in creating classes?
    * the type system is optional
    * I start with it looking JavaScript-y
    * then start adding types
* are you looking to roll types into the standard in the future?
    * hopefully, that's a long-term plan
    * working with Google Closure, Facebook Flow
    * Flow is taking a different approach
* why move from Google Closure to TypeScript
    * tooling [[?]]
    * play with it
    * annotation inline instead of in a comment
    * both doing error checking
    * the main diff is in the editing and typing experience
* quick survey
    * already using: 1/4 - 1/3
    * plan to use in the next 6mo: almost whole room
