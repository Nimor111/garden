+++
title = "Parallel typeclass pattern"
author = ["Georgi Bojinov"]
date = 2021-02-25T00:00:00+02:00
slug = "20210225232633-parallel-typeclass-pattern"
draft = false
+++

## Note {#note}

The Parallel typeclass is an abstraction over the conversion between an Applicative and a Monad, e.g. when we
want to do certain operations in parallel with an applicative instance, but then convert back to the monad to
use a for comprehension.

An example of it would be a conversion between Validated and Either, e.g. an Either with a List of errors as the
Left. Another example is IO and ParIO.

The definition is as follows:

```scala
trait Parallel[F[_]] {
  type M[_]
  def F: Monad[F]
  def M: Applicative[F]

  def parallel: F ~> M
  def sequential: M ~> F
}
```

`parallel` and `sequential` are natural transformations between the Monad and the Applicative, e.g. functions
without loss of information.


## Links to this note {#links-to-this-note}

-   [The Parallel Typeclass in Cats - Scala Tutorial]({{< relref "20210225232120-the_parallel_typeclass_in_cats_scala_tutorial" >}})

> [Parallel typeclass pattern]({{< relref "20210225232633-parallel_typeclass_pattern" >}})
