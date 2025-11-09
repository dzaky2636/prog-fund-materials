# Remedial Mission: C-Language Function Basics

Hello Cadet, M.E.C.H.A. here. Our data transfer to *sub-routines* in the last mission failed. It seems there's a basic connection issue when we try to call functions.

Don't worry. Let's review the most basic protocol for creating and calling a function. We'll ignore the complex parameters and *return values* for now, and focus on the basic calling flow.

## Main Focus: 3 Steps to Call a Function

To create a function in C, you need three parts: **Prototype**, **Definition**, and **Call**.

### 1. Prototype (Declaration)

* **What is it?** A declaration at the *top* of your program (below `#include <stdio.h>`).
* **Purpose?** To tell `main()` that "Hey, a function with this name exists, don't worry if you haven't seen its code yet."

```c
#include <stdio.h>

// 1. PROTOTYPE
void printWarning(void);

int main() {
    // ...
}
```

- `void`: Return type (means this function returns no value).
- `printWarning`: Our function name.
- `(void)`: Parameter list (means this function takes no input).

### 2. Definition

- **What is it?** This is the _actual_ code block containing the function's instructions.
- **Location?** Usually placed _after_ the closing brace of `main()`.

```c
// (main() is above here)

// 2. FUNCTION DEFINITION
void printWarning(void) {
    printf("WARNING: Reactor temperature too high!\n");
}
```

### 3. Call (Function Call)

- **What is it?** This is the command we write _inside_ `main()` to execute that function.
- **How?** Simply write the function name followed by `()` and semicolon `;`.

```c
int main() {
    printf("Starting system check...\n");
    
    // 3. CALLING THE FUNCTION
    printWarning();
    
    printf("Check complete.\n");
    return 0;
}
```

### Complete Result

When combined, the program will look like this:

```c
#include <stdio.h>

// 1. Prototype
void printWarning(void);

int main() {
    printf("Starting system check...\n");
    
    // 3. Call
    printWarning();
    
    printf("Check complete.\n");
    return 0;
}

// 2. Definition
void printWarning(void) {
    printf("WARNING: Reactor temperature too high!\n");
}
```

**Output:**
```
Starting system check...
WARNING: Reactor temperature too high!
Check complete.
```

That's it! Those are the absolute basics of how functions work. Let's test it.

## QUIZ

**Q1**: What is the purpose of a "Function Prototype" (e.g., void print(void);) at the top of the program?
A. To run the main program logic.
B. To tell the compiler that a function with that name exists, before the compiler finds its definition.
C. To store the return value from the function.
D. To print messages to the screen.
**Answer**: B

**Q2**: Where is the "Function Definition" (the actual content/logic of the function) usually placed?
A. Inside main(), before return 0;.
B. In a separate file that is never included.
C. Above #include <stdio.h>.
D. Outside main(), usually after main() ends.
**Answer**: D

**Q3**: What does void mean in the declaration void printMessage(void)?
A. The first void means this function accepts any data type, the second void means it returns any type.
B. The first void means this function returns no value, the second void means this function takes no parameters.
C. This function has an error and is invalid.
D. This function can only print text.
**Answer**: B

**Q4: Consider this code:**
```c
void greetCadet() {
    printf("Hello!");
}

int main() {
    // ???
    return 0;
}
```

What line of code should be written at // ??? to run the greetCadet function?
A. call greetCadet;
B. greetCadet();
C. run greetCadet(void);
D. int result = greetCadet();
**Answer**: B

**Q5: Look at the following code. What's wrong with it?**
```c
int main() {
    printMessage(); // Calling function
    return 0;
}

// Definition placed below main()
void printMessage(void) {
    printf("Hello");
}
```
A. Nothing's wrong, this code will run perfectly.
B. The printMessage function should be inside main().
C. printf won't work inside printMessage.
D. This code will fail to compile because there's no Function Prototype above main().
**Answer**: D

## Coding Challenge

### Problem Description
Create a simple C program that demonstrates the three-step function process.

1. Create a function named `displayStatus` that takes no parameters and returns nothing.
2. This function should print "System Status: Online" when called.
3. In `main()`, print "Initializing...", then call your function, then print "Initialization complete."

**Expected Output:**
```
Initializing...
System Status: Online
Initialization complete.
```

### Code Template
```c
#include <stdio.h>

// 1. Write the function prototype here

int main() {
    printf("Initializing...\n");
    
    // 2. Call the function here
    
    printf("Initialization complete.\n");
    return 0;
}

// 3. Write the function definition here
void displayStatus(void) {
    // Code here
}
```

### Test Cases
```json
[
  { "input": "", "output": "Initializing...\nSystem Status: Online\nInitialization complete.\n" }
]
```