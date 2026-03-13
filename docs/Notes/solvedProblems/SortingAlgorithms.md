# Sorting Algorithms

## 1. Bubble Sort.
<details>
  <summary>Explanation!</summary>

```text
Bubble Sort is an algorithm which is used to sort a list of elements, for example elements in an array.
The algorithm compares two adjacent elements and then swaps them if they are not in order.
The process is repeated until no more swapping is needed.

For example:
Let's take the following array: [3, 1, 5, 2]
Step 1: [1, 3, 5, 2] - the first two elements are compared and swapped.
Step 2: [1, 3, 5, 2] - the next pair is compared and not swapped, as they are in order.
Step 3: [1, 3, 2, 5] - the last two elements are swapped.

This was the first iteration over the array. Now we need to start the second iteration:
Step 1: [1, 3, 2, 5]
Step 2: [1, 2, 3, 5]
Step 3: [1, 2, 3, 5]

The third iteration will not swap any elements, meaning that the list is sorted!

The main advantage of Bubble Sort is the simplicity of the algorithm. Also, it does not
require any additional storage space, as it operates in-place. In terms of complexity,
bubble sort is consideredto be not optimal, as it required multiple iterations over the
array. In the worst scenario, where all elements need to be swapped, it will require
(n-1)+(n-2)+(n-3)+...+3+2+1 = n(n-1)/2 swaps (n is the number of elements).
```
</details>

<details>
  <summary>Solution!</summary>



Using Array
```java title="Java"
public static void main(String[] args) {
    int[] arr = {3, 1, 5, 2};
    
    for (int i=0; i<arr.length; i++) {
        for (int j=0; j<arr.length; j++) {
            if (i != j && arr[i] < arr[j]) {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }
    
    System.out.println(Arrays.toString(arr));
}
```

Using List
```java title="Java"
public static void main(String[] args) {
    List<Integer> l1 = Arrays.asList(3, 1, 5, 2);
    
    for (int i=0; i<l1.size(); i++) {
        for (int j=0; j<l1.size(); j++) {
            if (i != j && l1.get(i) < l1.get(j)) {
                int temp = l1.get(i);
                l1.set(i, l1.get(j));
                l1.set(j, temp);
            }
        }
    }
    
    System.out.println(l1);
}
```


```javascript title="JavaScript"
let arr = [3, 1, 5, 2];
    
for (let i=0; i<arr.length; i++) {
    for (let j=0; j<arr.length; j++) {
        if (i != j && arr[i] < arr[j]) {
            [arr[i], arr[j]] = [arr[j], arr[i]];
        }
    }
}

console.log(arr.join(", "));
```


```python title="Python"
arr = [3, 1, 5, 2]
    
for i in range(0, len(arr)):
    for j in range(0, len(arr)):
        if i != j and arr[i] < arr[j]:
            arr[i], arr[j] = arr[j], arr[i];

print(arr)
```
</details>

## 2. Selection Sort.
<details>
  <summary>Explanation!</summary>

```text
Selection Sort is a simple sorting algorithm that finds the smallest element in the array and
swaps it with the element in the first position, then finds the second smallest element and
swaps it with the element in the second position, and continues in this way until the entire
array is sorted.

For example:
Let's take the following array: [3, 1, 5, 2]

Step 1: The smallest element is 1. We swap it with the first element.
Result: [1, 3, 5, 2]

Step 2: The second smallest is swapped with the second element.
Result: [1, 2, 5, 3]

Step 3: The third smallest is swapped with the third element.
Result: [1, 2, 3, 5]

The array is now sorted.
```
</details>

<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int[] arr = {3, 1, 5, 2};

    for (int i=0; i<arr.length-1; i++) {
        int minIndex = i;
        for (int j=i+1; j<arr.length; j++) {
            if (arr[j] < arr[minIndex])
                minIndex = j;
        }

        // swap
        int temp = arr[minIndex];
        arr[minIndex] = arr[i];
        arr[i] = temp;
    }

    System.out.println(Arrays.toString(arr));
}
```


```javascript title="JavaScript"
let arr = [3, 1, 5, 2];

for (let i=0; i<arr.length-1; i++) {
    let minIndex = i;
    for (let j=i+1; j<arr.length; j++) {
        if (arr[j] < arr[minIndex])
            minIndex = j;
    }
    
    // swap
    [arr[minIndex], arr[i]] = [arr[i], arr[minIndex]];
}

console.log(arr);
```


```python title="Python"
arr = [3, 1, 5, 2]

for i in range(0, len(arr)-1):
    minIndex = i
    for j in range(i+1, len(arr)):
        if (arr[j] < arr[minIndex]):
            minIndex = j

    # swap
    arr[minIndex], arr[i] = arr[i], arr[minIndex]

print(arr)
```
</details>

## 3. Insertion Sort.
<details>
  <summary>Explanation!</summary>

```text
Insertion Sort is a simple sorting algorithm that works the way we sort playing cards in our
hands. We sort the first two cards and then place the third card in the appropriate position
within the first two, and then the fourth is positioned within the first three, and so on until
the whole hand is sorted. During an iteration, an element of the list is inserted into the
sorted portion of the array to its left. So, basically, for each iteration, we have an array
of sorted elements to the left, and an array of other elements still to be sorted to the right.
Sounds confusing? Let's look at an example to better understand the algorithm.

Take the following array: [3, 1, 5, 2]
Step 1: We start with the second element (1) and properly position it in the "array" of the first two elements.
Result: [1, 3, 5, 2] - now we have a sorted array to the left ([1, 3]), and the other elements to the right.

Step 2: The next element is 5. Inserting it into the array to the left
result: [1, 3, 5, 2].

Step 3: The last element (2) is inserted into the corresponding position,
result: [1, 2, 3, 5]
```
</details>

<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int[] arr = {3, 1, 5, 2};
    
    for (int i=1; i<arr.length; i++) {
        int j = i;
        while (j>0 && arr[j] < arr[j-1]) {
            // swap
            arr[j-1] = arr[j] + arr[j-1] - (arr[j] = arr[j-1]);
            j--;
        }
    }

    System.out.println(Arrays.toString(arr));
}
```


```javascript title="JavaScript"
let arr = [3, 1, 5, 2];

for (let i=1; i<arr.length; i++) {
    let j=i;
    while (j>0 && arr[j] < arr[j-1]) {
	// swap
        [arr[j], arr[j-1]] = [arr[j-1], arr[j]];
        j--;
    }
}

console.log(arr);
```


```python title="Python"
arr = [3, 1, 5, 2]

for i in range(1, len(arr)):
    j=i
    while (j>0 and arr[j] < arr[j-1]):
	# swap
        arr[j], arr[j-1] = arr[j-1], arr[j]
        j = j-1

print(arr)
```
</details>

## 4. Merge Sort.

<details>
  <summary>Explanation!</summary>

```text
Merge Sort belongs to the category of Divide and Conquer algorithms.
These algorithms operate by breaking down large problems into smaller, more easily solvable problems.
The idea of the merge sort algorithm is to divide the array in half over and over again until each
piece is only one item long. Then those items are put back together (merged) in sort-order.

Let's have a look at an example:
We start by dividing the array:
[31, 4, 88, 1, 4, 2, 42]
[31, 4, 88, 1]  [4, 2, 42] //divided into 2 parts
[31, 4]  [88, 1]  [4, 2]  [42] //divided into 4 parts
[31]  [4]  [88]  [1]  [4]  [2]  [42] //single items

Now we need to merge them back together in sort-order:
First we merge single items into pairs. Each pair is merged in sort-order:
[4, 31]  [1, 88]  [2, 4]  [42]
Next we merge the pairs, again in sort order:
[1, 4, 31, 88]  [2, 4, 42]
And then we merge the final two groups:
[1, 2, 4, 4, 31, 42, 88]

Now the array is sorted! The idea behind the algorithm is that smaller parts are easier to sort.
The merge operation is the most important part of the algorithm.
```
</details>

<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int[] arr = {31, 4, 88, 1, 4, 2, 42};
    
    mergeSort(arr);
    Arrays.toString(arr);
}
```
```java title="Java"
public static void mergeSort(int[] arr) {
    if (arr.length < 2) {
        return; // Base case: an array of size 0 or 1 is already sorted
    }
    
    int mid = arr.length / 2; // Find the midpoint
    int[] left = new int[mid]; // Create left subarray
    int[] right = new int[arr.length - mid]; // Create right subarray
    
    // Fill left subarray
    for (int i = 0; i < mid; i++) {
        left[i] = arr[i];
    }
    
    // Fill right subarray
    for (int i = mid; i < arr.length; i++) {
        right[i - mid] = arr[i];
    }
    
    // Recursively sort both subarrays
    mergeSort(left);
    mergeSort(right);
    
    // Merge sorted subarrays
    merge(arr, left, right);
}
```
```java title="Java"
public static void merge(int[] arr, int[] left, int[] right) {
    int i = 0, j = 0, k = 0; // Initialize pointers
    
    // Merge elements back into the original array
    while (i < left.length && j < right.length) {
        if (left[i] <= right[j]) {
            arr[k++] = left[i++]; // Take from left
        } else {
            arr[k++] = right[j++]; // Take from right
        }
    }
    
    // Copy remaining elements from left subarray (if any)
    while (i < left.length) {
        arr[k++] = left[i++];
    }
    
    // Copy remaining elements from right subarray (if any)
    while (j < right.length) {
        arr[k++] = right[j++];
    }
}
```


```javascript title="JavaScript"

```


```python title="Python"

```
</details>

## 5. Quick Sort.

<details>
  <summary>Explanation!</summary>

```text
QuickSort is another algorithm from the Divide and Conquer category. 
It operates by breaking down large problems into smaller, more easily solvable problems. 

The idea of QuickSort is the following: a pivot element is picked. The versions of
QuickSort differ in the way of pivot picking. First, last, median, or even a randomly
selected element is a candidate to be picked as the pivot.

The primary part of the sort process is partitioning. Once the pivot is picked, the
array is partitioned into two halves - one half containing all the elements less than
the pivot and the other half containing the elements greater than the pivot. The equal
ones can remain either side. Then, the same process occurs to the remaining halves of
the array recursively, eventually resulting in a sorted array.


Consider the example:
 
Suppose we have the following sequence:
[ 2, 0, 7, 4, 3 ]
We choose 3 (last element) as the pivot. After doing 4 comparisons we get the two halves:
[ 2, 0 ] (3) [ 7, 4 ]
Now, the same process repeats for the two halves. We choose (0) as a pivot for the lesser
half, and (4) for the greater half. After a comparison for each half, we get:
[ (0) [2] ] (3) [ (4) [7] ]
Which is a sorted sequence.
 
 
Advantages / Disadvantages
 
QuickSort operates in-place, so it doesn't require extra storage.
The choice of the pivot makes a big difference, as an unsuccessful pivot selection
can decreases the algorithm's speed significantly.

A variation of QuickSort is the 3-way QuickSort - it divides the sequence into three
pieces: smaller, greater, and equal. This makes it more convenient for data with high
redundancy (repetitions).
 
```
</details>

<details>
  <summary>Solution!</summary>


```java title="Java"

```


```javascript title="JavaScript"

```


```python title="Python"

```
</details>
