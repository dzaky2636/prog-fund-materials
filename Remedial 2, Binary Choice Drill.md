# Remedial Mission 2: Binary Choice Drill

Hello Cadet, M.E.C.H.A. here again. In the last mission, our selection logic was slightly off target. Let's sharpen the core foundation again: **IF-THEN-ELSE**.

## Core Focus: Binary Choice (IF-THEN-ELSE)
Let's forget complex `Nested IF` or `CASE` structures for now. We'll focus on the most basic structure: "IF-THEN-ELSE".

This is simple binary choice:
* **IF:** We test a condition.
* **THEN:** What we do if the condition is **True**.
* **ELSE:** What we do if the condition is **False**.
Only one of these two paths will be executed. Never both.

## Review: Basic Computer Operations in Selection

Before we practice, remember that selection control uses the 5th basic computer operation: **A computer can compare two variables and select one of two alternative actions**.

To represent this operation in pseudocode, we use special keywords: **IF**, **THEN**, and **ELSE**.
- The comparison is established in the IF clause
- The choice of alternatives is determined by the THEN or ELSE options
- Only one of these alternatives will be performed

### Pseudocode Review
```
IF condition THEN
    ...code block if TRUE...
ELSE
    ...code block if FALSE...
ENDIF
```

### Flowchart Review
The selection structure uses a diamond-shaped decision symbol. The condition is evaluated, and based on whether it's true or false, the program follows different paths.

### Relational Operators for Conditions
Remember these operators for creating conditions:
* `<` (less than)
* `>` (greater than) 
* `=` (equal to)
* `<=` (less than or equal to)
* `>=` (greater than or equal to)
* `<>` (not equal to)

Let's ensure we master this with some quick exercises!

## QUIZ
**Q1: Consider the following pseudocode:**
```
SET value = 15
IF value > 10 THEN
	WRITE "Greater"
ELSE
	WRITE "Smaller"
ENDIF
```
**What is the output of the code above?**
A. Greater
B. Smaller
C. GreaterSmaller
D. No output
**Answer: A**

**Q2: Consider the following pseudocode:**
```
SET temperature = 25
IF temperature <= 20 THEN
	WRITE "Cold"
ELSE
	WRITE "Hot"
ENDIF
```
**What is the output of the code above?**
A. Cold
B. Hot
C. ColdHot
D. No output
**Answer: B**

**Q3: In an `IF-THEN-ELSE` structure, which code block will be executed if the `IF` condition is FALSE?**
A. The `THEN` block
B. The `ELSE` block
C. Both `THEN` and `ELSE` blocks
D. No block is executed
**Answer: B**

**Q4: Consider the following algorithm for checking even/odd numbers:**
```
Prompt user for number
Get number
IF number MOD 2 = 0 THEN
    Display "Even"
ELSE
    Display "Odd"
ENDIF
```
**If the user enters the number `7`, what is the output?**
A. Even
B. Odd
C. 7
D. Error
**Answer: B**

**Q5: Consider the following pseudocode:**
```
SET x = 5
SET y = 5
IF x = y THEN
	WRITE "Same"
ELSE
	WRITE "Different"
ENDIF
```
**What is the output of the code above?**
A. Same
B. Different
C. 5
D. Error
**Answer: A**

**Q6: Which of the following demonstrates proper use of relational operators?**
A. `IF student_attendance = "part_time" THEN`
B. `IF account_balance < 300 THEN`
C. `IF age >= 18 THEN`
D. All of the above
**Answer: D**