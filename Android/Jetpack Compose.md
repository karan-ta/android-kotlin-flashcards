
---
tags: review
---

difference between mutablestateof and mutablestatelistof
?
mutabelStateOf implies that you want to change the entire field. If you want changes to happen when an item in a list changes, try mutabelStateListOf

composable functions can only be called from ___________ :: other composable functions

which axis does row, column have
?
main axis and cross axis.  
driving on the street is main axis. crossing on street is cross axis.

Which axis is alignment, arrangement in
?
Alignment is in cross axis. arrangement is in main axis

why should composable functions have the @composable annotation
?
this annotation informs the Compose compiler that this function is intended to convert data into UI.

properties of composable functions
?
no side effects, dont return anything, dont access global variables.

what are composables responsible for
?
your composables are responsible for transforming the current application state into a UI every time the observable data updates.

What is recomposition
?
When the state changes, the composable functions are called again with the new data. This causes the UI elements to be redrawn--this process is called recomposition.  
Recomposition is the process of calling your composable functions again when inputs change. This happens when the function's inputs change.

why should composable functions be fast
?
composable functions may be called in every frame for animations.  
To avoid jank during animation -> composable functions must be fast.

Which Order are composable functions executed
?
any order.

how often does composable function be called
?
as often as every frame for animation

why shouldnt composable functions update local variables
?
as the composable function may be called my multiple threads . so updates to local variable are not thread safe.

How to perform a side effect from a composable function
?
Again, executing all composable functions or lambdas should be side-effect free. When you need to perform a side-effect, trigger it from a callback.
as callbacks are called on the main thread

Types of vertical arrangement in column
?
Arrangement.Top  
Arrangement.SpaceBetween  
Arrangement.SpaceEvenly  
Arrangement.SpaceAround

Types of horizontal alignment in column
?
Alignment.start  
Alignment.end  
Alignment.centerHorizontally

Assign weight to child in column
?
Column(modifier = Modifier.fillMaxSize()) { Text(  
text = "First item",  
modifier = Modifier.weight(2f) )  
Text(  
text = "Second item",  
modifier = Modifier.weight(1f) ) }

Make a column scrollable





	
