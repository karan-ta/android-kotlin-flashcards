
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
<!--SR:!2023-09-16,26,290-->

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
<!--SR:!2023-08-30,1,193-->

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
?
Column (  
modifier = Modifier.fillMaxSize().scrollable (  
rememberScrollState (),  
orientation=Orientation.Vertical  
)
<!--SR:!2023-09-07,9,210-->

padding for text element
?
Text("Hello", modifier=Modifier.background(color = Color.Blue).padding(start = 30.dp, end=30.dp, top=10.dp, bottom = 5.dp )
<!--SR:!2023-09-12,14,273-->

padding across all axis
?
fun Modifier.padding(all: Dp)

padding across horizontal axis, vertical axis
?
Modifier.padding(horizontal = 16.dp)
Modifier.padding(vertical = 16.dp)

stateless vs stateful composable
?
stateful => caller doesnt have to manage state.  
stateful is less reusable and harder to test .
<!--SR:!2023-08-24,3,250-->

What is recomposition
?
Recomposition is typically triggered by a change to a State<T> object. Compose tracks these and runs all composables in the Composition that read that particular State<T>, and any composables that they call that cannot be skipped.
<!--SR:!2023-09-15,25,270-->

first alphabet of composable function
?
should be capital
as per coding convention

How to add a spacer
?
  
Spacer (modifier = Modifier.height (50.dp)

is UI in compose mutable or immutable
?
immutable.  
you can only change the state of the UI

How to center a column vertically
?
Modifier.gravity (Alignment.cernterVertically)
<!--SR:!2023-08-24,1,190-->

What do composable functions return
?
Composable functions don't return UI components, they emit them. That's why they must return Unit :

how to make a container composable function
?
fun MyApp(content: @Composable () -> Unit) {  
BasicsCodelabTheme {  
Surface(color = Color.Yellow) {  
content()  
}  
}}
<!--SR:!2023-08-30,7,230-->

recomposing = how is it done
?
Compose also looks at what data is needed by an individual composable so that it only needs to recompose components whose data has changed and can skip composing those that are not affected.
<!--SR:!2023-09-15,25,270-->

How is recomposing done
?
Under the hood, Compose uses a custom Kotlin compiler plugin so when the underlying data changes, the composable functions can be re-invoked to update the UI hierarchy.
<!--SR:!2023-08-25,4,273-->

How to add state to a composable
?
To add internal state to a composable, use the mutableStateOf function, which gives a composable mutable memory.  
To not have a different state for every recomposition, remember the mutable state using remember.  
and, if there are multiple instances of the composable at different places on the screen, each copy will get its own version of the state. You can think of internal state as a private variable in a class.
<!--SR:!2023-09-24,34,290-->

How to implement a non lazy list
?
val scrollState = rememberScrollState()  
Column(Modifier.verticalScroll(scrollState)) {repeat(100) {Text("Item #$it")}

Lazy Column
?
val scrollState = rememberLazyListState()  
LazyColumn(state = scrollState) {items(100) {Text("Item #$it")}}

How to make a new custom layout
?
Use Layout composable
you might need to build something unique to your app that requires measuring and laying out children manually. For that, you can use the Layout composable. In fact all higher level layouts like Column and Row are built with this.

How many parent , children does each element in the UI tree have
?
one parent , many children
<!--SR:!2023-09-19,29,290-->

which attributes does the Ui element have 
?
Also, it has a location within its parent: an (x, y) position, and a size: a width and height.  
location and size.
<!--SR:!2023-09-16,26,270-->

What is a co routine
?
A coroutine is an instance of suspendable computation. It is conceptually similar to a thread, in the sense that it takes a block of code to run that works concurrently with the rest of the code. However, a coroutine is not bound to any particular thread. It may suspend its execution in one thread and resume in another one.

From where we can call suspending functions
?
we can call suspending functions from other suspending functions
<!--SR:!2023-09-19,29,290-->

what is state hoisting
?
State hoisting is the pattern of moving state up to make a component stateless.

what are lifecycle aware components
?
components that automatically change their behaviour based on lifecycle of activity or fragment.

add state to a composable and make the state survive configuration changes 
?
rememberSaveable{}

convert list to mutableStateListOf
?
myList.toMutableStateList()

How to add viewmodel to compose
?
add lifecycle-viewmodel-compose in build.gradle

which data can be kept in remember , remembersaveable
?
we should not keep any data in remember, remembersaveable that we are afraid of loosing as 
the data is going to be destroyed whenever the composable disappears or goes out of composition
<!--SR:!2023-09-23,33,290-->

how to make OutlinedTextField
?
pass value , onValueChange, label, modifiers, colors.
label={Text()}, onValueChange = {}











	






	
