# Mission 10: The Data Stream

Cadet, so far we've only worked with single variables—one "memory box" for one value (like `int level = 5`). But what if we need to store 100 level values for 100 cadets? Are we going to create 100 separate variables? Absolutely not.

Welcome to "The Data Stream." In this mission, we'll learn the two most powerful (and most feared) concepts in C: **Arrays** and **Pointers**. These are how C handles large amounts of data efficiently.

## 1. Arrays (Data Collections)

An **Array** is a collection of data items of the **same type** stored in **contiguous (sequential)** memory locations.

Think of this as a cabinet with many drawers arranged in a row, where each drawer stores the same type of item.

### Array Declaration

We declare arrays with `data_type variable_name[size];`

```c
// Create a "cabinet" named 'scores'
// that has 5 "drawers" to store integers
int scores[5]; 
```

### Accessing Array Elements (0-Based Indexing)

This is the most important rule: **Arrays in C start from index 0, not 1.**

- The first element is at index `[0]`
- The second element is at index `[1]`
- The last element in an array of size `5` is at index `[4]`

We can access elements using square brackets `[]`:

```c
int scores[5];

scores[0] = 10; // Fill the first element
scores[1] = 20;
scores[4] = 50; // Fill the last element

printf("First element is: %d\n", scores[0]); // Output: 10
printf("Second element is: %d\n", scores[1]); // Output: 20
```

### Array Initialization

Arrays can be initialized in several ways:

```c
// Method 1: Using an initializer list
int numbers[5] = {37, 19, 85, 46, 93};

// Method 2: Partial initialization (remaining elements become 0)
int values[100] = {0}; // All elements become 0

// Method 3: Size determined by initializer list
int data[] = {10, 20, 30, 40}; // Creates array of size 4
```

The most common way to work with arrays is using `for` loops:

```c
int scores[5] = {10, 20, 30, 40, 50}; // Quick initialization

for (int i = 0; i < 5; i++) {
    printf("Element %d is %d\n", i, scores[i]);
}
```

---

## 2. Pointers (Memory Address Variables)

Now for a deeper concept. A **Pointer** is a special variable type that **doesn't store values** but instead stores the **memory address** of another variable.

- **Analogy:** `int age = 25;` is a **house**.
- The house has an **address** (like `0x7FFF5FBFFB8C`).
- A **pointer** is a piece of paper containing the **written address** of that house.

### Two Key Pointer Operators

We use two special operators to work with pointers:

1. **The `&` Operator (Ampersand / "Address-of")**
   - Read as "address of"
   - Used to **get** the memory address of a variable

2. **The `*` Operator (Asterisk / "Dereference")**
   - Read as "value at address..."
   - Used to **access or modify the value** at the address pointed to by the pointer

### Pointer Variable Definition & Initialization

Pointers must be defined before they can be used:

```c
data_type *pointer_name;
```

Example:
```c
int *numberPtr; // numberPtr is a pointer to int
```

### Using Pointers

```c
// 1. Create a regular variable (house)
int age = 25;

// 2. Create a pointer variable (address note)
// The * here declares that 'pAge' is a pointer
int *pAge;

// 3. Store the address of 'age' in the pointer
// Use the & operator ("address of")
pAge = &age;

// --- Now we can access 'age' in two ways ---

// Normal way:
printf("Value (via variable): %d\n", age);     // Output: 25

// Pointer way:
// Use the * operator ("value at address...")
printf("Value (via pointer): %d\n", *pAge);   // Output: 25
```

"Why is this useful?" you might ask. Because we can **modify the original value** using pointers:

```c
*pAge = 30; // "Set value 30 at the address I'm holding"

printf("Original 'age' value now: %d\n", age); // Output: 30
```

### Call by Pointer

Pointers are essential for functions that need to modify variables from the calling function:

```c
void swap(int *x, int *y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}

int main() {
    int a = 25, b = 30;
    
    swap(&a, &b); // Pass addresses
    printf("a = %d, b = %d\n", a, b); // Output: a = 30, b = 25
    
    return 0;
}
```

---

## 3. The Close Relationship Between Arrays and Pointers

Here's the concept that ties everything together: **In C, an array name is a constant pointer to its first element.**

This means:
```c
int scores[10];
```

The variable `scores` (without `[]`) is functionally **the same as** `&scores[0]`.

This is why `scanf` for strings (which are `char` arrays) doesn't require `&`:

```c
char name[50];
scanf("%s", name); // 'name' is already a pointer!
```

We can also use **Pointer Arithmetic** to traverse arrays:
- `scores[0]` is the same as `*scores`
- `scores[1]` is the same as `*(scores + 1)`
- `scores[2]` is the same as `*(scores + 2)`
- ...and so on.

Understanding this is key to mastering C.
## QUIZ

**Q1:** Which syntax is correct for declaring an integer array named `scores` that can hold 10 values?
A. `int scores[10];`
B. `int scores[9];`
C. `int scores = 10;`
D. `array{int} scores[10];`

**Answer:** A

**Q2:** If you have array `int values[5] = {10, 20, 30, 40, 50};`, how do you access the last element (value 50)?
A. `values[5]`
B. `values[4]`
C. `values(5)`
D. `values[last]`

**Answer:** B (Explanation: Indices start from 0, so an array of size 5 has indices 0, 1, 2, 3, and 4.)

**Q3:** What operator is used to get the memory address of a variable?
A. `*` (Asterisk)
B. `&` (Ampersand)
C. `->` (Arrow)
D. `.` (Dot)

**Answer:** B

**Q4:** What operator is used to get the value stored at a memory address pointed to by a pointer?
A. `*` (Asterisk / Dereference)
B. `&` (Ampersand / Address-of)
C. `->` (Arrow)
D. `.` (Dot)

**Answer:** A

**Q5:** (Logic Challenge) Consider the following C code:
```c
void modifyValue(int *ptr) {
    *ptr = 100;
}

int main() {
    int x = 50;
    modifyValue(&x);
    printf("%d", x);
    return 0;
}
```

What is the output of this program?
A. 50
B. 100
C. Memory address of x
D. Error

**Answer:** B (Explanation: The function receives the address of x and modifies the value at that address directly.)

---

## CODING CHALLENGE

Let's use `for` loops to manipulate an array. Create a C program that does the following:

1. Has an integer array of size 5 pre-filled with values: `{2, 4, 6, 8, 10}`.
2. Use a `for` loop to traverse each element in the array.
3. Inside the loop, **multiply each element by 2**.
4. After the loop finishes, use a second `for` loop to **print** all new values in the array.

**Example Input/Output:**
```
(No input)

Output:
4
8
12
16
20
```

### Code Template
```c
#include <stdio.h>

int main() {
    int numbers[5] = {2, 4, 6, 8, 10};
    int size = 5;
    int i;

    // 1. First loop: Modify array
    // Traverse array from i=0 to i < size
    for (i = 0; i < size; i++) {
        // Multiply current element (numbers[i]) by 2
        // and store back to the same position
        numbers[i] = numbers[i] * 2;
    }

    // 2. Second loop: Print array
    // Traverse array again from i=0 to i < size
    for (i = 0; i < size; i++) {
        // Print current element (numbers[i])
        // followed by newline (\n)
        printf("%d\n", numbers[i]);
    }

    return 0;
}
```

### Test Case
```json
[
  { "input": "", "output": "4\n8\n12\n16\n20\n" }
]
```