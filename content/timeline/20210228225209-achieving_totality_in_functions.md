+++
title = "Achieving totality in functions"
author = ["Georgi Bojinov"]
date = 2021-02-28T00:00:00+02:00
slug = "20210228225209-achieving-totality-in-functions"
draft = false
+++

## Note {#note}

This pertains to Haskell, but the concepts are valid in any functional language.

How to achieve totality? Common patterns:

-   Using a default value, e.g. something like `mempty` of `Monoid`
-   Using `Maybe`, `Either`, `Validation`, `These`, which are effects to model situations like these
-   Restricting input types (e.g. `NonEmpty`, or newtypes / refinement types)
-   Make abstractions smaller (example: don't define typeclass instances for types where some of the methods might
    be partial - `Num` and `Natural` typeclass for example, as `Num` has negative values as well)
-   Compiler warnings, static analysers, program verification (a bit more specific to FP languages and Haskell)
-   Dependent types (types that depend on values) - allows you to pass in requirements for types at the type
    levels (e.g. this list will have 5 elements, this integer is not zero, these two matrices have compatible
    dimensions so that they can be multiplied)

Totality is hard - we don't have enough automated tools to enforce it for now, so we should incorporate it by following these best practices and bake it into our architecture by modeling things in a total way. Totality does not come for free.


## Links to this note {#links-to-this-note}

-   [Totality in Functional Programming]({{< relref "20210228222248-totality_in_functional_programming" >}})

> [Total functions and how they are useful to us]({{< relref "20210228225636-total_functions_and_how_they_are_useful_to_us" >}})
