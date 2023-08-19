
---
tags: review
---

what is use of suspending function
?
when we use suspending function, we do not block the underlying thread

from where can we call suspending functions
?
every suspending function needs to be called from another suspending function.
this all need to be start from somewhere 
it starts with a co routine builder - a bridge from the normal to the suspending world.

which are the co routine builders
?
runblocking , launch , async
<!--SR:!2023-08-17,4,270-->

what is runblocking
?
runblocking is a coroutine builder that blocks the current thread 
until all tasks of the co routine it creates finish
<!--SR:!2023-08-17,4,270-->

what is launch
?
launch creates a new co routine. 
the new co routine gets suspended to release the thread for other tasks and resumes.
the co routine created can resume on a different thread.
<!--SR:!2023-08-17,4,270-->

what is async
?
same as launch but the only difference is 
it returns some value to the caller.
Deferred<T>

what is relationship between launch, async  and coroutine scope
?
launch , async are extension functions to co routine scope.
you can pass a suspending function as an argument.

How to update value of a variable in a mutually exculsive way.
or
what is alternative to synchronized keyword in java
?
mutex.withLock { counter ++ }

how to launch a coroutine in the global scope
?
GlobalScope.launch

How to launch a coroutine in the viewmodelscope
?
viewModelScope.launch

how to group two coroutines under a common scope
?
coroutineScope {
    val deferred1 = async {loadImage(name1)}
    val deferred2 = async {loadImage(name2)}
    }
    All the `async` coroutines become the children of this scope and, if the scope fails with an exception or is cancelled, all the children are cancelled, too.

how does coroutinescopr lifecycle start and stop 
?
A CoroutineScope lifecycle starts as soon as it is created and ends when it is canceled or when it associated Job or SupervisorJob finishes. When that happens, the CoroutineScope is no longer active.

why do we need CoroutineScope
?
we wish to control the lifecycle of a group of coroutines that we launch, so that we can cancel them and handle any exceptions.

How to create a **CoroutineScope**
?
`**CoroutineScope(**someCoroutineContext**)**`. Most often, the `someCoroutineContext` is a dispatcher (e.g. `Dispatchers.IO` or `Dispatchers.Main)` plus a `Job` or `SupervisorJob`.
val scope = CoroutineScope(Dispatchers.IO + SupervisorJob())









