---
tags: review
---

try catch expression
?
fun test() {  
val result = try { count() }  
catch (e: ArithmeticException) {  
  throw IllegalStateException(e)  
} // Working with result }
<!--SR:!2023-09-20,30,290-->

If expression
?
fun main()  
{  
val x = 1  
val y = if (x == 1)  
{"one" }  
else if (x == 2)  
{"two" }  
else {"other" }}

with example
?
class Turtle {  
fun penDown()  
fun penUp()  
fun turn(degrees: Double)  
fun forward(pixels: Double)  
}  
val myTurtle = Turtle()  
with(myTurtle)  
{ //draw a 100 pix square  
penDown()  
for (i in 1..4)  
{  
forward(100.0)  
turn(90.0)  
}  
penUp()  
}

varargs example
?
Varargs allow you to pass any number of arguments by separating them with commas.  
fun printAll(vararg messages: String) { // 1  
for (m in messages) println(m)  
}  
printAll("Hello", "Hallo", "Salut", "Hola", "你好") // 2
<!--SR:!2023-09-19,29,290-->

difference between val and var
?
val is read only.  
var variable can be changed.

expression body syntax
?
fun expressionBody(left: Int  
Int, right: Int  
Int) = left + right
<!--SR:!2023-09-18,28,270-->

instanceof in kotlin 
?
is
<!--SR:!2023-09-17,27,290-->

default access modifier in kotlin
?
public by default

do you need to annotate abstract classes or functions with open
?
no , you can override them even if they are not marked as open.  
for non abstract classes - you need to mark them as open to override them.  
By default classes in kotlin are final.
<!--SR:!2023-08-31,8,261-->

which is the common super class of all classes in kotlin::ANY
<!--SR:!2023-08-27,4,290-->

which methods does ANY class have::equals,hashcode,toSTring
<!--SR:!2023-08-24,3,250-->

By Default , kotlin classes are::final

How to make a class open for inheritance
?
mark it as open  
open class Base

how to override a method of a class in kotlin
?
keep class open.  
keep method open.  
use override keyword in method of derived class.

What is the use of string templates
?
we do not have to use + concatenation.  
println("My name is ${name.toUpperCase()}")
<!--SR:!2023-09-17,27,290-->

Pair data type
?
val capitol = "England" to "London" println(capitol.first) // Prints: England println(capitol.second) // Prints: London
<!--SR:!2023-09-22,32,290-->

what are immutable collections and mutable collections
?
immutable - we cannot add or remove items.  
mutable - we can add or remove items.
<!--SR:!2023-09-15,25,270-->

smart cast
?
if the kotlin compiler knows that x is a string after performing a check then it will automatically convert x to a string , without any explicit casts.
<!--SR:!2023-09-21,31,290-->

how to define anonymous function
?
just use the fun keyword without any function name:  
  val a = fun ()  
{  
println ("hello world")  
}

what are lambda expressions
?
simplest way to define anonymous functions

get type of a variable named images
?
println("${images_coloncolonclass.simpleName}")

find size of arraylist::size property of arrayList

for loop from and to a number
?
for (i in 1..3) {  
println(i)  
}

for loop downward
?
for (i in 6 downTo 0 step 2) {  
println(i)  
}

What is inline function 
?
inline function : function defined as inline its entire content will be copied to the plaes where it is called when this kotlin code is decompiled to java 
use it when funtion is small and is called only in few places

what is noinline
?
noinline  is in case you want a param out of two params on an inline function to be be inlined

what is lateinit
?
lateinit means we can initialize it before accesing 

what is lazy
?
lazy : means it will be initialized when it is accesed
<!--SR:!2023-09-22,32,290-->

String interpolation::"Hello $name"

${}
?
Arbitary expressions can be used.  
println ("The value of count is not ${count + 1})
<!--SR:!2023-09-18,28,290-->

if constructor parameters do not have var or val  
what are they
?
They are construction parameters . not properties.  
they can be accessed from init block but not from function

what is a kotlin property
?
field  
getter function  
setter function

protected access modifier::can only be accessed in sub class.  
<!--SR:!2023-08-24,3,250-->
not outside.

companion object::If you declare a companion object inside your class , you can access its members using only the class name as the qualifier.
override example
?
open class Shape {  
open fun draw (){  
}  
fun fill (){  
}  
}  
class Circle():Shape(){  
fun draw (){  
}  
fun fill (){  
  }  
override fun draw (){  
  }  
}
<!--SR:!2023-09-17,27,290-->

suppose a class is final , but member is declared as open - then what will happen
?
no effect

can you override val property with a var property::yes

can you override var property with a val property
?
no
<!--SR:!2023-09-13,23,250-->

can interface have constructor::no

destructive declarations in kotlin
?
val (country, city) = capitol  
println(country) // Prints: England println(city) // Prints: London
list of pairs example
?
val capitols = listOf("England" to "London", "Poland" to "Warsaw")  
capitols.forEach { (country, city) -> println("Capitol of $country is $city") }  
val capitols = listOf ("delhi" to "india","sydney" to "australia")for ((c,co) in capitols){println (c)println (co)}
<!--SR:!2023-09-18,28,290-->

lambda expressions android example
?
view.setOnClickListener { println("Click") }
<!--SR:!2023-09-18,28,290-->

any example
?
var title: Any = "Kotlin"  
title = 12

assignment of nullable type to non nullable type
?
var nullableVehicle: Vehicle_question
var vehicle: Vehicle  
nullableVehicle = vehicle // 1  
vehicle = nullableVehicle // 2, Error
<!--SR:!2023-09-17,27,290-->

what is const
?
const inlines the value of the variable reducing overhead 

what is reified
?
```kotlin
inline fun <reified T> doSomething(value: T) {
    println("Doing something with type: ${T::class.simpleName}")    // OK
}
``` 










	





