---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: March
day: 26
creation date: 2024-03-26 18:09
modification date: Tuesday 26th March 2024 18:09:46
---

#internetContent  #computerScience/computerBasic 
## Article link:
[Stack vs Heap Memory Allocation - GeeksforGeeks](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)
related notes: 
- [[]]
_____
## Content

# Stack vs Heap Memory Allocation

Memory in a C/C++/Java program can either be allocated on a stack or a heap.  
Prerequisite: [Memory layout of C program](https://www.geeksforgeeks.org/memory-layout-of-c-program/).

  
****Stack Allocation:**** The allocation happens on contiguous blocks of memory. We call it a stack memory allocation because the allocation happens in the function call stack. The size of memory to be allocated is known to the compiler and whenever a function is called, its variables get memory allocated on the stack. And whenever the function call is over, the memory for the variables is de-allocated. This all happens using some predefined routines in the compiler. A programmer does not have to worry about memory allocation and de-allocation of stack variables. This kind of memory allocation is also known as Temporary memory allocation because as soon as the method finishes its execution all the data belonging to that method flushes out from the stack automatically. This means any value stored in the stack memory scheme is accessible as long as the method hasn’t completed its execution and is currently in a running state.

****Key Points:****

- It’s a temporary memory allocation scheme where the data members are accessible only if the method( ) that contained them is currently running.
- It allocates or de-allocates the memory automatically as soon as the corresponding method completes its execution.
- We receive the corresponding error Java. lang. [StackOverFlowError](https://www.geeksforgeeks.org/stackoverflowerror-in-java-with-examples/) by [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/), If the stack memory is filled completely.
- Stack memory allocation is considered safer as compared to heap memory allocation because the data stored can only be accessed by the owner thread.
- Memory allocation and de-allocation are faster as compared to Heap-memory allocation.
- Stack memory has less storage space as compared to Heap-memory.

C++

`int main() {   // All these variables get memory   // allocated on stack   int a;   int b[10];   int n = 20;   int c[n]; }`

  
 

****Heap Allocation:**** The memory is allocated during the execution of instructions written by programmers. Note that the name heap has nothing to do with the [heap data structure](https://www.geeksforgeeks.org/heap-data-structure/). It is called a heap because it is a pile of memory space available to programmers to allocate and de-allocate. Every time when we made an object it always creates in Heap-space and the referencing information to these objects is always stored in Stack-memory. Heap memory allocation isn’t as safe as Stack memory allocation because the data stored in this space is accessible or visible to all threads. If a programmer does not handle this memory well, a [memory leak](https://www.geeksforgeeks.org/what-is-memory-leak-how-can-we-avoid/) can happen in the program.

****The Heap-memory allocation is further divided into three categories:-**** These three categories help us to prioritize the data(Objects) to be stored in the Heap-memory or in the [Garbage collection](https://www.geeksforgeeks.org/garbage-collection-java/).

- ****Young Generation –**** It’s the portion of the memory where all the new data(objects) are made to allocate the space and whenever this memory is completely filled then the rest of the data is stored in Garbage collection.
- ****Old or Tenured Generation –**** This is the part of Heap-memory that contains the older data objects that are not in frequent use or not in use at all are placed.
- ****Permanent Generation –**** This is the portion of Heap-memory that contains the JVM’s metadata for the runtime classes and application methods.

****Key Points:****

- We receive the corresponding error message if Heap-space is entirely full,  [java. lang.OutOfMemoryError](https://www.geeksforgeeks.org/understanding-outofmemoryerror-exception-java/) by JVM.
- This memory allocation scheme is different from the Stack-space allocation, here no automatic de-allocation feature is provided. We need to use a Garbage collector to remove the old unused objects in order to use the memory efficiently.
- The processing time(Accessing time) of this memory is quite slow as compared to Stack-memory.
- Heap memory is also not as threaded-safe as Stack-memory because data stored in Heap-memory are visible to all threads.
- The size of the Heap-memory is quite larger as compared to the Stack-memory.
- Heap memory is accessible or exists as long as the whole application(or java program) runs.

CPP

`int main() {    // This memory for 10 integers    // is allocated on heap.    int *ptr  = new int[10]; }`

****Intermixed example of both kinds of memory allocation Heap and Stack in java:****

C++JavaJavascript

`#include <iostream> using namespace std;  int main() {      int a = 10; // stored in stack     int* p = new int(); // allocate memory in heap     *p = 10;     delete (p);     p = new int[4]; // array in heap allocation     delete[] p;     p = NULL; // free heap     return 0; }`

****Following are the conclusions on which we’ll make after analyzing the above example:****

- As we start execution of the have program, all the run-time classes are stored in the Heap-memory space.
- Then we find the main() method in the next line which is stored in the stack along with all its primitive(or local) and the reference variable Emp of type Emp_detail will also be stored in the Stack and will point out to the corresponding object stored in Heap memory.
- Then the next line will call to the parameterized constructor Emp(int, String) from main( ) and it’ll also allocate to the top of the same stack memory block. This will store:
    - The object reference of the invoked object of the stack memory.
    - The primitive value([primitive data type](https://www.geeksforgeeks.org/data-types-in-java/)) int id in the stack memory.
    - The reference variable of the String emp_name argument will point to the actual string from the string pool into the heap memory.
- Then the main method will again call to the Emp_detail() static method, for which allocation will be made in stack memory block on top of the previous memory block.
- So, for the newly created object Emp of type Emp_detail and all instance variables will be stored in heap memory.

****Pictorial representation as shown in Figure.1 below:****

![](https://media.geeksforgeeks.org/wp-content/uploads/20201210222125/Untitled4-660x361.png)

Fig.1

****Key Differences Between Stack and Heap Allocations****   
 
1. In a stack, the allocation and de-allocation are automatically done by the compiler whereas, in heap, it needs to be done by the programmer manually.
2. Handling the Heap frame is costlier than handling the stack frame.
3. Memory shortage problem is more likely to happen in stack whereas the main issue in heap memory is fragmentation.
4. Stack frame access is easier than the heap frame as the stack has a small region of memory and is cache-friendly but in the case of heap frames which are dispersed throughout the memory so it causes more cache misses.
5. A stack is not flexible, the memory size allotted cannot be changed whereas a heap is flexible, and the allotted memory can be altered.
6. Accessing the time of heap takes is more than a stack.

****Comparison Chart****

|Parameter|STACK|HEAP|
|---|---|---|
|Basic|Memory is allocated in a contiguous block.|Memory is allocated in any random order.|
|Allocation and De-allocation|Automatic by compiler instructions.|Manual by the programmer.|
|Cost|Less|More|
|Implementation|Easy|Hard|
|Access time|Faster|Slower|
|Main Issue|Shortage of memory|Memory fragmentation|
|Locality of reference|Excellent|Adequate|
|Safety|Thread safe, data stored can only be accessed by the owner|Not Thread safe, data stored visible to all threads|
|Flexibility|Fixed-size|Resizing is possible|
|Data type structure|Linear|Hierarchical|
|Preferred|Static memory allocation is preferred in an array.|Heap memory allocation is preferred in the linked list.|
|Size|Small than heap memory.|Larger than stack memory.|
___
Rust does have pointers, but they are not used in the same way as they are in languages like C or C++. In Rust, pointers are used to represent references to data that is stored on the heap, rather than data that is stored on the stack. This means that Rust's pointers are not as powerful as C or C++ pointers, but they are also less prone to errors and bugs.Rust also has a concept called "borrowing" which allows you to temporarily use a reference to a value without taking ownership of it. This allows for safe and efficient use of resources without the need for pointers.Rust also has a strong focus on memory safety, with features like ownership and borrowing that help prevent common errors like null pointer dereferences, data races, and buffer overflows.Additionally, Rust has a built-in garbage collector that automatically manages memory and avoids memory leaks.So while Rust does have pointers, they are not used in the same way as in other languages and Rust's focus on memory safety and borrowing system makes it less prone to errors and bugs.