Migrating to Angular2
=====================

David East

* using Angular v1.4
    * use `Controller as controllerName` syntax
    * using john papa's angular style
    * lots of controllers
        * can cut down by using components
        * instead controller will get data and send it to a directive that knows what to do with it
            * [[v1.x controllers are glue, this is the right way to do this anyway in v1, right?]]
            * `controllerAs` and `controller` options (TODO: link to Angular 1.x docs)
            * controller is now only fetching data (model)
    * new boxes, how to know when added
        * could use `.observe` but that's not in Angular 2
            * [[and can be expensive]]
        * use observables
            * like Promise, but a "stream" of data instead of 1 time result
            * `.subscribe()` with `Rx.ReplaySubject` (??)
* to Angular 2
    * no more stand-alone controllers
    * `angular.Component(...).View(...).Class(...)`
        * annotations 'Component' and 'View' for 'Class'
    * scopes are replaced by the Components
        * always know where we are
    * view: "let's copy and paster our Angular 1 code"
    * using `*ng-for`
        * `*` not explained
        * `#` signifies local variable
            * [[as opposed to a component's class member?]]
    * copy & paste some Angular 1 js code
        * [[code reuse]]
    * angular 1 name collisions fixed in 2 via 'directive' list
