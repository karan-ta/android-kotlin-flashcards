
---
tags: review
---

are extension functions resolved statically or at runtime
?
statically  
abstract class A  
class B: A()  
fun A.foo() { println("foo(A)") }  
fun B.foo() { println("foo(B)") }  
val b = B()  
b.foo() // prints: foo(B)  
(b as A).foo() // 1, prints: foo(A)  
val a: A = b  
a.foo() // 1, prints: foo(A)
<!--SR:!2023-08-13,4,270-->

how to make an extension function
?
put the name of the class or interface that you're extending  
before the name of the function you're adding.  
class name is called the receiver type  
instance of receiver type is the receiver object
fun Int.newFunction(){
}

do extension functions have access to private or protected members of the class
?
no .  
extension functions do not allow to break encapsulation




