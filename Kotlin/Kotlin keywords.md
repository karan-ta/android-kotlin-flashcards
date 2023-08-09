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

difference between val and var
?
val is read only.  
var variable can be changed.

expression body syntax
?
fun expressionBody(left: Int  
Int, right: Int  
Int) = left + right

instanceof in kotlin 
?
is

default access modifier in kotlin
?
public by default

do you need to annotate abstract classes or functions with open
?
no , you can override them even if they are not marked as open.  
for non abstract classes - you need to mark them as open to override them.  
By default classes in kotlin are final.

which is the common super class of all classes in kotlin::ANY

which methods does ANY class have::equals,hashcode,toSTring

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

Pair data type
?
val capitol = "England" to "London" println(capitol.first) // Prints: England println(capitol.second) // Prints: London

what are immutable collections and mutable collections
?
immutable - we cannot add or remove items.  
mutable - we can add or remove items.

smart cast
?
if the kotlin compiler knows that x is a string after performing a check then it will automatically convert x to a string , without any explicit casts.

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





