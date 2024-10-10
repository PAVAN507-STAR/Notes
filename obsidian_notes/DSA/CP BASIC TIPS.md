- To find **gcd(a,b)** we can use gcd(a%b,b) assuming a>b and a=a%b or b=b%a until one of them becomes zero and other left is the gcd![[Pasted image 20240526154812.png]]
  - Use **hashing** to **count the frequency** of a character or number in array .If using C++ make sure that hash array size if more than 10^6 its declared globally.
  - To **sort an array of 0,1,2 's** use **national dutch flag algorithm** which is the optimal way to sort such type of arrays.Implementation =>  ![[Pasted image 20240528010300.png]]
  - Algorithm => - Keep three indices low = 1, mid = 1, and high = N and there are four ranges, 1 to low (the range containing 0), low to mid (the range containing 1), mid to high (the range containing unknown elements) and high to N (the range containing 2).
  Traverse the array from start to end and mid is less than high. (Loop counter is i)
  If the element is 0 then swap the element with the element at index low and update low = low + 1 and mid = mid + 1
  If the element is 1 then update mid = mid + 1
  If the element is 2 then swap the element with the element at index high and update high = high – 1 and update i = i – 1. As the swapped element is not processed
  Print the array.
  - `1<<(n.bit_length()-1)` => to find the largest and nearest 2 powered number to n.
  - To find **subsets** of an array use power set method (brute force method)
  - ![[Pasted image 20240601125617.png]] 
  - Optimal Solution![[Pasted image 20240601161109.png]]
# Bitwise Manipulation:
  - a & b <= min(a,b)
  - AND of a subarray has an importance property: the longer of the subarray, the smaller of the AND values.
# Sorting 
- Merge sort ![[Pasted image 20240603012450.png]]
- Use sparse array that is when u know ure going to use only some part of array for sure keep the rest of unused values zero
- 