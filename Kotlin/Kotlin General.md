
---
tags: review
---

what does it mean by kotlin is a statically typed language
?
type of every expression is known at compile time.  
compiler can validate whether the object has the properties , methods used by the object.
<!--SR:!2023-08-27,14,290-->

what are data classes
?
They provide a concise syntax for creating immutable value objects.
<!--SR:!2023-08-28,15,290-->

does kotlin enforce the functional style like haskell?
?
kotlin lets you program in the functional style but does not enforce it.
<!--SR:!2023-08-27,14,290-->

kotlin philosophy
?
pragmatic  
concise  
safe  
interoperable
<!--SR:!2023-08-28,15,290-->

In kotlin , can user define their own operator ?
?
No
<!--SR:!2023-08-30,17,290-->

How does kotlin strive to remove the null pointer exception from program
?
Kotlin's type system tracks values that can and cant be null  
and  
forbids operations that can lead to null pointer exception at runtime.

what is kotlin smart cast
?
the check and the cast are combined into a single operation.  
If you have checked for the type then you do not need to cast it  
if (value is String)  
value.upperCase () // you can use string methods as check is done
<!--SR:!2023-08-25,4,291-->

explain how kotlin compilation works
?
kotlin compiler compiles kt file to class file  
class file is converted to jar file.  
kotlin runtime library is distributed with the application  
  
gradle.maven take care of including the kotlin runtime library as a dependency of the project

does function need to be in a class
?
No. it can be at top of file

difference between statement and expression
?
expression has a value.  
statement does not have a value.  
assignments are statements in kotlin.  
control structrures except loops are expressions.  
If is an expression

explain block body , expression body of a function
?
if the body of a function is in brackets , it has a block body.  
if function returns an expression directly , we say that it has an expression body.

can we ignore return type for function with expression body
?
yes. kotlin compiler will infer the type from the expression.
<!--SR:!2023-09-24,34,298-->

How many times can val variable be initialized
?
once.  
as below :  
val message: String  
if (canPerformOperation()) {  
message = "Success"  
// ... perform the operation  
}  
else {  
message = "Failed"  
}

is the object that a val points to mutable ?
?
yes  
val languages = arrayListOf("Java")  
languages.add("Kotlin")

when to use import statements
?
declaration can be defined in other file.  
if that file is in a different package - we need to import it.  
in kotlin - we can import a class , function.

can we have multiple classes in the same file
?
you can put multiple classes in the same file and give any name to that file.

does package heirarchy need to follow the directory heirarchy
?
no
<!--SR:!2023-09-23,33,298-->

are if , when expressions or statements
?
if, when are expressions that return a value.
<!--SR:!2023-09-23,33,298-->

In when - do you need to add a break statement in each branch.
?
No
<!--SR:!2023-09-24,34,298-->

when 
what can we pass in blank
?
any object, any expression

what can the condition of when be when no argument is passed in when
?
any boolean expression
<!--SR:!2023-08-31,2,231-->

what is return value of a block
?
last statement

if function has block body , then what is return value
?
explicit return is needed.

in a range are first , second value part of the range
?
yes  
1..10  
includes 1 , 10

half closed range
?
for (i in 0 until 10)
<!--SR:!2023-09-25,35,298-->


Range can be used for which object
?
for any instance whose class  implements the comparable interface
<!--SR:!2023-09-21,31,298-->

does kotlin differentiate between checked and unchecked exceptions
?
no
<!--SR:!2023-09-22,32,298-->

Is try a statement or an expression
?
val number = try {  
Integer.parseInt(reader.readLine())  
} catch (e: NumberFormatException) {  
null  
}
<!--SR:!2023-09-20,30,298-->

How to check if a lateinit var is already initialized
?
if(foo_coloncolon bar.isInitialized) { println(foo.bar) }
<!--SR:!2023-08-25,4,291-->

Two forms of main
?
fun main (){  
  }  
fun main (args:Array<String>){  
  }

in a function , can Unit return type be omitted 
?
yes.  
other return types cannot be ommitted

Declare a hashmap and what is "to"
?
val h = HashmapOf (1 to "one", 2 to "two", 3 to "three")  
to is a function

does kotlin use the standard java collection classes::yes
<!--SR:!2023-09-23,33,298-->

in java constant is public static final.  
what is the equivalent in kotlin 
?
const
<!--SR:!2023-09-01,9,271-->

how to call a function defined in the file StringUtil.kt from java
?
StringUtilKt.lastChar ()

while using if , when is the else branch mdandatory
?
If you're using if as an expression, for example, for returning its value or assigning it to a variable, the else branch is mandatory.
<!--SR:!2023-09-22,32,298-->

In function declaration, can we omit the Unit return type::yes

what functionality do you get out of the box when you make a data class
?
getter , setter , equals,hashcode,toString, copy, component functions.

How to do instance checks
?
when (x) { is Foo -> ... is Bar -> ... else -> ... }

create a singleton::object Resource { val name = "Name" }

How to specify return type
?
fun simpleReturn(left: Int  
Int, right: Int  
Int) : Int {  
return left + right  
}

what is inline
?
replace function code wherever its called.
less function call overhead.








