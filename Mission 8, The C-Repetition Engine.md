# Mission 8: The C-Repetition Engine

Cadet, M.E.C.H.A. here. We've mastered program decision-making (`if`, `switch`). Now it's time to give our programs "stamina"—the ability to **repeat** tasks without rewriting the same code multiple times.

In Sector 1, we learned this as *looping*. In C, we'll activate the "Repetition Engine" using three main commands: `while`, `do-while`, and `for`.

## Repetition Fundamentals

A **loop** is a group of instructions the computer executes repeatedly while some loop repetition condition remains true. There are two main types of repetition:

- **Counter-controlled repetition** (definite): We know exactly how many times the loop will execute
- **Sentinel-controlled repetition** (indefinite): We don't know in advance how many times the loop will execute

## 1. `while` Loop (Pre-test)

The `while` loop is the most basic form of repetition. It's a *pre-test loop*, meaning it **checks the condition first** before executing the code block inside.

**Key Point:** If the initial condition is `false`, the code block inside `while` **will never execute** (runs 0 times).

**Syntax:**
```c
while (condition) {
    // This code block will repeat
    // AS LONG AS the condition is 'true'
}
```

**Example: Counting from 1 to 5**
```c
int i = 1;

while (i <= 5) {
    printf("%d\n", i);
    i = i + 1; // Update section (IMPORTANT!)
}
// Output:
// 1
// 2
// 3
// 4
// 5
```

---

## 2. `do-while` Loop (Post-test)

The `do-while` loop is similar to `while`, but has one crucial difference: it's a *post-test loop*. This means it **executes the code block first**, then checks the condition at the end.

**Key Point:** `do-while` **is guaranteed to run at least once**, even if the condition is false from the start. This is very useful for things like displaying menus or requesting input until valid.

**Syntax:**
```c
do {
    // This code block executes FIRST
    
} while (condition); // THEN check condition HERE
```

**Example: Input validation**
```c
int password;

do {
    printf("Enter password (1234): ");
    scanf("%d", &password);
} while (password != 1234);

printf("Access Granted!");
```

---

## 3. `for` Loop (Counter-Controlled)

The `for` loop is a clean and efficient way to execute **counter-controlled repetition**, where we know exactly how many times we want to repeat.

The `for` syntax combines 3 important parts of *looping* (Initialization, Condition, Update) into one line:

**Syntax:**
```c
for (initialization; condition; update) {
    // Loop body
}
```

**Example: Counting from 1 to 5 (the `for` way)**
```c
int i;

// 1. Initialization: i = 1
// 2. Condition: i <= 5
// 3. Update: i++ (same as i = i + 1)
for (i = 1; i <= 5; i++) {
    printf("%d\n", i);
}
// Output:
// 1
// 2
// 3
// 4
// 5
```

---

## 4. `break` and `continue` (Emergency Commands)

- **`break;`**: This command is used to **forcefully exit** from a loop immediately, even if the condition is still `true`.
- **`continue;`**: This command **skips the rest of the current iteration** and immediately jumps to the next iteration of the loop.

## 5. Nested Loops

**Nested loops** consist of an outer loop with one or more inner loops. Each time the outer loop repeats, the inner loops are re-entered, their control expressions are re-evaluated, and all required iterations are performed.

You are now ready to control repetition. Let's test it in the simulator!

## QUIZ

**Q1: What is the main difference between while loop and do-while loop?**
A. while is pre-test (checks first, can run 0 times), do-while is post-test (runs first, guaranteed to run at least once).
B. while is post-test (guaranteed to run once), do-while is pre-test (can run 0 times).
C. while uses if, do-while uses switch.
D. while is for numbers, do-while is for text.
**Answer: A**

**Q2: Consider the following C code:**
```c
int x = 10;
while (x < 10) {
    printf("Starcoder");
    x++;
}
```
What is the output of this code?
A. Starcoder
B. Starcoder (repeated 10 times)
C. Error
D. No output (Empty)
**Answer: D** (Explanation: This is a while loop (pre-test). The condition 10 < 10 is immediately false, so the loop body never executes.)

**Q3: Consider the following C code:**
```c
int x = 10;
do {
    printf("Starcoder");
    x++;
} while (x < 10);
```
What is the output of this code?
A. Starcoder
B. Starcoder (repeated 10 times)
C. Error
D. No output (Empty)
**Answer: A** (Explanation: This is a do-while loop (post-test). The do block executes once, x becomes 11. The condition 11 < 10 is checked and is false, so the loop stops.)

**Q4: Which for loop will print "1 2 3"?**
A. for (int i = 0; i <= 3; i++) { printf("%d ", i); }
B. for (int i = 1; i < 3; i++) { printf("%d ", i); }
C. for (int i = 1; i <= 3; i++) { printf("%d ", i); }
D. for (int i = 1; i > 3; i++) { printf("%d ", i); }
**Answer: C**

**Q5: You are inside a for loop. If a certain condition is met, you want to skip the rest of the code in that iteration and immediately continue to the next iteration. Which command do you use?**
A. break;
B. continue;
C. return;
D. skip;
**Answer: B**
## Coding

Time to activate the "Repetition Engine". Create a C program that asks the user to input an integer (N). Your program should then print all numbers **from 1 to N**, each on a new line.

Use a `for` loop for this challenge.

**Example Input/Output:**

```
Enter a number: 5

Output:
1
2
3
4
5
```

### Template Code

```c
#include <stdio.h>

int main() {
    int N;
    int i; // Variable for loop counter

    printf("Enter a number: ");
    scanf("%d", &N);

    printf("\nOutput:\n");

    // Create for loop here
    // Initialization: i = 1
    // Condition: i <= N
    // Update: i++

    return 0;
}
```

### Test Cases
```json
[
  { "input": "5", "output": "Enter a number: \nOutput:\n1\n2\n3\n4\n5\n" },
  { "input": "3", "output": "Enter a number: \nOutput:\n1\n2\n3\n" },
  { "input": "1", "output": "Enter a number: \nOutput:\n1\n" }
]
```