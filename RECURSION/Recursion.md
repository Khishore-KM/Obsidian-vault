When a function calls itself until a specific condition is met.

If no condition is specified then it will be executed infinite times.
this causes stack overflow and memory leak. 
##### Examples:
					- Tower of hanoi.
					- Inorder/Preorder/Postorder Tree Traversals.
					- DFS of graph.

##### Why recursion?
Recursion helps us in a number of way to reduce the length of the code.
A task that can be defined with similar sub tasks , for it recursion is the best solution.

###### Difference between direct and indirect recursion:

###### Direct recursion:
If a function calls itself then it is called direct recursion.

###### Indirect recursion:
If a function calls a function and that function calls the original function then it is called indirect recursion.

###### Finite recursion:
It occurs when the recursion terminates after a finite number of recursive calls.
The recursion terminates after  base condition is met.

###### Infinite recursion:
In infinite recursion the recursion doesn't terminate after a finite number of times.
This causes segmentation fault.

###### Tail recursive function:
Tail recursion is defined as a recursive function in which the recursive call is the last statement that is executed by the function. So basically nothing is left to execute after the recursion call.

The tail recursive functions are considered better than non-tail-recursive functions as tail recursion can be optimized by the compiler.
The idea used by the compiler to optimize tail-recursive functions is simple , since the recursive call is the last statement there is nothing left in the current statement to execute , hence saving the current statements stack frame is of no use.

###### Implicit recursion:
A specific sort of recursion called **implicit recursion** occurs when a function calls itself without making an explicit recursive call. This can occur when a function calls another function, which then calls the original code once again and starts a recursive execution of the original function.

##### Tower of Hanoi problem:
This is a mathematical puzzle in which there will be three rods and n number of disks the disks are stacked in decreasing order of the diameter . The objective is to move the disk to another rod obeying rules.
- Only one disk can be moved at a time.
- Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack.
- No disk can be placed on top of a smaller disk.


