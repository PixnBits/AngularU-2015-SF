Working with Broken APIs Delivered Late
=======================================

Yuri Takheyev

[slides](http://yto.io/xngu)

* split of FE/BE
* ideal:
    * FE builds client, BE builds API
    * API delivered before FE starts
    * once delivered, doesn't change
    * [[unicorns]]
* What's a good API?
    * don't assume BE devs want to send you models
* who will test the API?
    * to some point the BE
    * but real usage is tested by the FE
    * tools:
        * postman
        * supertest
    * "It's working now" --> redesigned as you find bugs
    * "in a few days" --> /s/days/weeks/ or months
    * "working on it" --> FE might be done first
* HackStack
    * set of best practices (guidlines)
    * wasn't code or a library, but due to demand
    * now it is: [HackStack.js](https://github.com/rangle/hackstack)
        * `bower install angular-hackstack`
    * practices:
        * Document the API
        * Use TDD
            * should be first go-to solution
        * mock server too expensive [[??]]
        * client-side mocking
* the last thing you want to do is mix mocking code with your buisiness logic
* see the [README](https://github.com/rangle/hackstack/blob/master/README.md)
* demo
* setup an easy toggle between mock and real data

Note
----
There was an issue in the screens where the titles of the slides (and possibly other info) was not showing up. The culprit was likely a loose/strained VGA cable. The mentioned titles were in only a single color (red) on a dark background. (VGA has only [a single pin for red data](http://pinouts.ru/Video/Vga15_pinout.shtml))

Another edge-case presenters might consider contingency plans for.
