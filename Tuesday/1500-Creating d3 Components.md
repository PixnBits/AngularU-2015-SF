Creating d3 Components with Angular
===================================

Aysegul Yonet

[slides](http://bit.ly/AngularU-d3)

[[be sure to read [Towards Reusable Charts](http://bost.ocks.org/mike/chart/)]]

* Angular Components
* D3
* together
    * put graphs into components :)
        * bind data through attributes
* works with ng-repeat
* angular 1 syntax
    * scope config for attributes
* enter and exit
    * [[`$watch`, so still angular v1?]]
* use angular data fetching mechanism
* you can ask your BE engineer for the data in the format you want
    * that doesn't happen very often
* use array of objects for data `[{value:10}, ...]`
* if one data point is a different format than what you're expecting, the whole graph won't render
    * used as a case for TypeScript
* learnxinyminutes
* Angular 2
    * component
        * element name,
        * template
        * don't forget to bootstrap
    * can make & use a re-usable data service
    * custom events
* demo 'live' coding :) (video)
* [angularU-example](https://github.com/Yonet/angularU-example)
