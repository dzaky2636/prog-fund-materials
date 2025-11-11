# Mission 5: Midterm Exam (The Logic Gauntlet)

Cadet, M.E.C.H.A. here. You have mastered the fundamentals of logic. You've conquered Sector 1's simulator.
Now it's time for "The Gauntlet"—the comprehensive final exam for Sector 1. Here, we will test everything you've learned, from basic flowcharts to complex modular logic.
This exam ensures you're truly ready for Sector 2, where we'll implement all this logic into the *live-fire* C language.
Focus, review your mission logs, and prove your mastery. Good luck, Cadet.

## ALGORITHM FUNDAMENTALS

An algorithm is a set of detailed, unambiguous, and ordered instructions developed to describe the processes necessary to produce the desired output from a given input. Flowcharts and pseudocodes are both popular ways of representing algorithms.

## QUIZ SECTION

**Q1: In flowcharts, which symbol is used to read input from the user OR display output to the screen?**
A. Rectangle
B. Oval (Terminator)
C. Parallelogram
D. Diamond
**Answer: C**

**Q2: You need to make a decision in an algorithm that has two paths: 'True' and 'False'. Which flowchart symbol would you use?**
A. Parallelogram
B. Diamond
C. Rectangle
D. Circle (Connector)
**Answer: B**

**Q3: Consider the following pseudocode:**
```pseudocode
START
DECLARE INTEGER x
DECLARE INTEGER y

SET x = 10
SET y = 20

IF x > y THEN
    WRITE "A"
ELSE
    IF y > 30 THEN
        WRITE "B"
    ELSE
        WRITE "C"
    ENDIF
ENDIF
STOP
```
What is the output of the code above?
A. A
B. B
C. C
D. A and C
**Answer: C**

**Q4: What is the fundamental difference between WHILE loop and DO-WHILE loop?**
A. WHILE is pre-test (may run 0 times), DO-WHILE is post-test (guaranteed to run at least once).
B. WHILE is for numbers, DO-WHILE is for text.
C. WHILE is post-test, DO-WHILE is pre-test.
D. WHILE is definite iteration, DO-WHILE is indefinite iteration.
**Answer: A**

**Q5: Consider the following pseudocode:**
```pseudocode
START
DECLARE INTEGER total
DECLARE INTEGER i

SET total = 0
FOR i = 1 TO 4
    SET total = total + i
ENDFOR

WRITE total
STOP
```
What value of total will be printed at the end?
A. 4
B. 5
C. 10
D. 0
**Answer: C** (Explanation: 1 + 2 + 3 + 4 = 10)

**Q6: Which of the following is NOT a main benefit of Modularization?**
A. Code becomes easier to understand.
B. Code can be reused.
C. Makes programs run significantly faster.
D. Code maintenance becomes more efficient.
**Answer: C**

**Q7: Consider this pseudocode:**
```pseudocode
MODULE Double(REF number)
    START
    SET number = number * 2
    STOP
END MODULE

// Main Program
START
DECLARE INTEGER my_value

SET my_value = 5
Double(my_value)
WRITE my_value
STOP
```
What is the output of the main program above?
A. 5
B. 10
C. 2
D. Error
**Answer: B** (Explanation: Because it uses REF (Pass-by-Reference), the Double module changes the original value of my_value.)

**Q8: Consider this pseudocode:**
```pseudocode
START
DECLARE INTEGER x

SET x = 5

WHILE x < 5
    WRITE "Loop running"
ENDWHILE
STOP
```
What is the output of the code above?
A. Loop running
B. 5
C. No output (Empty)
D. Error (Infinite Loop)
**Answer: C** (Explanation: This is a WHILE loop (pre-test). The condition 5 < 5 is immediately False, so the loop body is never executed.)

**Q9: The CASE OF structure in pseudocode is most efficiently used to replace...**
A. Nested/cascading IF-THEN-ELSE chains.
B. FOR loops.
C. WHILE loops.
D. Pass-by-Reference.
**Answer: A**

**Q10: (Logic Challenge) Consider the following pseudocode:**
```pseudocode
START
DECLARE INTEGER a
DECLARE INTEGER b

SET a = 5
SET b = 10

IF a > 2 AND b < 100 THEN
    SET a = a + 1
ELSE
    SET a = a - 1
ENDIF

IF b < 10 OR a = 5 THEN
    SET b = b + 1
ELSE
    SET b = b - 1
ENDIF

WRITE a
WRITE b
STOP
```
What is the final output of this program?
A. 4 and 11
B. 6 and 9
C. 4 and 9
D. 6 and 11
**Answer: B** (Explanation: 1. 5 > 2 (True) AND 10 < 100 (True) → a becomes 6. 2. 10 < 10 (False) OR 6 = 5 (False) → b becomes 9. Output is 6 and 9.)