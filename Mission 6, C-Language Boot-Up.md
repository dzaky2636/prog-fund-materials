# Mission 6: C-Language Boot-Up
Cadet, welcome to the "Live-Fire Zone"!
Everything we learned in Sector 1 (flowcharts, pseudocode) was *logic* on paper. Now, it's time to apply that logic using the real tool: **The C Programming Language**.
In this mission, we'll perform a "boot-up" of our C system. We'll learn basic syntax, how memory works, and how to perform the most fundamental operations: Input and Output.

## What is C?
C is a **compiled, high-level programming language** developed in the early 1970s. Unlike interpreted languages, C code must be compiled (translated) into machine code before it can run. This is why we needed to understand logic flow (flowcharts) first - C gives us the tools to implement that logic efficiently and precisely.
## 1. Basic C Program Structure
Forget `READ` and `WRITE`. In C, syntax is everything. Every C program has the same basic structure:
```c
// 1. Preprocessor Directive
#include <stdio.h>

// 2. Main Function (Program Entry Point)
int main() {
    
    // 3. Program Body (Your code here)
    printf("Hello, Cadet!");
    
    // 4. Return Statement
    return 0;
}
```

- `#include <stdio.h>`: This is a command for the _preprocessor_ to include the **Standard Input/Output** header file (`stdio.h`). This file gives us access to important functions like `printf` and `scanf`.
- `int main()`: This is the **main function**. C program execution _always_ starts here.
- `{ ... }`: Curly braces mark the beginning and end of a code block.
- `printf("Hello, Cadet!");`: This is a function from `stdio.h` to **print** (output) text to the console.
- `return 0;`: Indicates that the program ended successfully.
- **Semicolon (`;`)**: Important! In C, every statement **must** end with a semicolon. This is one of the most common _bugs_ you'll encounter!

## 2. Comments
Comments are text that the compiler ignores - they're for human readers to understand the code.

### Single-line Comments
Use `//` for single-line comments:
```c
// This is a single-line comment
int level = 5; // Comment can also be at the end of a line
```

### Multi-line Comments
Use `/* */` for multi-line comments:
```c
/* This is a multi-line comment
   that can span several lines
   and is very useful for longer explanations */
```

## 3. Constants
Constants are values that cannot be changed during program execution. There are two ways to define constants:

### Preprocessor Method
```c
#define PI 3.14159
#define MAX_LEVEL 100
```
The preprocessor simply replaces every occurrence of `PI` with `3.14159` before compilation.

### Modern/Safer Method
```c
const float PI = 3.14159;
const int MAX_LEVEL = 100;
```
This creates a proper constant variable that the compiler can type-check and optimize better.

---
## 4. Variables & Data Types
A variable is a "location in memory" that we give a name to store data. When you create a variable, you must tell C what type of data it will store.

### Basic Data Types
The most common basic data types are:
- `int`: For whole numbers (Example: `5`, `-10`, `1000`).
- `float`: For single-precision decimal numbers (Example: `3.14`, `1.5`).
- `double`: For double-precision decimal numbers (more accurate than `float`).
- `char`: For single characters (Example: `'A'`, `'z'`, `'!'`).

### Data Type Modifiers
You can modify the basic data types to change their size and range:
- `short`: Makes integers smaller (usually 16 bits)
- `long`: Makes integers larger (usually 64 bits)
- `unsigned`: Removes negative values, doubling the positive range

Examples:
```c
short int small_number = 100;
long long big_number = 1000000000LL;
unsigned int positive_only = 4000000000U;
```

### Variable Declaration
We declare variables with the format `data_type variable_name;`.
```c
int level = 5;
float price = 150.75;
char grade = 'A';
unsigned int score = 95000;
long long total_xp = 1500000LL;
```

---
## 5. Operators
Operators are symbols that tell the _compiler_ to perform mathematical or logical operations.

### A. Arithmetic Operators
These are the basic mathematical operators:
- `+` (Addition)
- `-` (Subtraction)
- `*` (Multiplication)
- `/` (Division)
- `%` (**Modulo / Remainder**): Very useful! `5 % 2` will result in `1` (remainder when 5 is divided by 2).

### B. Assignment Operator (=)
- The `=` sign does **not** mean "equals". It means "assign value".
- The statement `x = a + b;` means: "Calculate `a + b`, then _store_ the result in variable `x`".

### C. Increment and Decrement Operators
These operators increase or decrease a variable by 1:
- `++` (Increment): Adds 1 to the variable
- `--` (Decrement): Subtracts 1 from the variable

**Important distinction between prefix and postfix:**
```c
int count = 5;
int result1 = ++count; // Pre-increment: count becomes 6, then result1 = 6
int result2 = count++; // Post-increment: result2 = 6, then count becomes 7
```

### D. Compound Assignment Operators
Shorthand operators that combine arithmetic with assignment:
- `+=` (Add and assign): `x += 5` is the same as `x = x + 5`
- `-=` (Subtract and assign): `x -= 3` is the same as `x = x - 3`
- `*=` (Multiply and assign): `x *= 2` is the same as `x = x * 2`
- `/=` (Divide and assign): `x /= 4` is the same as `x = x / 4`
- `%=` (Modulo and assign): `x %= 3` is the same as `x = x % 3`

### E. Conditional (Ternary) Operator
A shorthand for simple if-else statements:
```c
condition ? true_value : false_value
```
Example:
```c
int age = 20;
char *status = (age >= 18) ? "Adult" : "Minor";
```

### F. Comparison (Relational) Operators
Used in `IF` statements (which we'll cover in the next mission) and always return `1` (True) or `0` (False).
- `==` (Equal to) -> **CAREFUL!** `==` (comparison) is DIFFERENT from `=` (assignment).
- `!=` (Not equal to)
- `>` (Greater than)
- `<` (Less than)
- `>=` (Greater than or equal to)
- `<=` (Less than or equal to)

### G. Logical Operators
Used to combine conditions:
- `&&` (Logical AND)
- `||` (Logical OR)
- `!` (Logical NOT)

### H. Bitwise Operators (Advanced)
These operators work at the bit level for low-level manipulation:
- `&` (Bitwise AND)
- `|` (Bitwise OR)
- `^` (Bitwise XOR)
- `~` (Bitwise NOT)
- `<<` (Left shift)
- `>>` (Right shift)

*Note: Bitwise operators will be covered in detail in advanced missions.*

---
## 6. Input & Output (I/O)
How do we interact with programs?

### `printf()` (Formatted Output)
We've already seen `printf()` for printing text. But `printf()` can also print variables using **format specifiers**:
- `%d` for `int` (decimal)
- `%f` for `float`
- `%c` for `char`
- `%s` for strings (we'll cover this more in advanced missions)
- `\n` is an _escape sequence_ to create a **newline**.

#### Advanced Formatting
You can control how numbers are displayed:
- **Field width**: `%5d` prints an integer in a field of 5 characters (right-aligned)
- **Zero padding**: `%05d` pads with zeros instead of spaces
- **Float precision**: `%.2f` displays a float with exactly 2 decimal places

```c
int level = 8;
float xp = 45.3;
printf("Level: %05d\n", level);      // Output: Level: 00008
printf("XP: %.2f\n", xp);            // Output: XP: 45.30
printf("Progress: %6.1f%%\n", 78.5); // Output: Progress:   78.5%
```

### `scanf()` (Formatted Input)
`scanf()` is a function to **read input** from the keyboard. It's a bit tricky because we must tell C the _memory address_ of the variable we want to fill. We do this using the **ampersand (`&`)** symbol.

#### Reading Numbers
```c
int number_input;

printf("Enter a number: ");
scanf("%d", &number_input); // Notice the &

printf("You entered: %d\n", number_input);
```

#### Reading Strings (Single Word)
```c
char name[50]; // Array to hold the string

printf("Enter your name: ");
scanf("%s", name); // No & needed for strings

printf("Hello, %s!\n", name);
```

**Important:** `scanf("%s", ...)` stops reading at the first whitespace (space, tab, newline).

#### Reading Full Lines
To read a complete line including spaces:
```c
char full_line[100];

printf("Enter a sentence: ");
scanf(" %[^\n]", full_line); // Reads until newline

printf("You said: %s\n", full_line);
```

### Unformatted I/O (Single Characters)
For reading and writing single characters:

#### `getchar()` - Read Single Character
```c
char ch;

printf("Press any key: ");
ch = getchar(); // Reads one character from input

printf("You pressed: %c\n", ch);
```

#### `putchar()` - Print Single Character
```c
char letter = 'A';

putchar(letter); // Prints: A
putchar('\n');   // Prints a newline
```

You have completed the _boot-up_! Now let's test your system.
## QUIZ
**Q1: What is the function of #include <stdio.h> in a C program?**
A. To start the main() function.
B. To end the program with return 0;.
C. To include the Standard Input/Output header file, which gives us access to functions like printf() and scanf().
D. To tell the compiler that we're using the C language.
**Answer: C**

**Q2: Which of the following is a valid int (integer) variable declaration in C?**
A. int myNum = 10.5;
B. int myNum = "10";
C. int myNum = 10;
D. myNum = 10;
**Answer: C**

**Q3: What is the main difference between the = and == operators in C?**
A. There is no difference, both are the same.
B. = is for comparing, == is for assigning values.
C. = is for assigning values (assignment), == is for comparing (equality).
D. = is for mathematics, == is for text.
**Answer: C**

**Q4: You want to print the value of a float variable named price. Which printf() is correct?**
A. printf("Price: %d", price);
B. printf("Price: %c", price);
C. printf("Price: %s", price);
D. printf("Price: %f", price);
**Answer: D**

**Q5: Why do we use the ampersand (&) symbol in scanf("%d", &age);?**
A. It is optional.
B. To convert age to text.
C. To tell scanf the memory address of the variable age where to store the input.
D. To print the value of age to the screen.
**Answer: C**

**Q6: What is the difference between const int X = 5; and #define X 5?**
A. They are exactly the same.
B. const creates a typed constant variable, #define is a preprocessor text replacement.
C. #define is safer and more modern.
D. const can be changed during runtime, #define cannot.
**Answer: B**

**Q7: If x = 5, what will be the value of y after this statement: y = ++x;?**
A. y = 5, x = 5
B. y = 5, x = 6
C. y = 6, x = 6
D. y = 6, x = 5
**Answer: C**

**Q8: How do you print a float variable price to exactly 2 decimal places?**
A. printf("%.2f", price);
B. printf("%2f", price);
C. printf("%f.2", price);
D. printf("%d.2", price);
**Answer: A**

**Q9: What is the purpose of the getchar() function?**
A. To print a single character
B. To read a single character from input
C. To count characters in a string
D. To convert characters to numbers
**Answer: B**

**Q10: Which statement is equivalent to x = x + 5;?**
A. x =+ 5;
B. x += 5;
C. x++5;
D. x + 5;
**Answer: B**

---
### Coding Challenge
Create your first comprehensive C program! This program should:
1. Ask for the user's **Level** (as an `int`)
2. Ask for their **XP** (as a `float`)
3. Print back a formatted summary that displays:
   - XP to exactly **two decimal places**
   - Level padded with zeros to **3 digits**

**Example Input/Output:**
```
Enter your Level: 8
Enter your current XP: 45.3

[Player Stats]
Level: 008
XP: 45.30
```

### Code Template
```c
#include <stdio.h>

int main() {
    // 1. Declare variables for level (int) and xp (float)
    
    // 2. Ask for and read the user's level
    
    // 3. Ask for and read the user's XP
    
    // 4. Print the formatted summary
    // Use %03d for zero-padded 3-digit level
    // Use %.2f for XP with 2 decimal places
    
    return 0;
}
```

### Test Cases
```json
[
  { 
    "input": "8\n45.3", 
    "output": "Enter your Level: Enter your current XP: \n[Player Stats]\nLevel: 008\nXP: 45.30" 
  },
  { 
    "input": "25\n1337.9", 
    "output": "Enter your Level: Enter your current XP: \n[Player Stats]\nLevel: 025\nXP: 1337.90" 
  },
  { 
    "input": "1\n0.0", 
    "output": "Enter your Level: Enter your current XP: \n[Player Stats]\nLevel: 001\nXP: 0.00" 
  }
]
```