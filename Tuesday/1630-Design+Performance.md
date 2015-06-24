Design+Performance
==================

Steve Souders

[slides](http://stevesouders.com/docs/d+p-angularu-20150623.key)

* this is going to be techy at the end
    * fluffy in the beginning
* part I
    * developers and designers often work in silos
        * are we as angular devs on the same page in terms of UX?
        * communication and operations, do they talk?
            * --> devOps
                * now it's a buzzword :(
        * more cooperation between designers & developers
        * how many people have designers sitting *with* the developers?
        * both sides going in with "cannot budge on x"
        * who more than these 2 groups want the exact same thing?
            * an exceptional UX
    * some designs are hard to make fast
    * being fast is important
        * some stats on performance and user behavior
* part II (Metrics)
    * small interdisciplinary teams
        * some may come/gain anchors (don't give up)
    * guiding principles
        * put the targets in
    * protoype early
        * teams should include designers
            * assets
                * imagery
                * color
                * "quick transistion of the CSS"
    * measure performance early
        * not the optimizations ("premature optimizations...")
        * yes, start with the early prototypes
        * performance budgets
            * make the metrics visible to the entire team
                * in-page reminders
                    * etsy: via IP check includes a bar on top of the performance
                * show what's beaconed
                    * in the page
                * bookmarklets
                * makes it easy to dog-food
    * I hope everyone is measuring perf
        * but not with `window.onload()`
            * Web 1.0
            * see post on blog ["Moving beyond window.onload()"](http://www.stevesouders.com/blog/2013/05/13/moving-beyond-window-onload/)
            * examples: 
                * gmail
                    * onload is the loading bar
                    * takes another second for most of the pixels to be painted
                * amazon
                    * all the stuff above the fold rendered in 2s
                    * onload fires ~9s (below the fold stuff)
            * we need better metrics
        * [webpagetest.org](http://webpagetest.org) is great
            * ignore the page load time
            * servers running real instances of browsers
            * OSS
            * 50 locations
                * 2 behind China's firewall
        * speed index
            * pixels painted
    * compare to competitors
        * side by side
* Part III
    * Hero Image design pattern
        * can be a large % of the pixels on the page
        * slow to load?
            * stop blaming light's speed, never the reason
            * asset load graph (waterfall chart)
                * jawbone:
                    * finishes downloading 540ms before being shown
                    * took 647ms for the request to even start
                * homeaway
                    * 2079ms before rendering
            * JavaScript & CSS mess with rendering
                * JS execution blocks rendering
                * [[as does something specific about CSS, typing sorry]]
                    * [[fonts?]]
            * (most) browsers look-ahead and load all JS & CSS before anything else
                * so they'll be loaded (blocking) even if they're towards the bottom
                * can now load JS in `async` mode
                * load CSS async [[how?]]
    * custom metrics
        * define _most imortant_ elements
        * measure user User Timing
        * track with RUM _and_ synthetic
        * examples
            * Twitter: time to first tweet
            * me: images?
                * how to measure
                    * performance.getEntriesByName(...)[0].asdf = download time, not rendered time
                    * `<img onload>`?
                    * `offsetHeight` polling fails, element present before rendered
                    * inline script right after `<img>`
                        * `<script> performance.mark('image'); </script>`
                        * but the image takes 7s to load
                    * final: max(image onload, inline script)
        * capture the UX more precisely
* Take-Aways
    * id what matters most
    * focus on UX performance
    * _____ TODO: find in the slides
* Lara Hogan's book
* Velocity Conference

Questions
---------

* base64-esqe optimizations?
    * use image tags
    * scripts block the html parser
    * the look-ahead finds `<img src="..."">`
    * but not `background-image: url(...);`
    * load the image first, before any JS (or CSS)
    * small imgs as base64 are okay
    * hero images are big
        * base64 doesn't cache
* create a static page?
    * I have a whole talk on how to mess with the user's perception of the page
    * you're not going to want to swap out the page the user is looking at
        * flash/switch
    * [[I imagine the framework picking up, not replacing, the server rendering should be good though]]
* Elliot Gregorik: Critical Path, Time the Glass
* webpage test, URL inside a firewall?
    * ~2000 companies have private instances inside their firewalls
    * webpage test doesn't store history
    * speedtest does
* custom fonts, icon format?
    * Mark & I rep the two sides of the debate
    * poor internet speed
    * but the custom font was blocking all the text on the page from rendering
    * the most important text is blocked from being rendered
        * there's a way around
    * icon format depends
* async ~~tag~~ attribute, but only IE10
    * use `async` and `defer`
        * `defer` is part of the spec
        * `async` takes precedence
* hero image: bring anything to the site other than slowing the page, any studies?
    * I would guess so, perhaps not
        * might not release them if they did have them
