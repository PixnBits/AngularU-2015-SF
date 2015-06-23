Angular 2 Server Rendering
==========================

Jeff Whelpley, Patrick Stapleton

* been working with Tobias to get server rendering working
* two reactions
    * super psyched
    * really upset
* neat pages, but require JS on FE
    * those w/o JS are small
    * [[but still present]]
* initial page load
    * server response --> painting
    * 3-7 seconds
    * 57% will abandon a page taking >3s to load
* people are used to native apps
* 3 potential approaches
    * compress the time
        * physics
            * latency (ex: CA SF to Boston)
    * break into smaller pieces
        * request/serve only what's needed
        * can get to work in a prototype
        * hard for a framework
    * server rendering
        * include a fully-rendered view
            * viewable to user
        * client takes over
* many others have this feature
    * Ember
    * React
* Angular 2 will as well
* Angular 1 tightly coupled to the DOM
    * application layer
        * creates view tree
        * passed on to the Rendering Layer
    * Rendering Layer
        * includes DomRenderer in browser
        * JsonRenderer for server (`.toString()`)
* how will this be used by devs?
    * write app the same
        * **except**: don't touch the DOM (directly)
            * or `window`
        * use angular abstraction
    * install Angular server plugin
* user events when client view hasn't taken over yet?
    * "preboot"
    * small bit of JS recording events
    * plays the events back when client view takes over
* trip through web application history
    * RoR
        * page refreshes
        * you can do the same and get the same result
        * fast initial view, slow updates
    * nowadays
        * blank screen
        * pushes all app logic to the client
        * slow initial view, really fast updates
        * now we go "add a loading screen"
            * designer's fault, not ours ;)
        * some fake the application
            * (lose user input)
                * [[that's a terrible, terrible thing]]
    * with server-rendering
        * looks instantly available
        * new problem: action goes to server to load?
* When?
    * @gdi2290 tweet
* special thanks to Tobias and the core team
