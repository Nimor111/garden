+++
title = "Where can we introduce partiality in functions?"
author = ["Georgi Bojinov"]
date = 2021-02-28T00:00:00+02:00
slug = "20210228225514-where-can-we-introduce-partiality-in-functions"
draft = false
+++

## Note {#note}

A function that is not total, is partial.
Yet again pertaining to Haskell, but is valid for other FP languages.

Where partiality can be introduced:

-   Non-exhaustive pattern matching
-   Missing conditions in guards
-   Any pattern matching, basically
-   Unspecified fields of records / structs / etc.
-   Using bottom, e.g. `error` and `undefined` in Haskell
-   Non-terminating loops
-   Seg faults, and other low-level issues

Be careful when using wildcards, as adding new cases to types will lead to unexpected behaviour - prefer
matching on all cases of a type instead when pattern matching.
Same goes when using `error` for seemingly unreachable code, or "trusting" that functions from libraries are total.


## Links to this note {#links-to-this-note}

-   [Totality in Functional Programming]({{< relref "20210228222248-totality_in_functional_programming" >}})

> [Total functions and how they are useful to us]({{< relref "20210228225636-total_functions_and_how_they_are_useful_to_us" >}})
