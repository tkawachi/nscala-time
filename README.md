nscala-time
===========

A new Scala wrapper for Joda Time.  This project forked from [scala-time](https://github.com/jorgeortiz85/scala-time/ "scala-time") since 
it seems that scala-time is no longer maintained.

USAGE:

```scala
import com.github.kmizu.nscala.time.Imports._

DateTime.now // returns org.joda.time.DateTime = 2009-04-27T13:25:42.659-07:00

DateTime.now.hour(2).minute(45).second(10) // returns org.joda.time.DateTime = 2009-04-27T02:45:10.313-07:00

DateTime.now + 2.months // returns org.joda.time.DateTime = 2009-06-27T13:25:59.195-07:00

DateTime.nextMonth < DateTime.now + 2.months // returns Boolean = true

DateTime.now to DateTime.tomorrow  // return org.joda.time.Interval = > 2009-04-27T13:47:14.840/2009-04-28T13:47:14.840

(DateTime.now to DateTime.nextSecond).millis // returns Long = 1000

2.hours + 45.minutes + 10.seconds
// returns org.scala_tools.time.DurationBuilder
// (can be used as a Duration or as a Period)

(2.hours + 45.minutes + 10.seconds).millis
// returns Long = 9910000

2.months + 3.days
// returns Period
```

This is mostly a convenience wrapper around the Joda Time libraries, adding
more pleasant syntax like operators for addition, subtraction, and comparison.
Also, most fields usually available as "getField" are now simply available as
"field", following the Scala convention. Some instances of "asX" or "toX" have
also been shortened.

Please see Joda Time for full explanation of key concepts and API:
http://joda-time.sourceforge.net/index.html

INSTALLATION:

Add the following to your sbt build (for Scala 2.9.1, Scala 2.9.2, and Scala 2.10-RC1):

```scala
libraryDependencies += "com.github.kmizu" %% "nscala-time" % "0.2-SNAPSHOT"
```

MOTIVATION:

The Java Date and Calendar libraries are largely inadequate. They are mutable, not thread-safe, and very inconvenient to use.

The Joda Time library is a great replacement for Java's Date and Calendar classes. They're immutable by default, have a much
richer and nicer API, and can easily be converted to Java's Date and Calendar classes when necessary.

This project provides a thin layer of convenience around the Joda Time libraries, making them more idiomatic to use within Scala.