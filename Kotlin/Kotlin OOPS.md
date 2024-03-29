
---
tags: review
---

difference between primary , secondary constructor
?
class Mentor(fname:String){
constructor(fname:String,age:Int):this(fname){   }
}
no code in primary constructor. secondary constructor can have code

When does the init block get called in kotlin
?
The init block in kotlin gets called after the primary constructor and before the secondary constructor
init block can use constructor parameters of primary constructor. there can be multiple init blocks

How do kotlin interfaces differ from those of java
?
kotlin interfaces can contain property declarations.

By default what are kotlins class declarations.
?
kotlins class declarations are public and final by default.

do nested classes contain an implicit refrence to their outer class
?
nested classes arent inner by default. 
they do not contain an implicit refrence to their outer class.

What does the object keyword do 
?
declares a class and creates an instance of the class

what does the sealed modifier do 
?
it restricts the possible subclasses of a class or implementations of an interface.

should abstract class be marked as open 
?
no , abstract class can be inherited.
we do not need to mark it as open.

what can kotlin interfaces contain
?
definitions of abstract methods
implementations of non abstract methods

how to check if lateinit is already initialized
?
if (foo::bar.isInitialized) { println(foo.bar) }

Backing field 
?
custom setter needs a backing field 
var counter = 0 // the initializer assigns the backing field directly set(value) { if (value >= 0) field = value // counter = value // ERROR StackOverflow: Using actual name 'counter' would make setter recursive }

which requirement should compile time constant follow
?
- It must be a top-level property, or a member of an [`object` declaration](https://kotlinlang.org/docs/object-declarations.html#object-declarations-overview) or a _[companion object](https://kotlinlang.org/docs/object-declarations.html#companion-objects)_.
- It must be initialized with a value of type `String` or a primitive type
- It cannot be a custom getter

why do we need lateinit
?
Normally, properties declared as having a non-null type must be initialized in the constructor. However, it is often the case that doing so is not convenient. For example, properties can be initialized through dependency injection, or in the setup method of a unit test. In these cases, you cannot supply a non-null initializer in the constructor, but you still want to avoid null checks when referencing the property inside the body of a class.To handle such cases, you can mark the property with the `lateinit` modifier:

In a class, can a val property have a setter
?
no, only var can have a setter

can interface have a property
?
yes Interface can have a property.
property in interface cannot be initialized.
it can be abstract 
or have a custom getter

which error we get if we try to initialize property in an interface
?
property initializers are not allowed in interfaces.

can property of interface have a backing field
?
no, no setter in property of backing field. 

If you derive a class from 2 interfaces and both interfaces have the same method, then what will happen
?
class must override because it inherits multiple methods of it.

What does the class declaration consist of
?
class name
class header
class body
class header and body are optional.
if class body is not there then no need for curly braces.
example:
class Empty

Give example of primary constructor
?
class Person constructor(firstName:String){}
if constructor does not have any annotation or visibility modifiers , the constructor keyword can be omitted.

How to run code during object creation
?
The class header can't contain any runnable code. If you want to run some code during object creation, use _initializer blocks_ inside the class body

where can primary constructor parameters be used
?
initializer blocks , property initializers
class Customer(name: String) { val customerKey = name.uppercase() }

How can we declare properties and initialize them using primary constructors
?
class Person(val firstName: String, val lastName: String, var age: Int)


are constructor parameters and property initialized in constructor both accessible in property initializer, 
initializer block
?
yes

What is constructor delegation
?
if a class has a primary constructor and a secondary constructor,
each secondary constructor has to delegare to the primary constructor 
either directly or indirectly through another secondary constructor.
class Person(val name: String) {
constructor(name: String, parent: Person) : this(name)
}

what is the order of execution of primary constructor , initializer block , secondary constructor
?
Code in initializer blocks effectively becomes part of the primary constructor. Delegation to the primary constructor happens at the moment of access to the first statement of a secondary constructor, so the code in all initializer blocks and property initializers is executed before the body of the secondary constructor.

Does delegation happen if there is no primary constructor
?
Even if the class has no primary constructor, the delegation still happens implicitly, and the initializer blocks are still executed:

what error we get if secondary constructor does not delegate to primary constructor
?
Primary constructor call expected.

How to make private primary constructor
?
class DontCreateMe private constructor() { /*...*/ }

what can class contain
?
constructors and initializer blocks
functions
properties
nested and inner class
object declarations

for which class or function - we do not need to use open keyword
?
abstract

does every class have implicit primary constructor generated
?
yes

how can a class be made ready to become a parent class
?
the class should be abstract or annotated with open keyword

while inheriting a class , do we need to initialize the constructor of the parent class
?
yes
class child:parent**()**

can abstract function have a body 
?
no

By default are class, function final
?
By default class, function are public , final

can you override non abstract method with abstract method
?
yes 
non abstract , open method can be overriden with abstract method

why do we need Companion objects
?
If you need to write a function that can be called without having a class instance but that needs access to the internals of a class (such as a factory method), you can write it as a member of an [object declaration](https://kotlinlang.org/docs/object-declarations.html) inside that class.
Even more specifically, if you declare a [companion object](https://kotlinlang.org/docs/object-declarations.html#companion-objects) inside your class, you can access its members using only the class name as a qualifier.







