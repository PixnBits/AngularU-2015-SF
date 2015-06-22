Dominating Shadow DOM
=====================

[slides]() REALLY need slides!!

* W3C Web Components
    * HTML Imports
    * HTML Templates
    * CUstom Elements
    * Shadow DOM
* browser support is lacking
    * polyfills [[how much can be polyfilled]]
* built-in examples
    * <audio controls>
    * <input type="date"
* in Chrome dev tools, can enable inspection
    * shadow host
    * shadow root
    * shadow DOM
* working example: [paper-chat](http://pubnub.github.io/paper-chat/)
* don't use single word
    * [[namespace your elements?]]
        * [[angular did before shadow DOM :)]]
* `host.createShadowRoot()`
    * can `.appendChild` to the shadow root
* CSS scoping
    * `:host`
    * `:host-context()`
    * `::content`
    * `::shadow` (deprecated)
    * [`>>>`](http://dev.w3.org/csswg/css-scoping/#deep-combinator)  (deprecated)
* examples
