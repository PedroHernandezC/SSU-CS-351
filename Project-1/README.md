1. Which program is fastest? Is it always the fastest?
malloc seems to be the fastest through all trials however alloc is very close second.

2. Which program is slowest? Is it always the slowest?
list seems to be the overall slowest in all trials and by a fair bit. In the trial testing numblock=10,000,000 alloc fails so its hard to determine if it is slower.

3. Was there a trend in program execution time based on the size of data in each Node? If so, what, and why?
malloc and alloc become faster when increasing the min or max bytes of the node. the larger node sizes can hold more data so less of them are needed to store the same information. so less brk commands are made during execution.

4. Was there a trend in program execution time based on the length of the block chain?
malloc seems to be the fastest through all trials. list and new seam to run in about the same amount of time.

5.Consider heap breaks, what's noticeable? Does increasing the stack size affect the heap? Speculate on any similarities and differences in programs?
Increasing the size of the stack will allow for many more stack frames that would normally cause an overflow into the heap. So it only indirectly affects the heaps

6. Considering either the malloc.cpp or alloca.cpp versions of the program, generate a diagram showing two Nodes. Include in the diagram the relationship of the head, tail, and Node next pointers. show the size (in bytes) and structure of a Node that allocated six bytes of data include the bytes pointer, and indicate using an arrow which byte in the allocated memory it points to.
					
```
		          |---------------|        |---------------| <—- byte* tail
   byte* head —-> | byte* next    | —->    | byte* next    | —-> null
		          |---------------|        |---------------|
		          |6 bytes of     |        | 6 bytes of    | 
                  |   data        |        |  data         |
		          |---------------|        |---------------|
```
7. There's an overhead to allocating memory, initializing it, and eventually processing (in our case, hashing it). For each program, were any of these tasks the same? Which one(s) were different?
The initialization of memory should be about the same and so should the hashing processes.
List has unique overhead as its part of the STL. Malloc and new are allocated to the heap and so have their own overhead.

8. As the size of data in a Node increases, does the significance of allocating the node increase or decrease?
The larger the node the more data needs to be allocated but the overhead largely stays the same. In this way the allocation of larger nodes is less significant.

