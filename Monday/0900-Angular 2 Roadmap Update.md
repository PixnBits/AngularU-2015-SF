Angular 2 Roadmap Update
========================

Brad Green
----------

* v1.x will be supported for the forseeable future
* performance
    * Benchpress
    * examples (see github)

Igor Minov
----------

 * experiments for further perf
    * fast scrolling
    * review of the Event Loop
        * 3 contenders: App, Angular, Browser
    * (more?) use of Web Workers
        * no access to DOM (pfft, not really a restriction: see React)
        * framework split into **2**
            * DOM Renderer
            * Angular proper
* native apps (ionic, onsen UI)
    * Angular Renderer <--> Angular, App
        * HTML5, Android, iOS
    * "NativeScript"
    * working with React Native
        * collaboration
        * what would integration look like?
            * demo ("angular-react", index.ios.ts)
* server-side
    * Faster Startup, SEO, Previews
    * futher details [Tuesday @10:30](Tuesday/1030-____.md)

Brad Green
----------

* AtScript --> TypeScript
* collaboration w/Ember on "decorators" for ES7

Misko Hevery
------------

* [demo](https://github.com/mhevery/angular-u-demo)
* build in ES5, transition to ES6, transpile
* IDE autocompletion, TypeScript
    * Microsoft Visual Code
    * plugin for Sublime
* annotations
* (renamed namespace from `angular` to `ng`?)
* all 3 of the transpilers support "decorators"
* material, also with v1.x
* **1-way data binding**
    * `[]` binding **to** the UI
    * `()` binding **from** the UI
    * `[()]` is...both?
        * "kinda reverse data binding"...wat?

Brad Green
----------

* Milestones
    * plan 3 weeks out on GitHub
    * next
        * finish core
        * API sugaring
        * perf+
        * docs
        * ----
        * migration support
            * automated transition tools
        * animate (like ng-animate in v1.x)
        * material design
        * CLI
        * ----
        * server side
        * native
        * web workers
        * ?

[Slides](https://goo.gl/vu4o5T)

Questions
---------

* Routing
    * own repo, not prod ready (broken)
    * ui-router best current?
        * yes, use some of those ideas
        * will have built-in lazy-loading
* Mobile: build process (Phone Gap, Cordova, etc?)
    * native shell from React-Native itself
* Style Guide
    * John Papa
    * TypeScript
* ES5 support, but Evergreen Browsers only, why?
    * big use case: easy to get started
        * toolchain req increases barrier to entry
        * audience of Angular is very wide
* Project Management: Feature Creep? criteria for adding features
    * ?? (Brad)
    * avoid breaking changes later (Web Worker restrictions) (Igor)
* Flux Architecture: works well w/Angular?
    * dramatic: death of MVC :)
    * yes: have a wide spectrum of choices (Misko)
* Will Angular 2 be easier than 1?
    * (sales pitch)
* Modules, how much to import?
    * always single import of Angular2 (Misko)
    * IDEs: team uses all (Igor)
        * I use WebStorm, not 100% but getting there
        * same for VisualCode, prob others
    * Angular2 Syntax: how to improve tooling (the IDEs) (Misko)
    * bake more in (Brad)
        * if you forget something, we'll tell you
* "Glue" Language, how to "glue" components together?
    * mixture is the same (Misko)
    * in ES6 very short templates can be inline (Green)
        * but more likely these will be separate in more full apps
* "more about the ways you're working", "helping internal teams transition"
    * Google Consultancy :) (Misko)
    * survey of Angular 1 app (Brad)
        * what can be auto-mapped
        * partially mappable
        * some things are easier (`$watch`, `scope` gone)
        * gant chart
        * Green Tea group builds things that don't exist as they find them
            * hopefully cover everything so you don't have to
* binding other apps to Angular instead of native Java/ObjC
    * glad you asked (Brad)
        * ?
* ?
    * new router allows you to mix & match views (Brad)
* attribute directives, how do those sit in Angular2?
    * "component" in ng2, "directive"? in ng1
    * in Web Worker, so no acces to DOM?
        * custom views, works with main thread
* wise to wait for TypeScript 1.5, or use Angular 1.5?
    * can use Angular 1.4 (Igor)
        * is DefinitelyTyped 
* suggestions for a module loader? how modular?
    * ES6 defines the module system (Misko)
        * competing implementations
    * SystemJS? but who knows?
