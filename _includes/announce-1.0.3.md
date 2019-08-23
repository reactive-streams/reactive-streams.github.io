Reactive Streams 1.0.3 is here!
===============================

We—the Reactive Streams Special Interest Group—are happy to announce the immediate availability of `Reactive Streams version 1.0.3`.

When we released `1.0.2`, we shipped a compatibility/conversion library to seamlessly convert between the `java.util.concurrent.Flow` and the `org.reactivestreams` namespaces—in `1.0.3` these adapters are instead included in the main `1.0.3` jar.

In `1.0.3` we have improved the TCK, clarified different aspects of the specification, and proved that the Reactive Streams specification is robust and is successfully used by many various implementations.

As usual, `1.0.3` is binary, and semantically, compatible with the previous 1.0.x releases of Reactive Streams.

The artifacts, documentation and specifications are released under [Creative Commons Zero](http://creativecommons.org/publicdomain/zero/1.0) into the Public Domain.

Documentation
-------------

* [Specification](https://github.com/reactive-streams/reactive-streams-jvm/tree/v1.0.3#specification)
* [Java API Documentation](http://www.reactive-streams.org/reactive-streams-1.0.3-javadoc)
* [TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.3/tck/README.md)
* [Flow TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.3/tck-flow/README.md)

Artifacts
---------

* *the Reactive Streams interfaces*
  * `org.reactivestreams:reactive-streams:1.0.3`

* *the Reactive Streams TCK*
  * `org.reactivestreams:reactive-streams-tck:1.0.3`

* *the Reactive Streams Flow TCK*
  * `org.reactivestreams:reactive-streams-tck-flow:1.0.3`

* *Example implementations—documented & verified—to draw inspiration from*
  * `org.reactivestreams:reactive-streams-examples:1.0.3`
   
Credits
-------

We'd like to thank everyone involved, all contributors and everyone who has given feedback during the development of this project.


## Highlights:

- Specification
  + Glossary term "External synchronization" has been [superseded](#Glossary)
  + No breaking/semantical changes
  + Rule [clarifications](#specification-clarifications-103-RC1)
- Interfaces
  + No changes
- Technology Compatibility Kit (TCK)
  + Improved [coverage](#tck-alterations-103-RC1)
  + Improved JavaDoc
- Examples
  + No changes
- Artifacts
  + FlowAdapters artifact removed, FlowAdapters moved into the core jar ([#424](https://github.com/reactive-streams/reactive-streams-jvm/issues/424))

## Specification clarifications 1.0.3

## Glossary term "External synchronization" replaced by "Serial(ly)"

**1.0.2:** Access coordination for thread safety purposes implemented outside of the constructs defined in this specification, using techniques such as, but not limited to, `atomics`, `monitors`, or `locks`.

**1.0.3** In the context of a Signal, non-overlapping. In the context of the JVM, calls to methods on an object are serial if and only if there is a happens-before relationship between those calls (implying also that the calls do not overlap). When the calls are performed asynchronously, coordination to establish the happens-before relationship is to be implemented using techniques such as, but not limited to, atomics, monitors, or locks.

## Publisher Rule 3 (Rule and Intent clarified)

**1.0.2:** `onSubscribe`, `onNext`, `onError` and `onComplete` signaled to a `Subscriber` MUST be signaled in a thread-safe manner—and if performed by multiple threads—use external synchronization.

*The intent of this rule is to make it clear that external synchronization must be employed if the Publisher intends to send signals from multiple/different threads.*

**1.0.3:** `onSubscribe`, `onNext`, `onError` and `onComplete` signaled to a `Subscriber` MUST be signaled serially.

*The intent of this rule is to permit the signalling of signals (including from multiple threads) if and only if a happens-before relation between each of the signals is established.*

## Subscriber Rule 1 (Intent clarified)

**1.0.2:** A `Subscriber` MUST signal demand via `Subscription.request(long n)` to receive `onNext` signals.

*The intent of this rule is to establish that it is the responsibility of the Subscriber to signal when, and how many, elements it is able and willing to receive.*

**1.0.3:** A `Subscriber` MUST signal demand via `Subscription.request(long n)` to receive `onNext` signals.

*The intent of this rule is to establish that it is the responsibility of the Subscriber to decide when and how many elements it is able and willing to receive. To avoid signal reordering caused by reentrant Subscription methods, it is strongly RECOMMENDED for synchronous Subscriber implementations to invoke Subscription methods at the very end of any signal processing. It is RECOMMENDED that Subscribers request the upper limit of what they are able to process, as requesting only one element at a time results in an inherently inefficient "stop-and-wait" protocol.*

## Subscriber Rule 5 (Intent clarified)

**1.0.2:** A `Subscriber` MUST call `Subscription.cancel()` on the given `Subscription` after an `onSubscribe` signal if it already has an active `Subscription`

*The intent of this rule is to prevent that two, or more, separate Publishers from thinking that they can interact with the same Subscriber. Enforcing this rule means that resource leaks are prevented since extra Subscriptions will be cancelled.*

**1.0.3:** A `Subscriber` MUST call `Subscription.cancel()` on the given `Subscription` after an `onSubscribe` signal if it already has an active `Subscription`

*The intent of this rule is to prevent that two, or more, separate Publishers from trying to interact with the same Subscriber. Enforcing this rule means that resource leaks are prevented since extra Subscriptions will be cancelled. Failure to conform to this rule may lead to violations of Publisher rule 1, amongst others. Such violations can lead to hard-to-diagnose bugs.*

## Subscriber Rule 7 (Rule and Intent clarified)

**1.0.2:** A `Subscriber` MUST ensure that all calls on its `Subscription` take place from the same thread or provide for respective external synchronization.

*The intent of this rule is to establish that external synchronization must be added if a Subscriber will be using a Subscription concurrently by two or more threads.*

**1.0.3:** A Subscriber MUST ensure that all calls on its Subscription's request and cancel methods are performed serially.

*The intent of this rule is to permit the calling of the request and cancel methods (including from multiple threads) if and only if a happens-before relation between each of the calls is established.*

## TCK alterations 1.0.3

- `PublisherVerification.optional_spec105_emptyStreamMustTerminateBySignallingOnComplete` fails if the publisher completes synchronously ([#422](https://github.com/reactive-streams/reactive-streams-jvm/issues/422))
- IdentityFlowProcessorVerification throws NPE when `createFailedFlowPublisher` returns null ([#425](https://github.com/reactive-streams/reactive-streams-jvm/issues/425))
- `required_spec208_mustBePreparedToReceiveOnNextSignalsAfterHavingCalledSubscriptionCancel` does not wait for request before invoking onNext ([#277](https://github.com/reactive-streams/reactive-streams-jvm/issues/277))
- Subscriber whitebox verification tests demand ([#280](https://github.com/reactive-streams/reactive-streams-jvm/issues/280))
- Incomplete documentation on stochastic tests in TCK ([#278](https://github.com/reactive-streams/reactive-streams-jvm/issues/278))
- TCK performance ([#446](https://github.com/reactive-streams/reactive-streams-jvm/issues/446))
- TCK: Receptacle#expectError timeout approach ([#451](https://github.com/reactive-streams/reactive-streams-jvm/issues/451))


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
  + (new) James Roper [(@jroper)](https://github.com/jroper)
  + (new) Oleh Dokuka [(@olegdokuka)](https://github.com/olegdokuka)
  + (new) Scott Mitchell [(@Scottmitch)](https://github.com/Scottmitch)

*Warm regards,
the Reactive Streams Special Interest Group*
