> sept 17

# stack & heap
* stack is where the frames go
* heap is where the objects go
# frames
* global frame (well its the global frame, code w/ zero indents)
	* however, there is also a built-ins frame that is above the GF
		* i.e. defines print, max, int, str
		* accordingly, there would be a section of the heap that is already being used
* the frames basically define the context of the code / variables
# functions
* arguments are the objects you pass in when you call
* parameters are the variable names when you define the function
* when you define a function it gets added to the heap
	* at the same time, you define an enclosing frame, which is the frame where the function is defined
* when you call a function you make a new subframe
	* this frame will have a parent frame which is the function's enclosing frame
	* any variable name not in the new subframe will be searched for in the parent frame
	* after the function returns/ends, the subframe will be garbage collected
# variables
* a variable name must always be assigned to something / have a reference to an object in heap
	* any object that has no variable referring to it will be garbage collected
* value is synonymous with object
* during assignment, the right side is evaluated first
	* this means that before the variable name refers to the object,
	* the right side is first pushed the the heap
# reserved keywords
* keywords that python will not let you use as variable names
	* def
	* return