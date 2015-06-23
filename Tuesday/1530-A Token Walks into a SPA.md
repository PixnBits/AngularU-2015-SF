A Token Walks into a SPA…
=========================

Martin Gontovnikas

* the title I wanted: <wall of text>
* follow me [@mgonto](https://twitter.com/mgonto) and increase my ego
* [auth0](https://auth0.com/)
* t-shirt throw
* more flashy lights
* browser-server
    * login: POST
        * creates an object in the session
            * includes an ID
            * sent to browser as cookie
    * buy a widget
        * sends user id to server
        * same as in session?
        * take his money
        * send response
            * and widget
    * used to work really well
* cookies don't work well with [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS)
* cookies require stateful servers
    * HTTP is a state-less protocol
* stateless: same response to the same request always
* statefull: response depends on state, not just request
* sharing state
    * store like redis, mongo
    * sticky sessions
    * "fixing" a problem that shouldn't be there
* APIs should be stateless
* cookies don't flow (server-to-server)
* Proposition: Token-based Authentication
    * [JSON web token](http://jwt.io/)
        * [IETF spec](http://tools.ietf.org/html/rfc7519) as of ~2months ago
* browser-server with token-based
    * login: POST
        * creates a JSON web token
        * sends token as response
        * server doesn't save **anything**
    * buy a widget
        * sends token
        * server checks the token with it's secret
        * take money, etc
    * any of the servers can check
        * only need the secret
    * [[how to prevent attackers from getting the token? where is it stored? (XSS)]]
* unholy experiment demo
    * TS
    * bind to (submit) event, pass in data
    * using [fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API#Browser_compatibility)
    * [[storing the key in localstorage]]
    * able to authenticate
    * who thinks it (auth request) will work?
        * good: it won't, we need to pass the token :)
    * `Authentication: 'Bearer ' + key`
    * logout? delete key in localstorage
        * [[need to notify the server?]]
    * logged out means no state [[??]]
        * user has a token or not
    * create a token on our own, server doens't use it: secret

Questions
---------

* security hijacking?
    * similar to cookies over HTTP
    * use HTTPS
    * localstorage vs cookies
        * cookies w/ http-only can't ready with JS
        * localstorage is readable but not subject to (direct) XSS
* supporting browsers w/o localstorage
    * use cookies
    * but it won't be the same
    * could use angular-storage module/project
* where did the secret come into play on the client
    * session creation is in the server
        * uses jwt
    * the secret can be anything
    * changing from HMAK to RSA 256
        * can use two secrets
            * public
            * private
        * can validate with the public key
            * reduces where the secrete key needs to be
* expiration?
    * sliding session
        * exchange an about-to-expire token with a new token
* private data in the token
    * put very little data into the token
    * but you can add an encrypted portion
        * it's part of the spec
* faking having a token, how much are you checking?
    * even if people can see the HTML, the data is hidden
        * through the authenticated URLs/endpoints
    * [[your app is public, but the user data is not]]
* Single Sign On vs Single Sign Up
    * use Auth0 as the single authN for many sites
    * auth0 manages the "session"
    * that's why people pay us money :)
