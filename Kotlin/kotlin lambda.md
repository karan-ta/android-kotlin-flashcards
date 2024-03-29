
---
tags: review
---

what is {1}
?
() -> Int
<!--SR:!2023-08-26,13,290-->

what is {s:String->println(s)}
?
(String)->Unit
<!--SR:!2023-08-26,13,290-->

what is {a:Int,b:Int -> a*b}
?
(Int,Int)->Int
<!--SR:!2023-08-27,14,290-->

In lambda expressions , what is the return value
?
last statement is the return value.  
return keyword is not allowed.
<!--SR:!2023-08-24,11,270-->

can we have lambda expression without lambda parameter
?
yes  
  
if there is only one parameter  
and  
the parameter type can be inferred  
  
val a: (Int) -> Int = { it * 2 } // 1  
val c: (String)->Unit = { println(it) } // 2
<!--SR:!2023-09-05,7,270-->

pass a lambda to a function
?
fun acceptLambda (a:()->Unit)  
{  
a ()  
}  
fun main ()  
{  
acceptLambda {println ("Hello World")}  
}
<!--SR:!2023-08-28,15,290-->

lambda example with list
?
fun main (){  
  
var myList = listOf ("karan","priya","vihaan")  
  
println (myList.filter {it.length>5}.map {it.uppercase()})  
}
<!--SR:!2023-08-29,16,290-->

pass lambda with parameters
?
fun execLambda (op1:Int,op2:Int,func:(op1:Int,op2:Int)->Int){  
  
println (func (op1,op2))  
}  
fun main (){  
  
execLambda (1,3) {op1:Int,op2:Int -> op1+op2 }  
  
execLambda (1,3) {op1:Int,op2:Int -> op1*op2 }  
  
}
<!--SR:!2023-09-30,38,290-->

lambda where parameters are not defined but are implicit
?
fun <T> myFilter (list:List <T>,predicate:(T)->Boolean){  
list.forEach{  
if (predicate (it))  
println (it.toString())  
}  
}  
fun main (){  
myFilter(listOf ("karan","priya","vihaan","j")){it.length>1}  
}
<!--SR:!2023-08-29,16,300-->

Pass a list of lambda expressions
?
fun callFunctions (list:List<()->Unit>){  
for (item in list)  
item ()  
}  
fun main() {  
callFunctions(  
listOf (  
{println ("Hello")},  
{println ("world")}  
)  
)  
}
<!--SR:!2023-08-31,18,300-->







	




