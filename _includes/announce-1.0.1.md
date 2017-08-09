Reactive Streams 1.0.1 is here!
===============================

After more than two years since 1.0.0, we—the Reactive Streams Special Interest Group—are proud to announce the immediate availability of `Reactive Streams version 1.0.1`.

Since 1.0.0 was released `Reactive Streams` has managed to achieve most—if not all—it set out to achieve. There are now numerous implementations, and it is scheduled to be included in [JDK9](http://download.java.net/java/jdk9/docs/api/java/util/concurrent/Flow.html).

Perhaps most importantly, there are no semantical incompatibilities included in this release.

When JDK9 ships, `Reactive Streams` will publish a compatibility/conversion library to seamlessly convert between the `java.util.concurrent.Flow` and the `org.reactivestreams` namespaces.

The artifacts, documentation and specifications are released under [Creative Commons Zero](http://creativecommons.org/publicdomain/zero/1.0) into the Public Domain.

Documentation
-------------

* [Specification](https://github.com/reactive-streams/reactive-streams-jvm/tree/v1.0.1#specification)
* [Java API Documentation](http://www.reactive-streams.org/reactive-streams-1.0.1-javadoc)
* [TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.1/tck/README.md)

Artifacts
---------

* *the Reactive Streams interfaces*
  * `org.reactivestreams:reactive-streams:1.0.1`

* *the Reactive Streams TCK*
  * `org.reactivestreams:reactive-streams-tck:1.0.1`

* *Example implementations—documented & verified—to draw inspiration from*
  * `org.reactivestreams:reactive-streams-examples:1.0.1`
   
Credits
-------

We'd like to thank everyone involved, all contributors and everyone who has given feedback during the development of this project.

## Highlights:

- Specification
  + A new [Glossary](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.1/README.md#glossary) section
  + Description of the intent behind every single rule
  + No breaking semantical changes
  + Multiple rule [clarifications](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.1/RELEASE-NOTES.md#specification-clarifications)
- Interfaces
  + No changes
  + Improved JavaDoc
- Technology Compatibility Kit (TCK)
  + Improved coverage
  + Improved JavaDoc
  + Multiple test [alterations](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.1/RELEASE-NOTES.md#tck-alterations)

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
  + (new) Brian Topping [(@briantopping)](https://github.com/briantopping)
  + (new) Rossen Stoyanchev [(@rstoyanchev)](https://github.com/rstoyanchev)
  + (new) Björn Hamels [(@BjornHamels)](https://github.com/BjornHamels)
  + (new) Jake Wharton [(@JakeWharton)](https://github.com/JakeWharton)
  + (new) Anthony Vanelverdinghe[(@anthonyvdotbe)](https://github.com/anthonyvdotbe)
  + (new) Kazuhiro Sera [(@seratch)](https://github.com/seratch)
  + (new) Dávid Karnok [(@akarnokd)](https://github.com/akarnokd)
  + (new) Evgeniy Getman [(@egetman)](https://github.com/egetman)
  + (new) Ángel Sanz [(@angelsanz)](https://github.com/angelsanz)

*Warm regards,
the Reactive Streams Special Interest Group*
