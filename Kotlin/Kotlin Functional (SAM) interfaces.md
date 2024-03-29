---
tags: review
---

what is a functional interface
?
An interface with only one abstract method is called a _functional interface_, or a _Single Abstract Method (SAM) interface_.

How to declare a functional interface in kotlin
?
``` kotlin
```
fun interface KRunnable {
   fun invoke()
}
```
```
What is a SAM conversion
?
For functional interfaces, you can use SAM conversions that help make your code more concise and readable by using [lambda expressions](https://kotlinlang.org/docs/lambdas.html#lambda-expressions-and-anonymous-functions).

``` kotlin

fun interface IntPredicate { 
fun accept(i: Int): Boolean
}

// Creating an instance of a class 
val isEven = object : IntPredicate { 
override fun accept(i: Int): Boolean
{ return i % 2 == 0 } 
}

//SAM conversion :

val isEven = IntPredicate { it % 2 == 0 }

fun main() {
   println("Is 7 even? - ${isEven.accept(7)}")
}

```
Typealias example
?
``` kotlin
typealias IntPredicate = (i: Int) -> Boolean
val isEven: IntPredicate = { it % 2 == 0 }
fun main() { println("Is 7 even? - ${isEven(7)}") }
```

