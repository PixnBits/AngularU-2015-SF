Angular: Today, Tomorrow and Beyond
===================================

with Dan Wahlin and John Papa

[slides](http://tinyurl.com/AngularTodayTomorrow)

* Today
    * Angular Versions
        * 1.x and 2.x
        * alpha 27 today
    * Choosing a Direction
        * ES ver, TS
            * ES5 w/Angular1.x
                * low risk, etc (see slide?)
        * Team Skillset
        * Code Consistency
            * playing with new code (versions) is playing with fire
        * Coding Guidlines
            * [jpapa.me/ngstyles](http://jpapa.me/ngstyles)
        * Maintenance
            * ex: coder A goes on vacation, coder B has to fix a bug, diff code style
    * Tooling
        * Visual Studio Code
            * built-in node debugging
        * Brackets?
* Tomorrow
    * Languages and Transpilers
        * know about
            * modules
            * annotations
            * classes
        * use ES6/TS in new projects
            * Angular 2 is a moving target
            * ES6 & TS work today (not moving)
                * fight 1 battle at a time
                * learn ES6 or TS first, then Angular2
        * venn of ES5, 6, & TS
        * Demo
            * Babel
                * class Person
                    * constructor
            * TypeScript
                * tsc compiler ("ATM machine" :)
                * introduction course
                * typing helps save you from/when running with scissors
                    * example: broken Promise ;)
* Beyond
    * module loading
        * SystemJS
* Usage w/Angular 2
    * modules
        * what to import?
            * practice
            * ...expertise...
    * data binding
        * 1-way
            * `[name]="phrase"`
                * or `bind-name="phrase"` if you prefer
            * binding directly to dom properties
                * eliminates ~12 directives from v1
        * 2-way
            * `[(name)]="phrase"`
                * or `bindon-name="phrase"`
            * aside: `ng-model` back in
    * handling events
        * `(click)="phrase"`
            * or `on-click="phrase"`
        * no more ng-* (ex: ng-click)
    * directives
        * `*ng-for="#a of b"`
            * generates a template (ES6?)
    * components
        * reuse, consistency
        * annotations (`selector`)
        * classes replace most of the Angular 1.x kinds madness
* demo
    * as many features as possible in one page
        * custom pipes
        * ___
        * router
    * components
        * like LEGO blocks
        * instead of chunks of views
