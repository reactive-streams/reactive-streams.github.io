Reactive Streams 1.0.4 is here!
===============================

We—the Reactive Streams Special Interest Group—are happy to announce the immediate availability of `Reactive Streams version 1.0.4`.

In `1.0.4` we have re-licensed under MIT No Attribution (SPDX: MIT-0), improved the TCK, clarified different aspects of the specification, and proved that the Reactive Streams specification is robust and is successfully used by many various implementations.

As usual, `1.0.4` is binary, and semantically, compatible with the previous 1.0.x releases of Reactive Streams.

Documentation
-------------

* [Specification](https://github.com/reactive-streams/reactive-streams-jvm/tree/v1.0.4#specification)
* [Java API Documentation](http://www.reactive-streams.org/reactive-streams-1.0.4-javadoc)
* [TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.4/tck/README.md)
* [Flow TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.4/tck-flow/README.md)

Artifacts
---------

* *the Reactive Streams interfaces*
  * `org.reactivestreams:reactive-streams:1.0.4`

* *the Reactive Streams TCK*
  * `org.reactivestreams:reactive-streams-tck:1.0.4`

* *the Reactive Streams Flow TCK*
  * `org.reactivestreams:reactive-streams-tck-flow:1.0.4`

* *Example implementations—documented & verified—to draw inspiration from*
  * `org.reactivestreams:reactive-streams-examples:1.0.4`
   
Credits
-------

We'd like to thank everyone involved, all contributors and everyone who has given feedback during the development of this project.


## Highlights:

- License
  + This project is now (re-)licensed under MIT No Attribution (SPDX: MIT-0)
- Specification
  + No breaking/semantical changes
  + Rule [clarifications](#specification-clarifications-104)
- Interfaces
  + No changes
- Technology Compatibility Kit (TCK)
  + Improved verification of Subscriber rule §2.3
  + Improved JavaDoc
- Examples
  + No changes
- Artifacts
  + No changes

## Specification clarifications 1.0.4
**1.0.3:** The intent of this rule is to permit the calling of the request and cancel methods (including from multiple threads) if and only if a happens-before relation between each of the calls is established.

**1.0.4:** The intent of this rule is to permit the calling of the request and cancel methods (including from multiple threads) if and only if a [serial](#term_serially) relation between each of the calls is established.

## Contributors
  + Roland Kuhn [(@rkuhn)](https://github.com/rkuhn)
  + Ben Christensen [(@benjchristensen)](https://github.com/benjchristensen)
  + Viktor Klang [(@viktorklang)](https://github.com/viktorklang)
  + Stephane Maldini [(@smaldini)](https://github.com/smaldini)
  + Stanislav Savulchik [(@savulchik)](https://github.com/savulchik)
  + Konrad Malawski [(@ktoso)](https://github.com/ktoso)
  + Slim Ouertani [(@ouertani)](https://github.com/ouertani)
  + Martynas Mickevičius [(@2m)](https://github.com/2m)
  + Luke Daley [(@ldaley)](https://github.com/ldaley)
  + Colin Godsey [(@colinrgodsey)](https://github.com/colinrgodsey)
  + David Moten [(@davidmoten)](https://github.com/davidmoten)
  + Brian Topping [(@briantopping)](https://github.com/briantopping)
  + Rossen Stoyanchev [(@rstoyanchev)](https://github.com/rstoyanchev)
  + Björn Hamels [(@BjornHamels)](https://github.com/BjornHamels)
  + Jake Wharton [(@JakeWharton)](https://github.com/JakeWharton)
  + Anthony Vanelverdinghe[(@anthonyvdotbe)](https://github.com/anthonyvdotbe)
  + Kazuhiro Sera [(@seratch)](https://github.com/seratch)
  + Dávid Karnok [(@akarnokd)](https://github.com/akarnokd)
  + Evgeniy Getman [(@egetman)](https://github.com/egetman)
  + Ángel Sanz [(@angelsanz)](https://github.com/angelsanz)
  + shenghaiyang [(@shenghaiyang)](https://github.com/shenghaiyang)
  + Kyle Thomson [(@kiiadi)](https://github.com/kiiadi)
  + Tomislav Hofman [(@tomislavhofman)](https://github.com/tomislavhofman)
  + Sean Sullivan [(@sullis)](https://github.com/sullis)

*Warm regards,
the Reactive Streams Special Interest Group*
