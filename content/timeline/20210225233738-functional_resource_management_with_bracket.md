+++
title = "Functional Resource Management with Bracket"
author = ["Georgi Bojinov"]
date = 2021-02-25T00:00:00+02:00
slug = "20210225233738-functional-resource-management-with-bracket"
draft = false
+++

## Note {#note}

A problem when acquiring resources for use in applications (opening files, database connections, http
connections) is closing them even when the operation fails. Imperative programs have `try,catch,finally` for
this, but what does Cats Effect have in the functional world?
It has `Bracket`. It's a type class that can have an instance for a custom type, it is also defined for `IO` by default.

Some of its usages are as follows.

The close will run even if any of the other operations fails or succeeds

```scala
open(file).bracket { readFile } { close }
```

Also guarantee is another function like this
This is the same idea as `try,catch,finally`, the `otherAction` will always run.

```scala
action.guarantee(otherAction)
```


## Links to this note {#links-to-this-note}

-   [Basic Resource Management With Bracket in Cats-Effect - Scala Tutorial]({{< relref "20210225233600-basic_resource_management_with_bracket_in_cats_effect_scala_tutorial" >}})

> [Functional Resource Management with Bracket]({{< relref "20210225233738-functional_resource_management_with_bracket" >}})
