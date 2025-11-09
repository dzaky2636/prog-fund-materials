# Remedial Mission: C Syntax Primer
Hello Cadet, M.E.C.H.A. here. We detected some minor syntax anomalies in the last *live-fire* mission. This is normal! C language syntax is very strict, like military protocol.
Let's review the most fundamental rules in this Sector: **Variables**, **Semicolons**, **`printf()`**, **`scanf()`**, and **Comments**. Mastering these concepts is 90% of the battle.
## 1. Variables: Data Storage Boxes
A variable is a "location in memory" that we give a name to store data. When you create a variable, you must tell C what type of data it will store.
The most common basic data types are:
* `int`: For whole numbers (Example: `5`, `-10`).
* `float`: For decimal numbers (Example: `3.14`, `1.5`).
* `char`: For single characters (Example: `'A'`, `'!'`).

We **declare** (create) variables with the format `data_type variable_name;`.
```c
// Variable declaration
int level;
float battery;
char grade;

// We can also give them values immediately (initialization)
int level = 5;
float battery = 95.5;
char grade = 'A';
```
## 2. Semicolon (;): The "Finished!" Command
This is the most important rule in C:

**Every statement MUST end with a semicolon (`;`)**

The semicolon tells the C _compiler_ that one instruction is complete and it should move to the next instruction.

```c
// CORRECT
int level = 5;
printf("Hello");

// WRONG (Will cause an error!)
int level = 5
printf("Hello")
```

9 out of 10 of your first _bugs_ will be caused by forgetting to place a semicolon. Always double-check!

## 3. Comments: Notes for Humans
Comments are text that the compiler ignores - they're for human readers to understand the code.

Use `//` for single-line comments:
```c
// This is a comment explaining the next line
int level = 5; // This comment explains this specific line
```

Comments are essential for making your code readable and maintainable. Always use them to explain what your code does!

## 4. `printf()`: The Message Broadcaster

`printf()` (short for "print formatted") is our standard function for **sending output (text) to the console**.
To print simple text, we use quotation marks:

```c
printf("Mission Started!");
```

To print values from variables, we use **Format Specifiers**:
- `%d` for `int` (decimal)
- `%f` for `float`
- `%c` for `char`

We also use **Escape Sequences** like `\n` to create a **newline**.

```c
int level = 3;
float xp = 75.5;

// Print variable values
printf("Cadet, you are at Level %d\n", level);
printf("Your current XP: %f\n", xp);
```

**Output:**
```
Cadet, you are at Level 3
Your current XP: 75.500000
```

## 5. `scanf()` and the Ampersand (&): Reading User Input

`scanf()` is the function we use to **read input** from the user. This is where most beginners get confused!

**The Critical Rule:** When using `scanf()` with variables (except strings), you MUST use the ampersand (`&`) before the variable name.

```c
int age;

printf("Enter your age: ");
scanf("%d", &age);  // Notice the & before age

printf("You are %d years old\n", age);
```

**Why do we need the `&`?**
The `&` gives `scanf()` the **memory address** of the variable - think of it as giving the function the variable's "mailbox address" so it knows where to put the value it reads from the keyboard.

Without the `&`, `scanf()` doesn't know where to store the input, and your program will crash or behave unpredictably.

```c
// CORRECT - with &
scanf("%d", &number);
scanf("%f", &price);

// WRONG - without & (will cause problems!)
scanf("%d", number);   // DON'T do this!
scanf("%f", price);    // DON'T do this!
```

That's it! Master these fundamentals and you'll avoid most beginner mistakes.
## QUIZ

**Q1: What happens if you forget to add a semicolon (;) at the end of a C statement?**
A. The program will ignore it and continue.
B. The program will show a warning but still run.
C. The program will fail to compile and produce an error.
D. The program will run slower.
**Answer: C**

**Q2: You have a variable int age = 25;. Which printf() syntax is correct to display it?**
A. printf("Age: %f", age);
B. printf("Age: %c", age);
C. printf("Age: %d", age);
D. printf("Age: %s", age);
**Answer: C**

**Q3: Which of the following is a valid float variable declaration in C?**
A. float value = 100;
B. float value = 95.5;
C. float value = 'A';
D. All answers are correct.
**Answer: B** (Although A is technically valid, B is the most appropriate example for float)

**Q4: What is the function of \n in a printf() string?**
A. Makes the text bold.
B. Adds a space (tab).
C. Creates a newline.
D. Displays the character n.
**Answer: C**

**Q5: Look at the following code. Why will this code FAIL?**
```c
int main() {
    int level = 5
    printf("Level: %d\n", level);
    return 0;
}
```
A. The use of printf is wrong.
B. Missing curly braces {}.
C. Forgot semicolon (;) after int level = 5.
D. return 0 should be return 1.
**Answer: C**

**Q6: What symbol is used to create single-line comments in C?**
A. /* */
B. //
C. #
D. --
**Answer: B**

**Q7: Why do we need the ampersand (&) in scanf("%d", &number);?**
A. It's optional and doesn't matter.
B. To convert the number to text.
C. To give scanf the memory address of the variable where to store the input.
D. To print the variable to the screen.
**Answer: C**