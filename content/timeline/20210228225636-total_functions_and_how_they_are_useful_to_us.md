+++
title = "Total functions and how they are useful to us"
author = ["Georgi Bojinov"]
date = 2021-02-28T00:00:00+02:00
slug = "20210228225636-total-functions-and-how-they-are-useful-to-us"
draft = false
+++

## Note {#note}

Functions in programming are different from maths as they are a concrete implementation of something
abstract, and thus have problems like how long they take to compute and whether they finish or hang.
They have side effects as well. But FP mitigates some of these differences (e.g. pure functions), which allows us to talk about totality.

A total function terminates and returns an output value for every value of the input domain.
Totality in programming means avoiding runtime exceptions by preventing them from happening at compile time.
Real totality is achieved without a bottom value, that in programming is usually something like `undefined` in
Haskell, which throws exceptions at runtime and makes stuff partial. An example of a pure language is Dhall, a config language - all functions must be pure, total, and terminating.

Benefits:

-   Not having to worry about missing cases in tests, as your function handles all inputs by being total and
    won't blow up
-   Easier refactoring due to composition of total functions being total
-   Less production failures with unexpected exceptions
-   Easier to reason about when there aren't unforeseen edge cases lurking in the back


## Links to this note {#links-to-this-note}

-   [Totality in Functional Programming]({{< relref "20210228222248-totality_in_functional_programming" >}})

> [Total functions and how they are useful to us]({{< relref "20210228225636-total_functions_and_how_they_are_useful_to_us" >}})
