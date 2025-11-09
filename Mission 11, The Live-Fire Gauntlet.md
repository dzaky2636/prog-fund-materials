# Mission 11: The Live-Fire Gauntlet (Final Exam)

Cadet, M.E.C.H.A. here. You have successfully completed Sector 1 and Sector 2. You have transitioned from designing flowcharts on paper to writing functional C programs.

Now, you have arrived at "The Live-Fire Gauntlet".

This is your comprehensive final examination. This exam will test everything we've learned in our Programming Fundamentals course, covering five critical areas:

## Examination Coverage:
1. **Selection Control Structures**: `if`, `else if`, `else`, nested conditionals, `switch` statements, and multiple-alternative decisions
2. **Repetition Control Structures**: `for`, `while`, `do-while` loops, nested loops, `break` and `continue` statements  
3. **Functions**: C Standard Library functions, programmer-defined functions, function prototypes, definitions, call-by-value vs call-by-reference, recursion
4. **Pointers**: Memory addresses, address operator (`&`), indirection operator (`*`), pointer declaration, pointer arithmetic, call-by-pointer
5. **Array Access**: Array declaration, initialization, sequential access with loops, relationship between arrays and pointers

This examination consists of two parts: A Comprehensive Knowledge Quiz and one final Live Coding Challenge that will test your ability to integrate all these concepts.

This is your final exam, Cadet. Prove your mastery. See you on the other side.

---
## Comprehensive Knowledge Quiz

**Q1: What happens if you forget to add the ampersand (`&`) when using `scanf()` for an `int` (e.g., `scanf("%d", age);`)?**
A. The program will run normally.
B. The program will display `0`.
C. The program will crash or exhibit undefined behavior because it tries to write data to the wrong memory address.
D. The program will automatically print "Error".
**Answer: C**

**Q2: The `break;` statement is used inside `switch`. What is another use of `break;`?**
A. To terminate the `main()` function.
B. To forcefully exit from loops (`for`, `while`, `do-while`) immediately.
C. To skip the current loop iteration and continue to the next iteration.
D. To declare a new variable.
**Answer: B**

**Q3: Consider this C code:**
```c
int x = 5;
if (x = 10) { // Be careful!
    printf("Ten");
} else {
    printf("Five");
}
```
What is the output of this code?
A. Five
B. Ten
C. No output
D. Compilation error
**Answer: B** (Explanation: `x = 10` is an assignment operation (not a comparison `==`). This assignment succeeds and returns the value 10. Since 10 is not 0, the if condition is considered true.)

**Q4: Which for loop will print "5 4 3"?**
A. `for (int i = 5; i > 3; i--) { printf("%d ", i); }`
B. `for (int i = 5; i >= 3; i--) { printf("%d ", i); }`
C. `for (int i = 3; i <= 5; i++) { printf("%d ", i); }`
D. `for (int i = 0; i < 3; i++) { printf("%d ", i); }`
**Answer: B**

**Q5: Consider this C code:**
```c
void modify(int x) {
    x = 100;
}
int main() {
    int y = 10;
    modify(y);
    printf("%d", y);
    return 0;
}
```
What is the output of this program?
A. 10
B. 100
C. 0
D. Error
**Answer: A** (Explanation: C uses call-by-value. The `modify` function only receives a copy of `y`. The original `y` in `main()` remains unchanged.)

**Q6: If you have an array `int scores[10];`, what is the index of the first element?**
A. `scores[1]`
B. `scores[0]`
C. `scores[10]`
D. `scores[first]`
**Answer: B**

**Q7: What operator do you use to get the memory address of a variable?**
A. `*`
B. `&`
C. `->`
D. `[]`
**Answer: B**

**Q8: Consider this C code:**
```c
int main() {
    int x = 50;
    int *pX = &x;
    *pX = 75;
    printf("%d", x);
    return 0;
}
```
What is the output of this program?
A. 50
B. 75
C. The memory address of x
D. Error
**Answer: B**

**Q9: The `continue;` statement is used inside loops. What does it do?**
A. Exit from the loop completely.
B. Delete all variables inside the loop.
C. Skip the remaining code in the current iteration and jump directly to the next iteration.
D. Stop the program.
**Answer: C**

**Q10: (Logic Challenge) Consider this C code:**
```c
int main() {
    int arr[3] = {10, 20, 30};
    int *p = arr;
    
    *(p + 2) = 50; // Pointer arithmetic
    
    printf("%d", arr[2]);
    return 0;
}
```
What is the output of this program?
A. 10
B. 20
C. 30
D. 50
**Answer: D** (Explanation: `p` points to `arr[0]`. `p + 2` points to the address of `arr[2]`. `*(p + 2) = 50` changes the value at address `arr[2]` to 50.)

---
## Final Live Coding Challenge

### Problem Description

**Final Challenge: Squadron Performance Analysis**
M.E.C.H.A. needs to analyze performance data from 5 pilots in your squadron. Create a C program that performs the following:

1. Prompt the user to input **5 performance scores** (integers).
2. Store all 5 values in an **array**.
3. **Modularization Requirement:** You **MUST** create and use three separate functions:
    - `int calculateSum(int arr[], int size)`: Receives an array and its size, returns the **total (sum)** of all elements.
    - `float calculateAverage(int sum, int size)`: Receives the total `sum` and `size`, returns the **average**.
    - `int findMax(int arr[], int size)`: Receives an array and its size, returns the **maximum (highest)** value in the array.
4. In `main()`, call all three functions and print the results to the screen.

**Sample Input/Output:**
```
--- Squadron Analysis ---
Enter score for Pilot 1: 10
Enter score for Pilot 2: 40
Enter score for Pilot 3: 20
Enter score for Pilot 4: 50
Enter score for Pilot 5: 30

--- Analysis Results ---
Total Performance: 150
Average Performance: 30.00
Highest Performance: 50
```
### Code Template
```c
#include <stdio.h>

// 1. Function Prototypes (Required)
int calculateSum(int arr[], int size);
float calculateAverage(int sum, int size);
int findMax(int arr[], int size);

int main() {
    int scores[5];
    int size = 5;
    int i, sum, max;
    float avg;

    printf("--- Squadron Analysis ---\n");
    for (i = 0; i < size; i++) {
        printf("Enter score for Pilot %d: ", i + 1);
        scanf("%d", &scores[i]);
    }

    // 2. Call your functions here
    sum = calculateSum(scores, size);
    avg = calculateAverage(sum, size);
    max = findMax(scores, size);

    // 3. Print results
    printf("\n--- Analysis Results ---\n");
    printf("Total Performance: %d\n", sum);
    printf("Average Performance: %.2f\n", avg); // %.2f for 2 decimal places
    printf("Highest Performance: %d\n", max);

    return 0;
}

// 4. Implementation of calculateSum Function
int calculateSum(int arr[], int size) {
    int total = 0;
    int i;
    // Use a for loop to sum all elements in arr[]
    
    return total;
}

// 5. Implementation of calculateAverage Function
float calculateAverage(int sum, int size) {
    // Be careful! 'sum' and 'size' are integers.
    // Use casting (float) so the result is decimal.
    return (float)sum / size;
}

// 6. Implementation of findMax Function
int findMax(int arr[], int size) {
    // Assume the first element is the largest
    int max = arr[0];
    int i;
    // Use a for loop to compare max with remaining elements
    // If any element > max, update max
    
    return max;
}
```
### Test Cases
```json
[
  { 
    "input": "10\n40\n20\n50\n30", 
    "output": "--- Squadron Analysis ---\nEnter score for Pilot 1: Enter score for Pilot 2: Enter score for Pilot 3: Enter score for Pilot 4: Enter score for Pilot 5: \n--- Analysis Results ---\nTotal Performance: 150\nAverage Performance: 30.00\nHighest Performance: 50\n" 
  },
  { 
    "input": "5\n1\n9\n3\n2", 
    "output": "--- Squadron Analysis ---\nEnter score for Pilot 1: Enter score for Pilot 2: Enter score for Pilot 3: Enter score for Pilot 4: Enter score for Pilot 5: \n--- Analysis Results ---\nTotal Performance: 20\nAverage Performance: 4.00\nHighest Performance: 9\n" 
  },
  { 
    "input": "100\n100\n100\n100\n100", 
    "output": "--- Squadron Analysis ---\nEnter score for Pilot 1: Enter score for Pilot 2: Enter score for Pilot 3: Enter score for Pilot 4: Enter score for Pilot 5: \n--- Analysis Results ---\nTotal Performance: 500\nAverage Performance: 100.00\nHighest Performance: 100\n" 
  }
]
```