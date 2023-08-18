---
tags: review
---

Execute if not null
?
val value = value?.let { ... // execute this block if not null }

passing nullable to non null gives compiler error
?
fun strLength(notNull: String): Int { // 7  
return notNull.length  
}  
strLength(nullable)

difference between == and ===
?
== means content equality  
=== means instance equality
<!--SR:!2023-08-30,17,290-->

Range data type in kotlin
?
for (i in 1..10) { print(i) } // 12345678910
<!--SR:!2023-08-17,4,272-->

safe call operator in kotlin
?
a?.doSomething  
if a is non null , doSomething will be called else it will be ignored and null will be returned
If-not-null shorthand
<!--SR:!2023-08-17,4,272-->

what is the elvis operator
?
question:  
question plus colon  
safe call operator  
question plus dot question.  
elvis operator can be thought of as  
if  null 
safe call operator can be thought of as 
if not null
<!--SR:!2023-08-17,4,272-->

how to convert nullable type to non nullable type
?
a?:b  
if a is null then b is returned.  
if a is not null then a is returned.

what is the not null asertion operator:: !!

what does !! do 
?

it explicitly casts nullable type to non nullable type.  
var y: String_question = "foo"  
var size: Int = y!!.length

what is let
?
let is a function defined in the kotlin standard library.  
a_question.somefunc  
  
what if somefunc is not already defined and you want to define it right now.  
  
a_question.let{  
println ("hi")  
}  
  
if a is not null then only hi will be printed.  
  
a can be accessed inside let with the it variable.





