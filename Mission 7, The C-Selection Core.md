# Mission 7: The C-Selection Core

Cadet, our system can now move straight (`Sequence`), perform loops (`Repetition`), and call modules (`Modular`). Now it's time to make it **intelligent**. This mission is about giving our program a "brain" to make decisions.

We will implement **Selection Control Structures** (which we learned in Sector 1) using C language syntax. This is the core of "smart" programs.

## 1. Control Structures Overview

Control structures organize instructions into three types to control execution flow:
- **Sequence**: Instructions execute one after another
- **Selection**: Program chooses among alternative statements by testing conditions
- **Repetition**: Instructions repeat based on conditions

A **condition** in C is an expression that evaluates to either false (0) or true (non-zero, usually 1).

---

## 2. The `if` Statement

The `if` statement is the direct implementation of the diamond-shaped flowchart symbol. It tests a condition and executes a block of code only when the condition is true.

### A. Single Alternative (`if` only)
Executes only when the condition is true.

```c
if (condition) {
    statementT;
}
```

**Example:**
```c
int grade = 85;
if (grade >= 55) {
    printf("Passed\n");
}
// Output: Passed
```

### B. Two Alternatives (`if-else`)
Selects one of two alternatives based on the condition.

```c
if (condition) {
    statementT;  // Executed if condition is true
} else {
    statementF;  // Executed if condition is false
}
```

**Example:**
```c
int grade = 45;
if (grade >= 55) {
    printf("Passed\n");
} else {
    printf("Failed\n");
    printf("You must take this course again\n");
}
// Output: Failed
//         You must take this course again
```

### C. Multiple Alternatives (`if-else if-else`)
Tests multiple conditions sequentially. This is cleaner than deeply nested if statements.

```c
if (condition1) {
    statement1;
} else if (condition2) {
    statement2;
} else if (condition3) {
    statement3;
} else {
    statementE;
}
```

**Example:**
```c
int systolicBloodPressure = 110;

if (systolicBloodPressure > 140) {
    printf("Hypertension\n");
} else if (systolicBloodPressure > 120) {
    printf("Pre-hypertension\n");
} else if (systolicBloodPressure > 90) {
    printf("Normal\n");
} else {
    printf("Hypotension\n");
}
// Output: Normal
```

---

## 3. Nested `if` Statements

An `if` statement with another `if` statement as its true task or false task. This allows for complex decision-making logic.

```c
if (condition1) {
    if (condition2) {
        statement1;
    } else {
        statement2;
    }
} else {
    if (condition3) {
        statement3;
    } else {
        statement4;
    }
}
```

---

## 4. The `switch` Statement

The `switch` statement provides a cleaner alternative to long `if-else if` chains, especially when comparing a single variable against multiple constant values.

**Important rules:**
- Only works with `int` and `char` data types
- Cannot use `string` or `double` values
- Each `case` must be a constant value
- **Always use `break`** to prevent fall-through behavior

```c
switch (expression) {
    case label1: 
        statement1;
        break;
    case label2: 
        statement2;
        break;
    case label3: 
        statement3;
        break;
    default: 
        statementD;
        break;
}
```

**Example:**
```c
char ship = 'C';

switch (ship) {
    case 'B': 
        printf("Battleship\n");
        break;
    case 'C': 
        printf("Cruiser\n");
        break;
    case 'D': 
        printf("Destroyer\n");
        break;
    default: 
        printf("Unknown\n");
        break;
}
// Output: Cruiser
```

**Critical Note about `break`:** Without `break`, execution "falls through" to the next case, which usually causes bugs!

You now have all the tools to create programs that can intelligently respond to different inputs. Time to test your new logic circuits!

## QUIZ

**Q1: What is the function of `else` in an if-else statement?**
A. To execute when the if condition is true
B. To execute when the if condition is false  
C. To repeat the if block
D. To end the program
**Answer: B**

**Q2: Look at this C code:**
```c
int x = 5;
if (x > 10) {
    printf("A");
} else {
    printf("B");
}
```
What is the output of this code?
A. A
B. B
C. AB
D. No output
**Answer: B**

**Q3: What is the correct operator in C for "equals to"?**
A. =
B. !=
C. ==
D. equals
**Answer: C**

**Q4: What is the function of the `break;` statement inside a switch structure?**
A. To stop the program completely
B. To indicate that the case condition is wrong
C. To repeat that case
D. To prevent "fall-through" execution to the next case
**Answer: D**

**Q5: (Logic Challenge) Look at this C code:**
```c
int score = 85;
if (score >= 80) {
    printf("B");
} else if (score >= 70) {
    printf("C");
}
```
What is the output of this code?
A. B
B. C
C. BC
D. No output
**Answer: A** (Explanation: Once the condition score >= 80 is met (True), its block executes and the entire remaining else-if chain is skipped.)

### Coding Challenge

Time to create your first selection program! Create a C program that asks the user to input an integer.
- If the number is **greater than 0**, print "Positive Number"
- If the number is **less than 0**, print "Negative Number"  
- If the number is **exactly 0**, print "Zero"

**Sample Input/Output:**
```
Enter a number: 7
Positive Number
```

```
Enter a number: -3
Negative Number
```

```
Enter a number: 0
Zero
```

### Code Template
```c
#include <stdio.h>

int main() {
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    // Write your IF-ELSE IF-ELSE logic here

    return 0;
}
```

### Test Cases
```JSON
[
  { "input": "7", "output": "Enter a number: Positive Number" },
  { "input": "-3", "output": "Enter a number: Negative Number" },
  { "input": "0", "output": "Enter a number: Zero" }
]
```