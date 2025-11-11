# Mission 3: The Time Loop

Cadet, welcome to "The Time Loop". In the previous mission, we learned how to make decisions with `IF` statements. Now, we will learn how to repeat them. **Repetition Control Structures (Loops)** are instructions that the computer executes repeatedly while (or until) a certain condition is met.

This is the backbone of automation. Instead of writing `WRITE "Hello"` five times, we can tell the computer to do it for us.
## 1. Types of Repetition

A loop is a group of instructions the computer executes repeatedly while some loop repetition condition remains true. There are two main categories of repetition:

1. **Counter-Controlled Repetition:** We know exactly how many times we want to repeat. For example, "Repeat exactly 5 times". This is often called a `FOR` loop. Counter-controlled repetition is sometimes called definite repetition because we know in advance exactly how many times the loop will be executed.

2. **Sentinel-Controlled Repetition:** We don't know how many times we will repeat. The loop will continue running until a specific condition ("sentinel") is met. For example, "Keep asking for password UNTIL user enters the correct one". Sentinel-controlled repetition is sometimes called indefinite repetition because it's not known in advance how many times the loop will be executed.
## 2. Sentinel-Controlled Repetition

### WHILE Loop (Pre-Test)
![Flowchart struktur WHILE](https://i.imgur.com/ALYVCZh.png)
The `WHILE` loop is a pre-test loop. This means it **checks the condition first** before performing an action. If the initial condition is `False`, the loop may not run at all.

**Logic:** "WHILE a condition is true, do some task."

The loop is repeated when the condition is true (when its value is not 0). The loop is exited when the condition is false.

**Example Pseudocode:**
```
DECLARE counter AS INTEGER

START
SET counter = 1                  ← Initialization
WHILE counter <= 5               ← Testing
	WRITE "Hello world"
	SET counter = counter + 1     ← Updating
ENDWHILE
STOP
```
* **Output:** "Hello world" will be printed 5 times. On the 6th iteration, `counter` will become 6. The condition `6 <= 5` is `False`, so the loop stops.
### DO-WHILE Loop (Post-Test)
![Flowchart struktur DO-WHILE](https://i.imgur.com/i8D40no.png)
The `DO-WHILE` loop is a post-test loop. This means it **performs an action first**, then checks the condition at the end. This guarantees that the action inside the loop will **run at least once**, even if the initial condition is `False`.

**Logic:** "DO this task, WHILE this condition is true."

As a result, the DO-WHILE loop always performs at least one iteration, even if its condition is false to begin with.

**Example Pseudocode:**
```
DECLARE number AS INTEGER

START
SET number = 0                    ← Initialization
DO
	WRITE number
	SET number = number + 1         ← Updating
WHILE number < 10                   ← Testing
STOP
```
* **Output:** This will print numbers 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9.
### DO-UNTIL Loop
![Flowchart struktur DO-UNTIL](https://i.imgur.com/GQ4RC9C.png)
The `DO-UNTIL` structure is similar to `DO-WHILE`, but the logic is reversed. It will continue repeating **WHILE the condition is `False`**, and only stop **WHEN the condition becomes `True`**.

**Logic:** "DO this task, UNTIL this condition is true."

Sometimes, it is more convenient to write a loop that iterates until a condition is true—that is, a loop that iterates as long as a condition is false, and then stops when the condition becomes true.

**Example Pseudocode (Password Validation):**
```
DECLARE password AS STRING

START
SET password = ""                ← Initialization (empty password)
DO
	WRITE "Enter the password:"
	READ password                ← Updating (new input from user)
	IF password != "prospero" THEN
		WRITE "Sorry, try again."
	ENDIF
UNTIL password == "prospero"     ← Testing (condition check)
WRITE "Password confirmed."
STOP
```
* **Logic:** The loop will continue running (`Sorry, try again.`) as long as `password != "prospero"` (the `UNTIL` condition is `False`). It only stops when the user enters "prospero" (the `UNTIL` condition becomes `True`).
## 3. Counter-Controlled Repetition

### FOR Statement
![Flowchart struktur FOR](https://i.imgur.com/QV7AGIu.png)
![Flowchart struktur FOR](https://i.imgur.com/A6jaCZw.png)
Counter-controlled repetition is sometimes called definite repetition because we know in advance exactly how many times the loop will be executed. This is usually called the FOR statement.

A loop control variable is used to count the number of repetitions. This is a cleaner way to write *counter-controlled loop*. It combines three steps in one line:

1. **Initialization:** Loop control variable is set to an initial value before the while statement is reached (e.g., `counter = 1`).
2. **Testing:** Loop control variable is tested before the start of each loop repetition (e.g., `counter <= 10`).
3. **Updating/Increment:** Loop control variable is updated (incremented/decremented) during each iteration (e.g., `counter = counter + 1`).

In some situations, it is also helpful to use the counter variable in a calculation or other task within the body of the loop. For example, suppose you need to write a program that displays the numbers 1 through 10 and their squares.

**Example Pseudocode:**
```
DECLARE counter AS INTEGER
DECLARE square AS INTEGER

START
WRITE "Number Square"
WRITE "--------------"
FOR counter = 1 TO 10            ← Initialization (counter=1), Testing (counter<=10), Updating (counter++)
	SET square = counter * counter
	WRITE counter, square
ENDFOR
STOP
```

**Breaking down the FOR loop components:**
- **Initialization:** `counter = 1` (sets starting value)
- **Testing:** `counter <= 10` (checks if loop should continue)  
- **Updating:** `counter = counter + 1` (increments after each iteration)
* **Output:** This will print a list of numbers 1 through 10 and their squares.

## QUIZ

**Q1: What is the main difference between `WHILE` and `DO-WHILE` loops?**
A. `WHILE` checks condition at the end, `DO-WHILE` checks at the beginning.
B. `WHILE` is guaranteed to run at least once, `DO-WHILE` might not run at all.
C. `WHILE` checks condition at the beginning (pre-test), `DO-WHILE` checks at the end (post-test).
D. There is no difference, both are the same.
**Answer: C**

**Q2: You want to create a program that MUST ask for user password at least once. Which loop structure is best for this?**
A. `FOR`
B. `WHILE`
C. `DO-WHILE` (or `DO-UNTIL`)
D. `IF-THEN-ELSE`
**Answer: C**

**Q3: Consider the following pseudocode:**
```
DECLARE counter AS INTEGER

START
SET counter = 10              ← Initialization
WHILE counter < 5             ← Testing
	WRITE "Hello"
	SET counter = counter + 1  ← Updating
ENDWHILE
STOP
```
**What is the output of the code above?**
A. Hello
B. Hello (repeated 5 times)
C. Hello (repeated 10 times)
D. No output at all.
**Answer: D**

**Q4: Consider the following pseudocode:**
```
DECLARE counter AS INTEGER

START
SET counter = 10              ← Initialization
DO
	WRITE "Hello"
	SET counter = counter + 1  ← Updating
WHILE counter < 5             ← Testing
STOP
```
**What is the output of the code above?**
A. Hello
B. Hello (repeated 5 times)
C. Hello (repeated 10 times)
D. No output at all.
**Answer: A**

**Q5: (Logic Challenge) You want to print the sequence: `20 14 8 2 -4 -10`. Which `FOR` pseudocode is most appropriate?**
A. `FOR counter = 20 TO -10`
B. `FOR counter = 20 TO -10 STEP -6` ← Init: 20, Test: ≥-10, Update: -6
C. `FOR counter = 1 TO 6 STEP 6`
D. `FOR counter = 20 TO -10 STEP 6`
**Answer: B**

**Explanation:** The three components in the correct answer:
- **Initialization:** `counter = 20` (starts at 20)
- **Testing:** `counter >= -10` (continues while ≥ -10)
- **Updating:** `counter = counter - 6` (decreases by 6 each time)