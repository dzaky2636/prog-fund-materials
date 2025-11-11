# Remedial Mission: Simple Count Drill
Hello Cadet, M.E.C.H.A. here. Our looping logic went a bit off course. Don't worry, that's normal! Let's focus on one type of loop that is the most basic and most common: **Counter-Controlled Repetition**.
## Main Focus: FOR Loops
This loop is also called **Definite Repetition** because we know exactly how many times we want to repeat even before the loop starts.

Examples:
* "Print 'Hello' 5 times."
* "Count from 1 to 10."

To do this, we use a loop control variable (commonly called `counter` or `i`) to count the number of repetitions. There are three important parts in this loop:

1. **Initialization:** We give an initial value to our counter (e.g., `SET counter = 1`).
2. **Testing:** We check if the counter has reached its end limit (e.g., `WHILE counter <= 5`).
3. **Updating:** We change the counter value at the end of each repetition so the loop can stop (e.g., `SET counter = counter + 1`).

### Flowchart Review 

The FOR loop flowchart shows the three essential components: initialization, testing, and updating in a structured format.

### Pseudocode Review
In pseudocode, we can shorten these three steps into one neat `FOR` command:

```pseudocode
FOR counter = 1 TO 5
    WRITE "Hello"
ENDFOR
```

The command `FOR counter = 1 TO 5` automatically performs all three steps:
1. **Initialization:** `counter` starts from `1`.
2. **Testing:** The loop will run as long as `counter` is less than or equal to `5`.
3. **Updating:** `counter` will automatically be increased by `1` each time the loop completes.

Let's try some simple exercises for this!
## QUIZ

**Q1: What type of loop is best to use when you know exactly the number of repetitions (for example, 10 times)?**
A. DO-WHILE Loop
B. WHILE Loop (Sentinel-Controlled)
C. FOR Loop (Counter-Controlled)
D. IF-THEN-ELSE
**Answer: C**

**Q2: Consider the following pseudocode:**
```
FOR i = 1 TO 4         ← Init: i=1, Test: i≤4, Update: i++
    WRITE "Hello"
ENDFOR
```
**How many times will the word "Hello" be printed on screen?**
A. 1 time
B. 3 times
C. 4 times
D. 5 times
**Answer: C** (Explanation: Loop runs for i=1, i=2, i=3, and i=4. Total 4 times.)

**Q3: What are the three important parts of counter-controlled loop?**
A. Input, Process, Output
B. If, Else, Endif
C. Start, Stop, Pause
D. Initialization, Testing, Updating
**Answer: D**

**Q4: Consider the following pseudocode:**
```
FOR x = 1 TO 3         ← Init: x=1, Test: x≤3, Update: x++
    WRITE x
ENDFOR
```
**What is the output of the code above?**
A. 1 2 3
B. 1 2 3 4
C. 3
D. 1
**Answer: A**

**Q5: Consider the following pseudocode:**
```
FOR k = 5 TO 10        ← Init: k=5, Test: k≤10, Update: k++
    WRITE "Test"
ENDFOR
```
**How many times will the word "Test" be printed?**
A. 5 times
B. 10 times
C. 1 time
D. 6 times
**Answer: D** (Explanation: Loop runs for k=5, 6, 7, 8, 9, 10. Total 6 times.)