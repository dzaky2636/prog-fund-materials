# Remedial Mission: C-Language FOR Loop Drill
Hello Cadet, M.E.C.H.A. detected unexpected repetition in the last mission. Let's recalibrate our `Repetition Engine` and focus on the most efficient tool for counter-controlled repetition: **`for` loops**.
## Main Focus: `for` Loop

When you **know exactly** how many times to repeat (for example, 5 times, 10 times, or N times), the `for` loop is your best friend.

### Syntax Review

Remember, the `for` loop combines three important parts into one line:

1. **Initialization:** `int i = 1` (Creates our *counter*)
2. **Condition:** `i <= 5` (When the *loop* should continue)
3. **Update:** `i++` (What to do after each *loop* completes)

```c
// Syntax: for (initialization; condition; update)
for (int i = 1; i <= 5; i++) {
    // This code block will run 5 times
    printf("Iteration %d\n", i);
}

// Output:
// Iteration 1
// Iteration 2
// Iteration 3
// Iteration 4
// Iteration 5
```

Let's do a quick drill for this.
## QUIZ

**Q1: Consider the following C code:**
```c
for (int i = 0; i < 3; i++) {
    printf("A");
}
```
What is the output of this code?
A. A
B. AA
C. AAA
D. AAAA
**Answer: C** (Explanation: Loop runs for i=0, i=1, and i=2. Total 3 times.)

**Q2: You want to print the numbers "5 4 3 2 1". Which for loop is correct?**
A. for (int i = 5; i >= 1; i--)
B. for (int i = 1; i <= 5; i++)
C. for (int i = 5; i > 1; i--)
D. for (int i = 0; i < 5; i++)
**Answer: A**

**Q3: Consider the following C code:**
```c
for (int k = 1; k <= 3; k++) {
    // No content
}
printf("%d", k);
```
What is the output of this code?
A. 1
B. 3
C. 4
D. Error
**Answer: D** (Explanation: Variable k is declared inside the for loop (local scope), so it cannot be accessed by printf outside the loop.)

---

## Coding

Let's try a focused live coding drill. Create a C program that prints the word "Loading..." exactly 3 times, each on a new line. Use a `for` loop.

**Example Input/Output:**
```
(No input)

Output:
Loading...
Loading...
Loading...
```

### Template Code
```c
#include <stdio.h>

int main() {
    int i; // Variable for counter

    // Create for loop that runs 3 times
    // (for example, from i=0 to i < 3)
    for ( ) {
        // Print "Loading..." followed by newline '\n
    }

    return 0;
}
```

### Test Cases
```json
[
  { "input": "", "output": "Loading...\nLoading...\nLoading...\n" }
]
```