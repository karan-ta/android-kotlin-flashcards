
---
tags: review
---

What is the common superclass of all classes in kotlin
?
Any

Which methods does Any class have
?
equals, tostring,hashcode

what is open keyword
?
By default, Kotlin classes are final – they can't be inherited. To make a class inheritable, mark it with the `open` keyword

How to declare explicit supertype
?
open class Base(p: Int)
class Derived(p: Int) : Base(p)

How  to call parent class constructor from child class
?
if the child class has primary constructor, then call primary constructor of parent class from primary constructor of child class
if child class does not have primary constructor , then call parent class constructor using super keyword from the secondary constructor of child class

example - child class has primary constructor
?
open class Person(name:String){}  
class Employee(name:String):Person(name){}

example - child class does not have primary constructor
?
open class Person(name:String){}  
class Employee:Person{constructor(name:String):super(name)}

How to override a method of parent class
?
both parent class and parent method should be open

can a method marked with override keyword be overriden again 
?
A member marked `override` is itself open, so it may be overridden in subclasses. If you want to prohibit re-overriding, use `final`

which property can be overriden
?
property should be declared open
property of parent class, child class should be compatible

How to access super class inside inner class of derived class
?
Inside an inner class, accessing the superclass of the outer class is done using the `super` keyword qualified with the outer class name: `super@Outer`

How does kotlin resolve multiple inheritance
?
In Kotlin, implementation inheritance is regulated by the following rule: if a class inherits multiple implementations of the same member from its immediate superclasses, it must override this member and provide its own implementation (perhaps, using one of the inherited ones).To denote the supertype from which the inherited implementation is taken, use `super` qualified by the supertype name in angle brackets, such as `super<Base>`:






