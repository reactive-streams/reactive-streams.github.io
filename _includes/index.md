# Reactive Streams

Reactive Streams is an initiative to provide a standard for asynchronous stream processing with non-blocking back pressure on the JVM.

## The Problem

Handling streams of data—especially “live” data whose volume is not predetermined—requires special care in an asynchronous system. The most prominent issue is that resource consumption needs to be carefully controlled such that a fast data source does not overwhelm the stream destination. Asynchrony is needed in order to enable the parallel use of computing resources, on collaborating network hosts or multiple CPU cores within a single machine.

The main goal of Reactive Streams is to govern the exchange of stream data across an asynchronous boundary—think passing elements on to another thread or thread-pool—while ensuring that the receiving side is not forced to buffer arbitrary amounts of data. In other words, back pressure is an integral part of this model in order to allow the queues which mediate between threads to be bounded. The benefits of asynchronous processing would be negated if the communication of back pressure were synchronous (see also the [Reactive Manifesto](http://reactivemanifesto.org/)), therefore care has been taken to mandate fully non-blocking and asynchronous behavior of all aspects of a Reactive Streams implementation.

It is the intention of this specification to allow the creation of many conforming implementations, which by virtue of abiding by the rules will be able to interoperate smoothly, preserving the aforementioned benefits and characteristics across the whole processing graph of a stream application.

## Scope

The scope of Reactive Streams is to find a minimal set of interfaces and methods that will describe the necessary operations and entities to achieve the goal—asynchronous streams of data with non-blocking back pressure.

End-user DSLs to create instances of the API interfaces have purposefully been left out of the scope to encourage and enable different implementations that potentially use different programming languages to stay as true as possible to the idioms of that platform.

We anticipate that acceptance of this Reactive Streams specification and experience with its implementations will together lead to standardized Java platform support in future JDK releases.

## First Draft Specification

Available immediately is a First Draft Specification covering:

* [Semantics](https://github.com/reactive-streams/reactive-streams/blob/v1.0.0.RC3/README.md#specification)—a specification document
* [API](https://github.com/reactive-streams/reactive-streams/tree/v1.0.0.RC3/api/src/main/java/org/reactivestreams)—Java interfaces for implementations ([javadoc](https://reactive-streams.github.io/reactive-streams-1.0.0.RC3-javadoc))
* [TCK](https://github.com/reactive-streams/reactive-streams/tree/v1.0.0.RC3/tck)—a test harness to validate implementations and guide implementor ([javadoc](https://reactive-streams.github.io/reactive-streams-tck-1.0.0.RC3-javadoc))

All of the parts of the Draft Proposal is released under [Creative Commons Zero](http://creativecommons.org/publicdomain/zero/1.0) (Public Domain).

## Users

Don’t hesitate to take a look at or try out some of the early implementations of the draft spec!

For feedback on

* the draft spec, the Reactive Streams initiative or general feedback:

    please open an Issue on the [Reactive Streams project](https://github.com/reactive-streams/reactive-streams/issues).

* the implementations themselves:

    please direct that to the implementor via their preferred feedback system listed below.

### Implementations of the draft spec

* Akka Streams
   * See this [Activator template](http://www.typesafe.com/activator/template/akka-stream-scala) introducing the [Akka Project](http://akka.io/) implementation in Scala; a Java version will follow shortly.
   * Please give [Feedback](http://doc.akka.io/docs/akka/current/project/issue-tracking.html) on the issue tracker.
* Reactor Composable
   * [Reactor (1.1+)](http://github.com/reactor/reactor)
   * Current Implementation Draft is being explored for 1.1 and onwards, see Reactor Composable
* RxJava
   * See [github.com/ReactiveX/RxJavaReactiveStreams](https://github.com/ReactiveX/RxJavaReactiveStreams).
* [Ratpack](http://www.ratpack.io)
   * See the [“Streams”](http://www.ratpack.io/manual/current/streams.html) chapter of the manual.

## Implementors

To get started implementing the draft specification, it is recommended to start by reading the [README](https://github.com/reactive-streams/reactive-streams/blob/v1.0.0.RC3/README.md), then taking a look at the [Specification](https://github.com/reactive-streams/reactive-streams/blob/v1.0.0.RC3/README.md#specification) then taking a look at the [TCK](https://github.com/reactive-streams/reactive-streams/tree/v1.0.0.RC3/tck). If you have an issue with any of the above, please take a look at [closed issues](https://github.com/reactive-streams/reactive-streams/issues?page=1&state=closed) and then open a [new issue](https://github.com/reactive-streams/reactive-streams/issues/new) if it has not already been answered.
