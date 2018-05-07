# Memory Management


## C# 
For the majority of the objects that your app creates, you can rely on .NET's garbage collector to handle memory management. 

The Microsoft .NET common language runtime requires that all resources be allocated from the managed heap. Objects are automatically freed when they are no longer needed by the application.

When a process is initialized, the runtime reserves a contiguous region of address space that initially has no storage allocated for it. This address space region is the managed heap. The heap also maintains a pointer. This pointer indicates where the next object is to be allocated within the heap. Initially, the pointer is set to the base address of the reserved address space region.

An application creates an object using the new operator. This operator first ensures that the bytes required by the new object fit in the reserved region (committing storage if necessary). If the object fits, then the pointer points to the object in the heap, this object's constructor is called, and the new operator returns the address of the object.

### Reference Counting
Reference counting is the idea that an object needs to be maintained when the count of that object is greater than 0.

### Garbage Collection
The garbage collector checks to see if there are any objects in the heap that are no longer being used by the application. If such objects exist, then the memory used by these objects can be reclaimed. (If no more memory is available for the heap, then the new operator throws an OutOfMemoryException.)

In the common language runtime, the managed heap always knows the actual type of an object, and the metadata information is used to determine which members of an object refer to other objects.

### Automatic reference counting?
Not used in C# (it uses Garbage Collection) - an e-mail from Brian Harry explains why:

> “We initially started with the assumption that the solution would take the form of automatic ref counting (so the programmer couldn't forget) plus some other stuff to detect and handle cycles automatically. ...we ultimately concluded that this was not going to work in the general case.
...
 In summary:
We feel that it is very important to solve the cycle problem without forcing programmers to understand, track down and design around these complex data structure problems.
We want to make sure we have a high performance (both speed and working set) system and our analysis shows that using reference counting for every single object in the system will not allow us to achieve this goal.
For a variety of reasons, including composition and casting issues, there is no simple transparent solution to having just those objects that need it be ref counted.
We chose not to select a solution that provides deterministic finalization for a single language/context because it inhibits interop with other languages and causes bifurcation of class libraries by creating language specific versions.
