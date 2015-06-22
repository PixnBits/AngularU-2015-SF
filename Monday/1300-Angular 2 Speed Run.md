Angular 2 Speed Run
===================

[code](https://github.com/johnlindquist/speed-run)

Demo, best to view video but...

* goals
    * add a game to a cart
* getting started
    * how did you get angular2?
        * jspm (github, npm)
            * sister proj to SystemJS
* `System.import` akin to ES6 `import`
* ES6 Array methods require shims
* `GameStore` component
    * [[selector looks like a CSS selector]]
* and bootstrap
    * `bootstrap()` returns a Promise
* don't worry about fat arrows here, going for the big picture :)
* created `GameList` component
    * template with `<game-list></game-list>`
        * doesn't work
        * must list out directives used by the component (here, in `GameStore`)
* DI
    * here `httpInjectables` into `GameStore`
    * `GameList` has access to the same dependency via its parent `GameStore`
    * `.subscribe` for changes (TODO: research further for specifics)
* looping
    * `*ng-for="#game of games"`
    * blank screen of death! ;)
    * again, add list of used directives
* attributes
    * add list to component
    * pass data throughd
* `CartService`
* routing
* if a directive is missing (from that list) you won't get an error, you'll just get a blank screen
* "http is an observable"
