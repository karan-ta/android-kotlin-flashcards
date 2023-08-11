
what is recycler view 
?
easily , efficiently display large sets of data
you supply data, items view definition and
recyclerview dynamically creates the elements when they are needed.

How does RecyclerView work or why is recycler view named so
?
RecyclerView _recycles_ those individual elements.
When an item scrolls off the screen, RecyclerView doesn't destroy its view. 
Instead, RecyclerView reuses the view for new items that have scrolled onscreen.

Benefits of RecyclerView
?
RecyclerView improves performance and your app's responsiveness, and it reduces power consumption.

Is Recycler View a view or a view group
?
RecyclerView is a ViewGroup that contains the views corresponding to your data.
RecyclerView is a view itself.
so you add it to the layout as you add any other UI element.

What is a ViewHolder object
?
Each indvidual element in the list is defined by the viewholder object.
You define the view holder by extending RecyclerView.ViewHolder.

Who adds data to the viewholder
?
When the view holder is created, it doesn't have any data associated with it. After the view holder is created, the RecyclerView binds it to its data.
The RecyclerView requests views, and binds the views to their data, by calling methods in the adapter.


In RecyclerView , How to define the adapter
?
You define the adapter by extending RecyclerView.Adapter.

what does the layout manager do 
?
The layout manager arranges the individual elements in your list.
Layout managers are all based on the library's LayoutManager abstract class.

which layout managers are there in recyclerview
?
Linear Layout Manager
GridLayout Manager
StaggeredGrid Layout Manager

What is LinearLayout Manager
?
LinearLayoutManager arranges the items in a one-dimensional list.

What is GridLayoutManager
?
GridLayoutManager arranges the items in a two-dimensional grid:

how are rows sized if grid is arranged vertically
?
If the grid is arranged vertically, GridLayoutManager tries to make all the elements in each row have the same width and height, but different rows can have different heights.

how are rows sized if grid is arranged horizontally
?
If the grid is arranged horizontally, GridLayoutManager tries to make all the elements in each column have the same width and height, but different columns can have different widths.

What is StaggeredGridLayoutmanager
?
StaggeredGridLayoutManager is similar to GridLayoutManager, but it does not require that items in a row have the same height (for vertical grids) or items in the same column have the same width (for horizontal grids). The result is that the items in a row or column can end up offset from each other.

which 3 key methods you override when you define adapter
?
onCreateViewHolder()
onBindViewHolder()
getItemCount()

onCreateViewHolder() definition
?
override fun onCreateViewHolder(viewGroup: ViewGroup, viewType: Int): ViewHolder {
 val view = LayoutInflater.from(viewGroup.context).inflate(R.layout.text_row_item, viewGroup, false)
}

onBindViewHolder() definition
?
override fun onBindViewHolder(viewHolder: ViewHolder, position: Int) {
 }

what is text_row_item
?
The layout for the each view item is defined in an XML layout file, as usual. In this case, the app has a `text_row_item.xml`



