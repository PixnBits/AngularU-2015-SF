Vaadin Components for AngularJS
===============================

Joonas Lehtinen

[github.com/vaadin](https://github.com/vaadin)

* who's heard of Vaadin :)
* something you can use today
* what does vaadin have to do with Angular
* 1 min intro:
    * framework for building rich webapps in Java
    * been around 14 years
    * enterprise-grade
        * logging
        * charting
        * interactive graphics
        * drag'n'drop
        * tabular data (very common)
            * usually either paginated, or infinite scroll
* vaadin value
    * automated communication
    * statically typed Java
    * components
* Vaadin Component(s)
    * `<v-grid>` is a (the) really good one
        * features
            * sorting
            * frozen columns
            * [[smoth scrolling, but also on a mac]]
            * header levels
            * many rows? Still smoth scrolling
                * size of the DOM isn't dependent on data nodes
            * transactionality
            * can add input widgets
            * detail rows
        * how it works
            * regular `<table>` inside the `<v-grid>`
            * can use `<colgroup>`
* use it with Angular2
    * no vaadin specific code, all angular stuff you've seen before
    * data is array of row objects
        * regular JSON
    * can add custom render functions
    * can add custom sort function
    * selection 
        * select all...1e6? 1e9?
    * [vaadin.github.io/components-examples/grid](http://vaadin.github.io/components-examples/v-grid/)
* building all of this with Web Components
    * ___
    * shadow DOM
        * a bit of an overpromise right now
        * Chrome has support, but not so much with others
        * polyfills like ShadyDom, but not really hidden
    * html imports
        * `<link type="import" ...>`
    * templates
* Polymer
    * polyfills --> best practices --> elements
    * example `<polymer-element>`
* `<v-grid>` development:
    * 2 years
    * 3-5 people
    * 37k LoC
* Escalator
    * only build the elements visible & recycle
        * translate
    * GPU acceleration via transforms
    * plays nice with screen readers
* scrolling
* Apache 2.0 license
* extend, rather than replace, material components
    * there are about 100 compnents in Vaadin framework
    * want to add DateField
* Valo
    * tried to mimc Apple iOS6 theme
        * apple updated a week later
        * android apps looked like iOS
    * Valo Sass styles: theme variations
    * want to bring this over to web components as well
    * polyfill CSS4 instead of using Sass
    * [demo.vaadin.com](http://demo.vaadin.com)
* Vaadin Charts
    * commercial (everything before is freely available)
        * enterprise oriented
    * deisred to implement via web components

Questions
---------

* draggin rows around
    * columns? [[yes for support?]]
    * not yet for rows
* Google building two versions of web components?
    * concern with polymer: server rendering?
* when is the charts available?
    * v1-alpha vailable now
    * right after summer for beta
        * feature complete
