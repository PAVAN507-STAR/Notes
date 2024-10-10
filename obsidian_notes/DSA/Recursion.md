- ![[Pasted image 20240610002244.png]]
- Base condition => where function stops making new calls.
- Every call of a function will take up some memory.
- Recursion converted to a formula is recurrence relation.
- Tail recursion => is a single final recursion call of a function.
-  ![[Pasted image 20240610003934.png]]![[Pasted image 20240610004007.png]]![[Pasted image 20240610004250.png]]![[Pasted image 20240610005609.png]]
-  variables used in every call goes into => arguments
- variables used in specific to one function call goes into => body

*Recursion in Memory* 
- A function works as intialised  -> Function is called -> pushed into Activation Record -> returns a value -> poped out of Activation Record(AR)
- Activation Record is a place in memory which keeps track of all the that are currently being in executed.
- Function at top of AR is the one actually running the rest of them are just called but not in active state running.
- Load time -> this is the time where the program assigns,allocates memory for global variables or static variables assigns them their default values.
- Functions are only called after load time so if a static variable is assigned to return value of function an error is throwed.
- Load-time variables cannot be initialized with local variables.
- Load time variables get memory allocated before any function and are released at the end of execution(FILO)
- 