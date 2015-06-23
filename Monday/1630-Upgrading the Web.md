Upgrading the Web
=================

Douglas Crockford!!!

* Apology
    * nothing to show you
    * you know the intentions of a programmer is meaningless
* the Web
    * the most amazing thing ever done
    * but it has big problems
        * security
            * historical perspective
                * military computers
                    * physical security
                * then disk drives
                * and time-sharing
                * passwords
                    * you were not getting into another account
                    * pay for your computer time
                * the web didn't start with passwords
                * now we have a password for every site
                    * humans can't remember that many passwords
                        * bad, reused, etc passwords generated
                * RFC 1738: URLs (1994)
                    * included a password
                        * sent in the clear
* How to fix? What's wrong first
* What's wrong with the Web?
    * might be shocking to those used to it
    * insecure
    * complex
    * argue: most insecurity comes from the complexity
    * the web is brilliant at being
        * decentralized
        * simple (compared to the early competitors)
    * standards can't remove defects, only add new defects
    * what is the web made of?
        * HTTP
            * key/value pairs
            * negotiation
                * early browsers couldn't consume everything
            * req/res protocol
                * client was frozen until there was a response
                * opening multiple channels
                    * adds to complexity
        * DNS  
            * not compatible w/the trademark system
            * not trustworthy
        * SSL
            * dev'd at Netscape
                * their approach was complicated
                * about every month has a major disaster
                    * so it's still not finished
            * Certificate Authorities
                * can be verified offline
                    * feature? (what's the point)
                * the bad part: I don't trust them
                    * they accept money, but does that mean anythin?
                    * they've been hacked
                        * refused to acknowledge
                    * browsers trust them all equally
        * HTML
            * good or bad? it depends
            * simple technical documents?
                * bad
                * markdown
            * dynamic applications?
                * terrible
                * decades spent how to get it usable
                * 3 reasons to hate **templating**
                    * source of XSS
                    * layer leakage
                    * it's a trap
            * DOM
                * worst API ever created
                    * perf
                    * reliability
                    * **insecure**
            * CSS
                * Crappy Style Sheets
                * lack of modularity
                * designed for technical documents
            * JavaScript
                * a "hot mess" [[??]]
                * there might be some good parts in ES2015, 2016, etc
                    * but there will be bad parts too
                * I'm getting tired of JavaScript
* Many have tried
    * some cases tech was better
    * solution was not open (most cases)
    * there was no transition
        * how to get devs in?
            * wrong model
* Upgrade the Web
    * keep it up
    * keep it open
* NTSC --> HDTV
    * we watched it even though we couldn't see much
        * 3 channels
    * FCC had to mandate cutting off
    * if many TV sets can't see the SuperBowl there will be an armed rebellion
    * nervousness
    * key to the transition: the **set top box**
        * rx digital, translate to analog for existing TV
        * there was no mode switch
        * just results
* Helper App
    * first browsers didn't know how to do much
    * pass on to another program that did know
    * still there, though unused
* Transition Plan
    * convince 1 browser to integrate this "set top box"
    * convince 1 secure site to require customers to use that browser
    * risk mitigation will compel other "secure" sites
    * competitive pressure to move other browser
    * the world will follow for improvments
    * **Nothing breaks!**
* Strong Cryptogrophy
    * not a garantee of security
    * ECC 251
    * AES 256
    * SHA 3-256
* Zooko's Triangle
    * at most 2
    * Human Meaningful
    * Securely Unique
    * Global: Decentralized
        * no approval or accepting names
        * use ECC521 public keys as unique identifiers
            * can prove it's you via private key
            * only one password, but **never sent over the wire**
* Secure JSON over TCP
    * TCP is one of the best things ever
    * fixes the req/res model
    * more apps than over HTTP
* `web: publickey @ ipaddress / capability`
    * the web didn't use `web` so I will
    * capability uniquely identify user?
* Trust Management/Petnames
    * in the cloud
    * on all your devices but not to everyone else
    * Petnames are unique, you make your own
        * no one else sees yours
* Vat
    * made of iron
    * Virtual _______ (nothing)
    * sandboxes leak
        * cats make things worse
    * JSON data exchanges
    * cooperation under mutual suspicion
* Block Diagram
    * JS Message Server
        * I've got some problems with Node
            * way overspecialized for HTTP
            * I have much higher security requirements
    * Qt ("cute")
        * application framework
            * just the displays/interactivity
* I get to enforce good architecture design
* Not getting rid of the web
    * The Old Web: Promiscuity
    * The New Web: Commitment
        * every time I communicate with them I know its them
        * same for them
* Nothing new here
* Keep doing what you're doing
    * don't stop
    * FUD
        * vaporware
        * not what I'm doing
    * it's too early, I shouldn't even be talking about this
        * offering hope
