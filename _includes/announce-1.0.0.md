Reactive Streams 1.0.0 is here!
===============================


It is with great pleasure that we—the *Reactive Streams Special Interest Group*—are announcing the immediate availability of the final form of _Reactive Streams_—after countless hours of prototyping, discussions, debate, evaluations, programming, testing, specifying requirements, documenting, and refining—we are confident that we have found the essential solution to the problem that we set out to solve:

> […] provide a standard for asynchronous stream processing with non-blocking back pressure.“ - [reactive-streams.org](http://www.reactive-streams.org)

The artifacts, documentation and specifications are released under [Creative Commons Zero](http://creativecommons.org/publicdomain/zero/1.0) into the Public Domain.

Documentation
-------------

* [Specification](https://github.com/reactive-streams/reactive-streams-jvm/tree/v1.0.0#specification)
* [Java API Documentation](http://www.reactive-streams.org/reactive-streams-1.0.0-javadoc)
* [TCK README](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.0/tck/README.md)

Artifacts
---------


* *the Reactive Streams interfaces*
  * `org.reactivestreams:reactive-streams:1.0.0`

* *the Reactive Streams TCK*
  * `org.reactivestreams:reactive-streams-tck:1.0.0`

* *Example implementations—documented & verified—to draw inspiration from*
  * `org.reactivestreams:reactive-streams-examples:1.0.0`
  


Implementations
---------------

We are also proud to let _Reactive Streams_ `1.0.0` be announced to the world accompanied with a multitude of compliant implementations verified by the TCK for 1.0.0, listed below in alphabetical order:

* [Akka](http://akka.io/) Streams *(version `1.0-RC2`)*
   * See this [Activator template](http://www.typesafe.com/activator/template/akka-stream-scala) and the [documentation](http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-RC2/index.html).
* [MongoDB](http://mongodb.org) *(version `1.0.0`)*
   * For the documentation see [here](http://mongodb.github.io/mongo-java-driver-reactivestreams).
* [Ratpack](http://www.ratpack.io) *(version `0.9.16`)*
   * See the [“Streams”](http://www.ratpack.io/manual/current/streams.html) chapter of the manual.
* Reactive Rabbit *(version `1.0.0`)*
   * Driver for RabbitMQ/AMQP, see [here](https://github.com/ScalaConsultants/reactive-rabbit).
* [Reactor](http://projectreactor.io/) *(version `2.0.1.RELEASE`)*
   * For the documentation see [here](http://projectreactor.io/docs/reference/streams.html).
* [RxJava](http://reactivex.io/) *(version `1.0.0`)*
   * See [github.com/ReactiveX/RxJavaReactiveStreams](https://github.com/ReactiveX/RxJavaReactiveStreams).
* [Slick](http://slick.typesafe.com/) *(version `3.0.0`)*
   * See the [“Streaming”](http://slick.typesafe.com/doc/3.0.0/dbio.html#streaming) section of the manual.
* [Vert.x 3.0](http://vertx.io) *(version `milestone-5a`)*
   * Vert.x 3.0 is currently in alpha. The Reactive Streams implementation can be found [here](https://github.com/vert-x3/vertx-reactive-streams).
   
Credits
-------

We'd like to thank everyone involved, all [contributors](https://github.com/reactive-streams/reactive-streams-jvm/graphs/contributors), and everyone who has given feedback during the development of this project.

*Warm regards,
the Reactive Streams Special Interest Group*
