Componentize your app with Polymer Elements
===========================================

Rob Dodson

[event](https://angularu.com/ng/workshop/2015sf/componentize-your-app-with-polymer-elements)
[video]()

* Jam
    * communist scientists gave people coupons
        * 1st group: display w/6 jars of jam
            * 30% bought
        * 2nd group: ostentatous display
            * 3% bought
    * 10x difference
    * Front-End choice paralysis
    * comparison of FE queries
    * "components"
        * cant use react comp. in angular in ember etc
        * let's work together
* Polymer
    * lib for building web components
    * **Polymer is not a framework.**
* app block diagram
    * Web Components between Web Platform and Existing Frameworks
* Polymer started as a project
    * polyfills --> best practices --> elements
    * findings
        * +
            * data binding is sweet
            * reuse other components
            * easy to get started
        * -
            * cross-browser wierdness
            * styling
    * benchmark of 0.5 experiment
        * Macbook Pro and iPhone
    * 0.8 benchmark
        * 5x faster iPhone 6, 8x faster Firefox Macbook Pro
        * smaller
    * 1.0 ready for production
* demo of building something
    * `<link rel="import" href="...">`
        * inside quick-alert.html
    * `<script> Polymer({ is: 'quick-alert' });</script>`
    * have our own custom tag!
    * `<dom-module id="quick-alert"><template>...local DOM here...</template></dom-module>`
        * local dom: the dom an element is in charge of creating and managing
            * alias for shadow dom, shady dom
    * can add a `<style>` into `<dom-module>`
        * doesn't leak out
    * the light dom: the world outside the element
    * `<quick-alert>Success!</quick-alert>`
* Properties & Data Binding
    * the properties object
        * ` Polymer({ ... properties: { (see below) } ... });`
            * `first: String`
            * `age: { type: Number, value: 12, observer: '_ageChanged', notify: true }`
            * `fullname: { type: String, computefullname: ___ }`
* angular bindings work fine
* styling & theming
    * custom properties are variables, like Sass/Less
        * `background: var(--quick-alert-background);`
        * `<style is="custom-style"> quick-alert { --quick-alert-background: orange; }</style>`
    * mixins
        * `@apply(--quick-alert-theme);`
* Elements
    * "There's an element for that!"
    * elements sets
        * core
        * paper (material implementation)
        * google web components
            * has over 250 APIs
        * platinum
            * push-notifications
            * offline caching
        * gold
            * e-commerce
            * 80% mobile traffic
            * autocomplete: users finish 30% faster
    * [elements.polymer-projects.org](http://elements.polymer-projects.org)
* polymer starter kit
    * how to knit together into an app
    * opinionated setup
    * templates/layouts
        * responsive breakpoints built-in
    * app-wide theming
    * mobile web defaults
        * meta theme color
        * web app install banner
    * good icon defaults
    * offline first
        * if your app doesn't work w/o connectivity, it's not really a mobile app
        * adding support for Service Worker
            * very low level
            * `<platinum-sw><platinum-sw-cach ...></></>`
            * can also use a js file
    * `<platinum-push-messaging>`
* Production-izing Apps
    * have a gulp file included
        * testing
        * building
        * minimizing
* how to combine with Angular 2
    * Preface: I'm not an Angular dev
    * zone.js #138
    * polymer starter kit
    * angular getting starter guide
    * remove some code (empty body)
        * move it to component
    * update routes and others
* creating components
    * careful, both angular and polymer are trying to keep track of shadow DOM
    * telling polymer to use shadow dom instead of shady works on Chrome, still broken on Firefox
    * bandaids:
        * NativeShadowDomStrategy?
        * Shady DOM Adapter?
    * fix:
        * ship shadow dom
* listening for events
    * hyphen-case event names converted to camelCase
        * messes with Polymer?
* [bit.ly/polycasts](http://bit.ly/polycasts)
* Polymer summit in Amsterdam in August
* [polymer-project.org](http://polymer-project.org)

Questions
---------

* why do you think other browser vendors have been slow implementing Web Components
    * bit features, hard to implement
    * we're the one driving it
        * wanted to ship fast
        * opposite of typical web standard approach
    * there's starting to be buy-in from the other browsers
    * polymer gives good proof points
        * devs want it
* 508 compatability, keyboard only, non-sighted users?
    * a11y
    * 0.5 terrible
    * looks like a generic div to a browser
    * have to be very thoughtful
    * lots of fixes went in right before Google IO
    * it's a really big deal for us
        * P0 priority
* angular & polymer: encap angular app in polymer?
    * `<angular>?`
    * sounds neat, thought about it
* polymer caching is neat, POSTs back to the server?
    * concern of the IO website
        * ex: analytics
    * there's a project
        * don't know if it's open source yet
        * replays the events
* seems counter-intuitive for, say, offline caching to be represented as dom?
    * [[seems like xml config file, like pom.xml]]
    * there is precedent for non-visual living in the dom
        * <style>
        * <script>
    * I get that some people are opposed to it
* what do you see as the ideal relationship between angular & polymer
    * remember the block diagram
    * other frameworks are doing the same thing
    * reuse
        * example: datepicker
* what is the testing situation of polymer, DI?
    * can't really run headless
        * Phantom is an old version of Safari
    * can try in Saucelabs
    * I use "web component tester"
* how to avoid many GET requests from imports
    * vulcanize 
        * concatenates all elements into a single file
        * working to support lazy-loaded
    * imports are only requested once
    * we really want HTTP/2 server push to replace concatenating
* with Angular I'm used to the code behind an element, what's the equivalent in polymer
    * native dom API calls
        * register element
        * create shadow dom  
        * etc
    * 3 levels
        * std : 99%
        * mini
        * micro
    * the team is pretty dogmatic against requiring tools to use/build polymer
