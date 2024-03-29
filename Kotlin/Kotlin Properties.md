
---
tags: review
---

How to make private setter 
?
``` kotlin
    var setterVisibility: String = "abc" 
    private set // the setter is private and has the default implementation
```

why we need lateinit
?
``` kotlin

public class MyTest { 
lateinit var subject: TestSubject 
@SetUp fun setup() { 
subject = TestSubject() 
} 
@Test fun test() {
subject.method() // dereference directly
}
}

```

which property can be lateinit
?
This modifier can be used on `var` properties declared inside the body of a class (not in the primary constructor, and only when the property does not have a custom getter or setter), as well as for top-level properties and local variables. The type of the property or variable must be non-null, and it must not be a primitive type.


How to use override keyword in a primary constructor
?
``` kotlin
class Rectangle(override val vertexCount: Int = 4) : Shape // Always has 4 vertices
```


