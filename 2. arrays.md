## Data Structure - Array

Continous memory allocation of data, with O(1) space complexity to access any element with an index.

- Collection of data with somedata type
- Collection is sorted in contigous memory space.

### Access an element

In an array, to access an element, at an index 'i', is arr[i].

- when an array is defined, 'arr', address of the first element is store in the variable 'arr', which is generally known as base address
- On accessing the value at ith index, address is calculated by,
-   - address of the ith index = Base Address + i * dataSize
- After calculating the address of ith index, arr[i] dereferences the value at i.

## Dynamic Array

When an array size cannot be predicted, dynamic arrays are defined that internally has an abstraction which implements the functionality to increase the size of the array.


## Memory Fragementation

In an multiprocessor system, there can be different programs running, and in that situation if there is a need to create an array of some datatype elements. The space required to create the array should be in contigous nature, but due to other programs the processor can be able to provide contigous memory blocks to create the array. In that case LinkedLists can be help full to store the elements.

```quote
LinkedLists next topic