Directives in Angular: 1 + 2 = WIN
==================================

Joe Eames

* 6th grade to Middle School
    * lost on the first day
    * after a while, the school wasn't that big anymore
        * started making sense
* analogy for directives (&components)
* the buidling blocks of our apps
    * small simple pieces
    * put together for larger apps
* epiphany 1 year in: angular apps are just big bags of directives
    * angular is a directive compiler
    * ex: `ng-app`
* there are 3 effective types of (angular 1) directives (internal names)
    * components
        * criteria
            * represented by an element
            * have a template
        * examples:
            * `<voting-button votin-data="asdf.qwerty"></voting-button>`
        * very commonly written
    * decorators
        * criteria
            * represented by an attribute
            * no template
        * examples:
            * `<div ng-click="handleClick()">`
            * `<video paused="handlePaused()">`
        * not as commonly written as component directives
    * (structural)/template
        * criteria
            * represented by elements in the DOM
            * add/remove elements
        * examples
            * `<div ng-repeat="comment in comments">...</div>`
        * very rarely written
* Angular 2 "Directives"
    * components
        * criteria
            * represented by an element
            * have a template
        * examples
            * `@Component(...)@View(...)class...`
    * directives
        * poor naming :(
        * criteria
            * represented by an attribute
            * no template
        * why not call them decorators?
            * ES7
            * Yehudah Katz
                * annotations
        * examples
            * `@Directive({ selector: '[blue]' })export class Blue {...}`
    * where are the third type from angular 1?
        * like `*ng-for`
        * very unusually written
            * not included
* how to structure app?
    * angular 1
        * controllers with directives?
        * nested directives?
    * Angular 2: now it's easy
        * [[no controllers?]]
* side-by-side code example
    * template
        * very similar
        * ng-show becomes a binding
    * [[js]] code
        * restict --> selector
* Angular 2 is like Middle School
    * laid out very logically
    * same concepts in both
        * angular 2 is a neater package
