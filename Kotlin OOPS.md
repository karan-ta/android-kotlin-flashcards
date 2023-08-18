
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


