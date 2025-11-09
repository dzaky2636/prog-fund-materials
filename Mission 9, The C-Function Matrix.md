# Mission 9: The C-Function Matrix

Cadet, M.E.C.H.A. here. Our programs can now make decisions (`if`) and perform repetition (`for`, `while`). However, our `main()` function is starting to look very crowded and complex.

Just like in Sector 1, it's time for **Modularization**. In C language, modules are called **Functions**.

## 1. What are Functions in C?

Functions are independent blocks of code that perform specific tasks. The `main()` function we've been using is actually a function—the main function that executes when the program starts.

We can create our own functions to organize our code. Remember the benefits?

* **Reusable**: Create a `calculateTax()` function once, call it 50 times.
* **Readable**: Your `main()` function will look clean, containing only function calls.
* **Maintainable**: If tax calculations change, you only need to fix one function.

---

## 2. Anatomy of a Function in C

Creating functions in C has three parts:

### A. Function Prototype (Function Declaration)

This is a declaration at the *top* of your file (below `#include`), which tells the *compiler* about functions you'll use later.

**Syntax:** `return_data_type function_name(parameter_data_type_1, parameter_data_type_2);`

```c
// Prototype for function that adds two numbers
int addNumbers(int a, int b);

// Prototype for function that only prints a message
void printMessage(void);
```

- `int addNumbers(...)`: This function will **return** an `int` value.
- `void printMessage(...)`: `void` means this function **returns no value**.
- `(...)`: This is the list of parameters (input) the function receives. `(void)` means no parameters.

### B. Function Definition

This is the actual code block containing the function's logic. Usually placed _after_ `main()`.

```c
// Definition of addNumbers function
int addNumbers(int a, int b) {
    int result = a + b;
    return result; // Returns the result value
}

// Definition of printMessage function
void printMessage(void) {
    printf("Hello, Cadet!\n");
    // No 'return' value
}
```

### C. Function Call

This is how we execute the function from within `main()` or from other functions.

```c
int main() {
    // Calling void function
    printMessage(); 
    
    // Calling function that returns a value
    int total = addNumbers(5, 3); // 5 is sent to 'a', 3 is sent to 'b'
    
    printf("The result is: %d\n", total); // Will print 8
    
    return 0;
}
```

---

## 3. Variable Scope: Local vs Global

- **Local Variables**: Variables declared **inside** a function (like `result` in `addNumbers`). These variables _only_ exist inside that function and are destroyed when the function ends. `main()` cannot see the `result` variable.

- **Global Variables**: Variables declared **outside** all functions (at the top). These variables can be seen and modified by _all_ functions. **Be careful!** Using global variables can make your program very hard to debug. The best practice is to use **parameters**.

## 4. Parameters: Call-by-Value (Very Important!)

In Sector 1, we learned about _Call-by-Value_ and _Call-by-Reference_.

**By _default_, C language always uses _Call-by-Value_ for all basic data types (int, float, char).**

This means when you call `addNumbers(5, 3)`, C makes **copies** of values 5 and 3. The `addNumbers` function works with these _copies_. (We'll discuss _Call-by-Reference_ using Pointers in the next mission!)

## 5. Standard Library Functions

C provides many built-in functions through standard libraries:

- `<stdio.h>`: Input/output functions like `printf()`, `scanf()`
- `<math.h>`: Mathematical functions like `sqrt()`, `pow()`
- `<string.h>`: String manipulation functions
- `<stdlib.h>`: Utility functions for memory allocation, random numbers

You are now ready to modularize your programs!

## QUIZ

**Q1**: What is the name of an independent code block in C that performs a specific task?
A. Module
B. Function
C. Parameter
D. Variable
**Answer**: B

**Q2**: What is the purpose of a "Function Prototype" (e.g., int add(int a, int b);)?
A. To tell the compiler about the name, return type, and parameters of a function before it's used.
B. To execute the code inside the function.
C. To stop function execution.
D. To store the return value from the function.
**Answer**: A

**Q3**: A function is declared as void printMenu(void). What does this mean?
A. This function returns an int value and takes one void parameter.
B. This function returns no value (void) and takes no parameters (void).
C. This function can return any data type.
D. This is an incorrect declaration.
**Answer**: B

**Q4**: What is meant by "Local Variables"?
A. Variables that can be accessed from any function.
B. Variables declared outside main().
C. Variables declared inside a function and can only be accessed within that function.
D. Variables that are always of int type.
**Answer**: C

**Q5: Consider this C code:**
```c
void changeValue(int x) {
    x = 100;
}

int main() {
    int y = 10;
    changeValue(y);
    printf("%d", y);
    return 0;
}
```
What is the output of this program?
A. 100
B. 10
C. 0
D. Error
**Answer**: B (Explanation: C uses Call-by-Value. The changeValue function receives a copy of y. It changes its copy to 100, but the original y in main() remains 10.)

---

## Coding Challenge

### Problem Description
Let's practice modularization. Create a C program that has a separate function to calculate the square of a number.

1. Create a function named `calculateSquare` that takes one `int` parameter.
2. This function must **return** an `int` value of that number multiplied by itself (squared).
3. In `main()`, ask the user to enter a number.
4. Call the `calculateSquare` function with that number.
5. Print the result returned by the function.

**Example Input/Output:**
```
Enter a number: 5
The square is: 25
```

```
Enter a number: 8
The square is: 64
```

### Code Template
```c
#include <stdio.h>

// 1. Create Function Prototype for calculateSquare here
// Return type: int
// Name: calculateSquare
// Parameter: int number
int calculateSquare(int number);

int main() {
    int input;
    int result;

    printf("Enter a number: ");
    scanf("%d", &input);

    // 2. Call calculateSquare function and store the result
    //    in the 'result' variable
    
    printf("The square is: %d\n", result);
    
    return 0;
}

// 3. Create Function Definition for calculateSquare here
//    This function must return (return) number * number
int calculateSquare(int number) {
    // Write your return logic here
    return number * number;
}
```

### Test Cases
```json
[
  { "input": "5", "output": "Enter a number: The square is: 25\n" },
  { "input": "8", "output": "Enter a number: The square is: 64\n" },
  { "input": "10", "output": "Enter a number: The square is: 100\n" }
]
```