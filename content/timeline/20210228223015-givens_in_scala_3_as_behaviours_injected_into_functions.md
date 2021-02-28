+++
title = "Givens in Scala 3 as behaviours injected into functions"
author = ["Georgi Bojinov"]
date = 2021-02-28T00:00:00+02:00
slug = "20210228223015-givens-in-scala-3-as-behaviours-injected-into-functions"
draft = false
+++

## Note {#note}

What is the use case of `givens` in Scala 3?
They are a replacement for `implicits`, avoiding to explicitly have to pass instances used at call site.
`Given` is well named - it is considered a "given" to the function. We don't instantiate it as we do with
implicits, but rather automatically creates instances to be injected in the function at call site.

An example of a `given` instance that defines an ordering behaviour for a custom type `Person`:

```scala
given personOrdering as Ordering[Person] {
  override def compare(x: Person, y: Person): Int =
    x.surname.compareTo(y.surname)
}
```

And then in the function to use it:

```scala
def listPeople(people: List[Person])(using ordering: Ordering[Person]) = ???
```

This way we don't need to explicitly pass the `ordering` argument. We are `using` the ordering behaviour we have
previously defined for the `Person` type. This encodes the concept of type classes, e.g. behaviours for types.


## Links to this note {#links-to-this-note}

-   [Given and Using Clauses in Scala 3]({{< relref "20210228222135-given_and_using_clauses_in_scala_3" >}})

> [Givens in Scala 3 as behaviours injected into functions]({{< relref "20210228223015-givens_in_scala_3_as_behaviours_injected_into_functions" >}})
