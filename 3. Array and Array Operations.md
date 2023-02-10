## An array is a sequence of data that are numbered, the numbers are called index which is an integer, and they help with fast retrieval of data that is stored in an array.

## In most of the implementations of an array for e.g. in Java, C, C++, Python index of an array starts with a zero. 

## In implementation of one dimensional array in many languages mentioned above, the data is stored in contiguous memory location and arrays store identical/homogeneous data.

### An array is a random access structure, i.e. a type of data structure in which the time taken to access, insert or delete any data, no matter the size of the array, is always constant. 

## Two of the most basic operations that an array supports are Store and Retrieve. Store and retrieve both take constant time, i.e. both operations take the same time no matter the size of the array as we can calculate the address of an element of an array using a simple arithmetic operation which is the base address of the array plus the index of the array multiplied by the size of a single element. 

### Suppose the base address of an array is 1000, and we want to know the address of the element at index 4 and the size of each element is 2 bytes therefore the address of the element at 4th index will be:

### Base Address + (Index of the element x Size of the element ) = 1000 + (4 x 2) = 1008

## Array operations in Java

### Defining a new array:

``` java

int num[] = new int[5]; // This statement defines an integer array called 'num' of size 5

num[0]; // accesses the first element of the array num, the one we just created

num[1]; // accesses the 2nd element of the array num

num[i]; //accesses the ith element of the array num 

System.out.println(num[4]); //prints the last or 5th element of the array num

num[5]; // This statement will throw an arrayindexoutofbound error since our array only has 5 elemnts and this command is trying to retrieve the 6th element which is not present

num[-1]; // Note: You can also access the last element of an array even if you dont know the size by giving -1 as the index

// Similarly you can define an array of any type in Java by metioning the type while declaring it:

float newArray[] = new float[8]; // Defines a float array of size 8 called newArray

int emptyArray[]; // This statement declares an array without mentioning the size which will create a null reference to the array without allocating any memory

emptyArray = new int[10] // This will allocate memomry for 10 integers for the emptyArray we created

int numberArray[] = new int[10]

int numberArray1 = {1,2,3,4,5,6} // This will initialize the array we created in the previous statement with numbers 1 to 6 we mentioned inside the curly brackets {}

for(int i=0; i<numberArray1.length; i++); // This is a for loop that is iterating through the numberArray1 and numberArray.length is a function that is giving us the size of the array
   System.out.print(numberArray[i]) // This statement is printing the element in the numberArray1, combined with the for loop it will iterate through the array and prnnt all the numbers that are present in the array.

```

