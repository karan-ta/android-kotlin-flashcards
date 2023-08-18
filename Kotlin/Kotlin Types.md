---
tags: review
---

Number types in kotlin
?
Byte, short, Int , Long , Float, Double
<!--SR:!2023-08-17,4,270-->

we can upsize literals but cannot upsize variables
?
var count: Long = 5  
println(count::class  
class)  
val thisIsInt = 5  
val thisIsLong : Long = thisIsInt  
above is compile error  
solve :  
thisIsLong = thisIsInt.toLong ()

Boolean, Boolean(with questionmark / nullable)
?
Boolean can have true, false values  
Boolean? true,false, null

example of null safety in kotlin
?
var a: String = "abc"  
a = null // compilation error  
var b: String? = "abc"  
b = null // It is correct

Notation used to define a function type
?
(type of parameters) -> return type

Explain below function types  
  (Int) -> Int  
() -> Int  
(Int) -> Unit
?
A function that takes an int and returns an int.  
A function that takes in nothing and returns an Int  
A function that takes an Int and returns nothing



