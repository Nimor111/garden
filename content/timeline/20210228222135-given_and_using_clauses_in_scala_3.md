+++
title = "Given and Using Clauses in Scala 3"
author = ["Georgi Bojinov"]
date = 2021-02-28T00:00:00+02:00
slug = "20210228222135-given-and-using-clauses-in-scala-3"
draft = false
+++

## Notes {#notes}

[Givens in Scala 3 as behaviours injected into functions]({{< relref "20210228223015-givens_in_scala_3_as_behaviours_injected_into_functions" >}})

[Givens in Scala 3 as proofs of existence of types]({{< relref "20210228223600-givens_in_scala_3_as_proofs_of_existence_of_types" >}})

Other random facts about `givens`:

To import `givens`:

```scala
object Givens {
  given personOrdering as Ordering[Person] {
    ???
  }
}

import Givens.personOrdering
import Givens.{given Ordering[Person]}
import Givens.{given _}
```

Givens can be "derived" (as this is not the same as deriving in Haskell for example, where instances are defined
automatically). Here it means, when you have a higher kinded type like `Ordering[T]` for example, you can write
an instance for `Ordering[Option[T]]` using the first instance.

```scala
given optionOrdering[T](using tOrdering: Ordering[T]) as Ordering[Option[T]] {
  // pattern match on Option values
  def compare(optionA: Option[T], optionB: Option[T]) = ???
}
```

With implicits you would have to use `implicitly` to fetch the implicit for the type `T`, which adds more
confusion to the mix. It took me an embarrassing amount of time to understand `implicitly`.

Can't have > 1 `given` instance for a type. Compiler would be confused which one to pick. Be good to the compiler!

Uses of `givens`:

1.  Type classes
2.  Dependency Injection
3.  Type level programming

Comparison with `implicits` - better syntax, better name, less boilerplate. This seems like a great step towards
making one of the most powerful but esoteric features of Scala more accessible to newcomers.


## Resources {#resources}

<https://blog.rockthejvm.com/scala-3-given-using/>
