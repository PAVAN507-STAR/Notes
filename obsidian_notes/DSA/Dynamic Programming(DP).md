*Basics*
- Dynamic programming => technique used when the problem can be solved by solving its sub problems.
- Identify  & solve  sub problems => Use solved sub problems to solve larger problems
- Dynamic Program = Recursion + Memoization
- Memoization => storing the previous results obtained in a dictionary so we can avoid recalculating things again and rather get them from stored dictionary 
- ![[Pasted image 20240715222757.png]]
- ![[Pasted image 20240715222731.png]]
- A bottom up approach is where u want to avoid using recursion calls and just use loops
- The solution of subproblem is stored in cache and if same sub problem encountered again then access it from cache which takes O(1) time rather than computing again which takes O(2$^k$).
- ![[Pasted image 20240729200628.png]]![[Pasted image 20240729200918.png]]
- Deciding data structure of cache is important step in memoization. The cache should be capable of storing results of all subproblems. Usually cache is an array. If our problem has only one dimension, then it is one-dim array, else we use multi-dimensional array.
- Memoization = Recursion + Cache - Overlapping results
- ![[Pasted image 20240729201557.png]]
- TopDown approach mostly is made of using recursion as the name suggest we go from top to down like for example for n! we calculate (n-1)! and so on till 1! .We go from main problem to sub problem base case
- Bottom Up approach is mostly by loops and here for example for 4! we calculate 1! and then use it in 2! and use it 3! and use it 4!.We calculate from the base sub problem to original problem asked.
- ![[Pasted image 20240731234400.png]]
- ![[Pasted image 20240801000412.png]]
- 