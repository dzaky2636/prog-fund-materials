# Remedial Mission: Pointers and Array Drill

Hello Cadet, M.E.C.H.A. here. The data signals in the last mission got a bit corrupted. `Arrays` and `Pointers` are the two most complex concepts in C, so it's natural that we need a review.

Let's focus on two things:
1. How to access data in **Arrays** (Data Collections).
2. The two **Pointer** operators (`&` and `*`).

## 1. Array Review

An array is a "data cabinet." The key is **Zero-Based Indexing**.

If you have an array of size 4: `int scores[4] = {10, 20, 30, 40};`
* `scores[0]` is `10` (First element)
* `scores[1]` is `20`
* `scores[2]` is `30`
* `scores[3]` is `40` (Last element)
* `scores[4]` is **OUT OF BOUNDS!** (This will cause a *bug*!)

### Array Declaration and Initialization

```c
// Method 1: Declare then assign
int values[5];
values[0] = 100;
values[1] = 200;
// ... etc

// Method 2: Initialize with list
int numbers[5] = {37, 19, 85, 46, 93};

// Method 3: Initialize all to zero
int zeros[100] = {0};

// Method 4: Size determined by initializer
int data[] = {10, 20, 30}; // Creates array of size 3
```

### Accessing Arrays with Loops

The most common way to work with arrays:

```c
int scores[5] = {100, 85, 92, 78, 88};

// Print all elements
for (int i = 0; i < 5; i++) {
    printf("Score %d: %d\n", i+1, scores[i]);
}
```

## 2. Pointer Review (Two Key Operators)

A pointer is a variable that stores a **memory address**.

* **The `&` Operator (Ampersand): "Address of..."**
    * Used to **get the address** of a variable.
    * `&x` means "Give me the memory address of `x`".

* **The `*` Operator (Asterisk): "Value at..."**
    * Used to **get the value** at an address.
    * `*p` means "Give me the value at the address stored by pointer `p`".

### Combined Example:
```c
// 1. Regular variable (House)
int x = 50;

// 2. Pointer variable (Address note)
int *pX;

// 3. Store address of 'x' into 'pX'
pX = &x; 

// 4. Accessing values
// *pX is the same as x
printf("Value of x is %d\n", *pX); // Output: 50

// 5. Modifying through pointer
*pX = 75;
printf("Value of x is now %d\n", x); // Output: 75
```

### Pointer Data Types

The pointer type must match the variable type:

```c
int number = 10;
int *numberPtr = &number;        // Correct

float price = 25.50;
float *pricePtr = &price;        // Correct

char letter = 'A';
char *letterPtr = &letter;       // Correct
```

### Common Pointer Mistakes to Avoid

```c
int *ptr;           // Uninitialized pointer - DANGEROUS!
*ptr = 10;          // ERROR: Writing to unknown location

// Correct way:
int value = 0;
int *ptr = &value;  // Initialize pointer first
*ptr = 10;          // Now safe to use
```

Let's make sure both concepts are solid!
## QUIZ

**Q1:** You have array `int score[3] = {100, 200, 300};`. How do you access the value 200?
A. `score[2]`
B. `score[200]`
C. `score[1]`
D. `score[0]`

**Answer:** C (Explanation: Index starts from 0. `score[0]` is 100, `score[1]` is 200.)

**Q2:** If you have array `char letters[4];`, what is the index of the last valid element?
A. 4
B. 5
C. NULL
D. 3

**Answer:** D (Explanation: Array of size 4 has indices 0, 1, 2, and 3.)

**Q3:** Which C operator is used to get the memory address of a variable?
A. `*`
B. `&`
C. `->`
D. `.`

**Answer:** B

**Q4:** Which C operator is used to access the value at the address pointed to by a pointer?
A. `*`
B. `&`
C. `->`
D. `.`

**Answer:** A

**Q5:** Consider the following C code:
```c
int main() {
    int number = 10;
    int *pNumber = &number;
    
    printf("%d", *pNumber);
    return 0;
}
```
What is the output of this program?
A. Memory address of number
B. 10
C. 0
D. Error

**Answer:** B (Explanation: `pNumber` stores the address of `number`. `*pNumber` gets the value at that address, which is 10.)

**Q6:** What does this code print?
```c
int main() {
    int values[4] = {5, 15, 25, 35};
    printf("%d", values[2]);
    return 0;
}
```
A. 15
B. 25
C. 35
D. Error

**Answer:** B (Explanation: `values[2]` is the third element, which is 25.)

**Q7:** Consider this code:
```c
void doubleValue(int *num) {
    *num = *num * 2;
}

int main() {
    int x = 7;
    doubleValue(&x);
    printf("%d", x);
    return 0;
}
```
What is the output?
A. 7
B. 14
C. Memory address
D. Error

**Answer:** B (Explanation: The function receives the address of `x` and doubles the value at that address.)

**Q8:** Which array initialization is correct for creating an array of 5 integers?
A. `int arr[5] = {1, 2, 3, 4, 5};`
B. `int arr[] = {1, 2, 3, 4, 5};`
C. `int arr[5] = {0};`
D. All of the above

**Answer:** D (Explanation: All three methods are valid ways to initialize an integer array.)

## CODING DRILL

Write a C program that:
1. Creates an integer array of size 6 with values: `{12, 24, 36, 48, 60, 72}`
2. Uses a pointer to traverse the array
3. Prints each element using pointer arithmetic (not array indexing)
4. Calculates and prints the sum of all elements

**Expected Output:**
```
Element 0: 12
Element 1: 24
Element 2: 36
Element 3: 48
Element 4: 60
Element 5: 72
Sum: 252
```

### Code Template
```c
#include <stdio.h>

int main() {
    int numbers[6] = {12, 24, 36, 48, 60, 72};
    int *ptr = numbers;  // Point to first element
    int sum = 0;
    
    // Print elements using pointer arithmetic
    
    printf("Sum: %d\n", sum);
    
    return 0;
}
```

### Test Case
```json
[
  { 
    "input": "", 
    "output": "Element 0: 12\nElement 1: 24\nElement 2: 36\nElement 3: 48\nElement 4: 60\nElement 5: 72\nSum: 252\n" 
  }
]
```