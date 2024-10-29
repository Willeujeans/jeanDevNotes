# Pseudocode
*a non specific language used in describing algorithms*
## Structured Pseudocode
```
SET move_count to 1
FOR each row on the Board
	FOR each column on the Board
		IF Player position (row, column) is occupied THEN
			CALL find_adjacent_tiles with row, column
			INCREMENT move_count
		ENDIF
	ENDFOR
ENDFOR
```

```
Input: READ, OBTAIN, GET
output: PRINT, DISPLAY, SHOW
Compute: COMPUTE, CALCULATE, DETERMINE
Initialize: SET, INIT
Add: INCREMENT, BUMP
Subtract: DECREMENT
```


SEQUENCE
	represents linear tasks sequentially performed one after the other.

```
WHILE condition
sequence
ENDWHILE

```

```
REPEAT
sequence
UNTIL condition
```

```
FOR iteration bounds
sequence
ENDFOR
```

```
IF condition THEN
	sequence 1
ELSE
	sequence 2
ENDIF
```

```
CASE expression OF
condition 1: sequence 1
condition 2: sequence 2
condition n: sequence n
OTHERS:
default sequence
ENDCASE
```

## LATEX Pseudocode
arrayMax(in_array, n):
  **Input**: An array 'in_array' storing n >= 1 integers.
  **Output**: The maximum element in 'in_array'

  *currentMax* $\leftarrow$ in_array[0]
  **for** i $\leftarrow$ 1 **to** n - 1 **do**
    **if** *currentMax* < in_array[i] **then**
      *currentMax* $\leftarrow$ A[i]
  **return** *currentMax*
## Informal Pseudocode
```code
function heapSort(array):
    n = length(array)

    // Build a max heap
    for i from n/2 - 1 down to 0:
        heapify(array, n, i)

    // One by one extract elements from heap
    for i from n - 1 down to 1:
        // Move current root to end
        swap(array[0], array[i])
        
        // Call max heapify on the reduced heap
        heapify(array, i, 0)

function heapify(array, n, i):
    largest = i  // Initialize largest as root
    left = 2 * i + 1  // left = 2*i + 1
    right = 2 * i + 2 // right = 2*i + 2

    // If left child is larger than root
    if left < n and array[left] > array[largest]:
        largest = left

    // If right child is larger than largest so far
    if right < n and array[right] > array[largest]:
        largest = right

    // If largest is not root
    if largest != i:
        swap(array[i], array[largest])

        // Recursively heapify the affected subtree
        heapify(array, n, largest)
```