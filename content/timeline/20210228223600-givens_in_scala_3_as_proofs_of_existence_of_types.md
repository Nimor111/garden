+++
title = "Givens in Scala 3 as proofs of existence of types"
author = ["Georgi Bojinov"]
date = 2021-02-28T00:00:00+02:00
slug = "20210228223600-givens-in-scala-3-as-proofs-of-existence-of-types"
draft = false
+++

## Note {#note}

From the point of view of Type level programming, a `given` proves the existence of a type - e.g. the compiler
can prove the existence of types, and then create new given instances `using` those types. This can be used for
computations at compile time. (e.g. for a type level sum for example)

A `given` is conceptually constructing an instance of a type with a concrete behaviour where a `using` claused is used.


## Links to this note {#links-to-this-note}

-   [Given and Using Clauses in Scala 3]({{< relref "20210228222135-given_and_using_clauses_in_scala_3" >}})

> [Givens in Scala 3 as behaviours injected into functions]({{< relref "20210228223015-givens_in_scala_3_as_behaviours_injected_into_functions" >}})
