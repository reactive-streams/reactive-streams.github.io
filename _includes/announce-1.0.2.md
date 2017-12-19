Reactive Streams 1.0.2 is here!
===============================

We—the Reactive Streams Special Interest Group—are happy to announce the immediate availability of `Reactive Streams version 1.0.2`.

When we released 1.0.1, we promised that after JDK9 had shipped, we'd release a compatibility/conversion library to seamlessly convert between the `java.util.concurrent.Flow` and the `org.reactivestreams` namespaces.

Not only have we done that in this release—we have also shipped a TCK for implementations of the `java.util.concurrent.Flow` interfaces, so that they now can be verified without having to manually adapt/convert to the `org.reactivestreams` interfaces.

As usual, `1.0.2` is binary, and semantically, compatible with the previous 1.0.x releases of Reactive Streams.

The artifacts, documentation and specifications are released under [Creative Commons Zero](http://creativecommons.org/publicdomain/zero/1.0) into the Public Domain.

Documentation
-------------

* [Specification](https://github.com/reactive-streams/reactive-streams-jvm/tree/v1.0.2#specification)
* [Java API Documentation](http://www.reactive-streams.org/reactive-streams-1.0.2-javadoc)
* [Flow Adapters Java API Documentation](http://www.reactive-streams.org/reactive-streams-flow-adapters-1.0.2-javadoc)
* [TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.2/tck/README.md)
* [Flow TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.2/tck-flow/README.md)

Artifacts
---------

* *the Reactive Streams interfaces*
  * `org.reactivestreams:reactive-streams:1.0.2`

* *the Reactive Streams Flow adapters*
  * `org.reactivestreams:reactive-streams-flow-adapters:1.0.2`

* *the Reactive Streams TCK*
  * `org.reactivestreams:reactive-streams-tck:1.0.2`

* *the Reactive Streams Flow TCK*
  * `org.reactivestreams:reactive-streams-tck-flow:1.0.2`

* *Example implementations—documented & verified—to draw inspiration from*
  * `org.reactivestreams:reactive-streams-examples:1.0.2`
   
Credits
-------

We'd like to thank everyone involved, all contributors and everyone who has given feedback during the development of this project.

## Highlights:

- Specification
  + Glossary term added for `Thread-safe`
  + No breaking/semantical changes
  + Rule [clarifications](#specification-clarifications-102-rc1)
- Interfaces
  + No changes
- Technology Compatibility Kit (TCK)
  + Improved [coverage](#tck-alterations-102-rc1)
    * Supports Publishers/Processors which do [coordinated emission](http://www.reactive-streams.org/reactive-streams-tck-1.0.2-javadoc/org/reactivestreams/tck/PublisherVerification.html#doesCoordinatedEmission--).
  + Improved JavaDoc
- Examples
  + New example [RangePublisher](http://www.reactive-streams.org/reactive-streams-examples-1.0.2-javadoc/org/reactivestreams/example/unicast/RangePublisher.html)
- Artifacts
  + NEW! [Flow adapters](#flow-adapters)
  + NEW! [Flow TCK](#flow-tck)
  + Java 9 [Automatic-Module-Name](#automatic-module-name) added for all artifacts

## Specification clarifications 1.0.2

## Subscriber Rule 2

**1.0.1:** The intent of this rule is that a Subscriber should not obstruct the progress of the Publisher from an execution point-of-view. In other words, the Subscriber should not starve the Publisher from CPU cycles.

**1.0.2:** The intent of this rule is that a Subscriber should not obstruct the progress of the Publisher from an execution point-of-view. In other words, the Subscriber should not starve the Publisher from receiving CPU cycles.

## Subscriber Rule 8

**1.0.1:** The intent of this rule is to highlight that there may be a delay between calling `cancel` the Publisher seeing that.

**1.0.2** The intent of this rule is to highlight that there may be a delay between calling `cancel` and the Publisher observing that cancellation.

## Flow adapters

An adapter library has been created to convert `org.reactivestreams` to `java.util.concurrent.Flow` and vice versa. Read more about it [here](http://www.reactive-streams.org/reactive-streams-flow-adapters-1.0.2-javadoc).

~~~xml
<dependency>
   <groupId>org.reactivestreams</groupId>
   <artifactId>reactive-streams-flow-adapters</artifactId>
  <version>1.0.2</version>
</dependency>
~~~

## Flow TCK

A TCK artifact has been created to allow for direct TCK verification of `java.util.concurrent.Flow` implementations, and you can read more about it [here](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.2/tck-flow/README.md).

~~~xml
<dependency>
   <groupId>org.reactivestreams</groupId>
   <artifactId>reactive-streams-tck-flow</artifactId>
  <version>1.0.2</version>
</dependency>
~~~

## Automatic Module Name

  * `org.reactivestreams:reactive-streams` => `org.reactivestreams`
  * `org.reactivestreams:reactive-streams-examples` => `org.reactivestreams.examples`
  * `org.reactivestreams:reactive-streams-tck` => `org.reactivestreams.tck`
  * `org.reactivestreams:reactive-streams-flow-adapters` => `org.reactivestreams.flowadapters`
  * `org.reactivestreams:reactive-streams-tck-flow` => `org.reactivestreams.tckflow`

## TCK alterations 1.0.2

- Added support for Publisher verification of Publishers who do coordinated emission, i.e. where elements only are emitted after all current Subscribers have signalled demand. ([#284](https://github.com/reactive-streams/reactive-streams-jvm/issues/284))
- The `SubscriberWhiteboxVerification` has been given more user friendly error messages in the case where the user forgets to call `registerOnSubscribe`. ([#416](https://github.com/reactive-streams/reactive-streams-jvm/pull/416))

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
  + Anthony Vanelverdinghe [(@anthonyvdotbe)](https://github.com/anthonyvdotbe)
  + Kazuhiro Sera [(@seratch)](https://github.com/seratch)
  + Dávid Karnok [(@akarnokd)](https://github.com/akarnokd)
  + Evgeniy Getman [(@egetman)](https://github.com/egetman)
  + Ángel Sanz [(@angelsanz)](https://github.com/angelsanz)
  + (new) shenghaiyang [(@shenghaiyang)](https://github.com/shenghaiyang)
  + (new) Kyle Thomson [(@kiiadi)](https://github.com/kiiadi)

*Warm regards,
the Reactive Streams Special Interest Group*
