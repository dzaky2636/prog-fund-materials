# Remedial Mission: C-Language IF/ELSE Drill

Hello Cadet, M.E.C.H.A. here. Our `if-else` logic from the last mission seems to be experiencing some interference. Don't worry, we just need to recalibrate the basics.

Let's focus **only** on the simplest `if-else` structure. This is binary choice: "IF A is true, do B, OTHERWISE, do C."

## Syntax Review

The simple `if-else` structure in C looks like this:

```c
#include <stdio.h>

int main() {
    int number = 10;

    if (number > 5) {
        // This block executes if the condition (number > 5)
        // evaluates to TRUE
        printf("Number is greater than 5.");
        
    } else {
        // This block executes if the condition
        // evaluates to FALSE
        printf("Number is 5 or smaller.");
    }
    
    return 0;
}
```

Remember, **only one** of the two blocks (`if` or `else`) will ever execute. Never both.

## Key Concepts for C Selection

**Conditions in C:**
- In C, `0` means **False**
- Any **non-zero number** (including negative numbers) means **True**
- We use comparison operators (like `number > 10`, `age == 18`) to produce `true` (1) or `false` (0) values

**Sequential Flow vs Selection:**
- **Sequential flow**: Uses compound statements with `{` and `}` where all statements execute in order
- **Selection flow**: Uses `if-else` where only ONE branch executes based on the condition

Let's try this short drill!
## QUIZ

**Q1: Look at this C code:**
```c
int x = 3;
if (x == 3) {
    printf("A");
} else {
    printf("B");
}
```
What is the output of this code?
A. A
B. B
C. AB
D. Error
**Answer: A**

**Q2: Look at this C code:**
```c
int grade = 50;
if (grade >= 60) {
    printf("Passed");
} else {
    printf("Failed");
}
```
What is the output of this code?
A. Passed
B. Failed
C. 50
D. Error
**Answer: B**

**Q3: Look at this C code:**
```c
int temperature = 90;
if (temperature > 100) {
    printf("Boiling");
} else {
    printf("Not boiling");
}
```
What is the output of this code?
A. Boiling
B. Not boiling
C. 90
D. Error
**Answer: B**

**Q4: What does this code print when input is 80?**
```c
int noise;
scanf("%d", &noise);
if (noise <= 50) printf("Quiet\n");
if (noise <= 70) printf("Intrusive\n");
if (noise <= 90) printf("Annoying\n");
if (noise <= 110) printf("Very Annoying\n");
else printf("Uncomfortable\n");
```
A. Annoying
B. Very Annoying
C. Annoying and Very Annoying
D. Quiet, Intrusive, Annoying, and Very Annoying
**Answer: C** (Explanation: Each `if` is independent, not `else if`. So noise=80 satisfies both <= 90 and <= 110 conditions.)

---

### Coding Challenge

Let's try a simple live coding exercise. Create a C program that asks the user to input their age.
- If the age is **17 or more**, print "May enter"
- If not, print "May not enter"

**Sample Input/Output:**
```
Enter your age: 20
May enter
```

```
Enter your age: 15
May not enter
```

### Code Template
```c
#include <stdio.h>

int main() {
    int age;

    printf("Enter your age: ");
    scanf("%d", &age);

    // Write your simple IF-ELSE logic here

    return 0;
}
```

### Test Cases
```JSON
[
  { "input": "20", "output": "Enter your age: May enter" },
  { "input": "15", "output": "Enter your age: May not enter" },
  { "input": "17", "output": "Enter your age: May enter" }
]
```