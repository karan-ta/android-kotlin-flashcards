
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

what is runblocking
?
runblocking is a coroutine builder that blocks the current thread 
until all tasks of the co routine it creates finish

what is launch
?
launch creates a new co routine. 
the new co routine gets suspended to release the thread for other tasks and resumes.
the co routine created can resume on a different thread.

what is async
?
same as launch but the only difference is 
it returns some value to the caller.
Deferred<T>

what is relationship between launch, async  and coroutine scope
?
launch , async are extension functions to co routine scope.
you can pass a suspending function as an argument.


