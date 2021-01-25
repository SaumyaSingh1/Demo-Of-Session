# Insetion Sort  

>**Insertion sort is a simple sorting algorithm that works similar to the way you sort playing cards in your hands.  
The array is virtually split into a sorted and an unsorted part. Values from the unsorted part are picked and placed   
at the correct position in the sorted part.**  

## Algorithm  

**To sort an array of size n in ascending order:**  
1. Iterate from arr[1] to arr[n] over the array.  
2. Compare the current element (key) to its predecessor.  
3. If the key element is smaller than its predecessor, compare it to the elements before. Move the greater elements   
one position up to make space for the swapped element.  

## Example  
![Example](https://media.geeksforgeeks.org/wp-content/uploads/insertionsort.png)  

## Another Example  

**12**, 11, 13, 5, 6

Let us loop for i = 1 (second element of the array) to 4 (last element of the array)

i = 1. Since 11 is smaller than 12, move 12 and insert 11 before 12
**11, 12**, 13, 5, 6

i = 2. 13 will remain at its position as all elements in A[0..I-1] are smaller than 13
**11, 12, 13,** 5, 6

i = 3. 5 will move to the beginning and all other elements from 11 to 13 will move one position ahead of their current position.
**5, 11, 12, 13,** 6

i = 4. 6 will move to position after 5, and elements from 11 to 13 will move one position ahead of their current position.
**5, 6, 11, 12, 13**

## Now Let's understand this sorting with a Code  

```cpp
// C++ program for insertion sort 
#include <bits/stdc++.h> 
using namespace std; 

/* Function to sort an array using insertion sort*/
void insertionSort(int arr[], int n) 
{ 
	int i, key, j; 
	for (i = 1; i < n; i++) 
	{ 
		key = arr[i]; 
		j = i - 1; 

		/* Move elements of arr[0..i-1], that are 
		greater than key, to one position ahead 
		of their current position */
		while (j >= 0 && arr[j] > key) 
		{ 
			arr[j + 1] = arr[j]; 
			j = j - 1; 
		} 
		arr[j + 1] = key; 
	} 
} 

// A utility function to print an array of size n 
void printArray(int arr[], int n) 
{ 
	int i; 
	for (i = 0; i < n; i++) 
		cout << arr[i] << " "; 
	cout << endl; 
} 

/* Driver code */
int main() 
{ 
	int arr[] = { 12, 11, 13, 5, 6 }; 
	int n = sizeof(arr) / sizeof(arr[0]); 

	insertionSort(arr, n); 
	printArray(arr, n); 

	return 0; 
} 

```

**Output**  
>**5 6 11 12 13** 

**Time Complexity**: O(n*2)  

**Auxiliary Space**: O(1)  

**Boundary Cases**: Insertion sort takes maximum time to sort if elements are sorted in reverse order. And it takes  
 minimum time (Order of n) when elements are already sorted.

**Algorithmic Paradigm**: Incremental Approach  

**Sorting In Place**: Yes  

**Stable**: Yes  

**Online**: Yes  

**Uses**: Insertion sort is used when number of elements is small. It can also be useful when input array is almost sorted,  
 only few elements are misplaced in complete big array.  