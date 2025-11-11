# Mission 1: The Algorithmic Nexus

Welcome, Cadet! In this first mission, we will learn the foundation of all programming: **Algorithms**. This is the blueprint we use before we start building.
## What is an Algorithm?

Simply put, an algorithm is **like a recipe**: it lists the steps involved in accomplishing a task. In programming terms, an algorithm can be defined as a set of **detailed, unambiguous, and ordered instructions** developed to describe the processes necessary to produce the desired output from a given input.

A good programmer doesn't jump straight into coding. They design a solution (algorithm) first, test it, and then code the program in a chosen programming language. Leaping straight into the coding phase without first designing a proper solution usually results in a program that contains many errors!

There are two popular ways of representing algorithms: **Flowcharts** and **Pseudocode**.

---

## Program Development Process

Before diving into algorithm representation, let's understand the basic steps in program development:

1. **Define the problem** - Identify what needs to be solved
2. **Outline the solution** - Plan the approach
3. **Develop the outline into an algorithm** - Create detailed steps
4. **Test the algorithm for correctness** - Desk check the solution
5. **Code the algorithm into a specific programming language** - Implement the solution
6. **Run the program on the computer** - Execute and verify
7. **Document and maintain the program** - Keep records and updates

---

## 1. Flowcharts

Flowcharts are popular because they graphically represent the program logic by a series of **standard geometric symbols** and connecting lines. Flowcharts are relatively easy to learn and are an intuitive method of representing the flow of control in an algorithm.

### Standard Flowchart Symbols
![Diagram simbol-simbol dasar flowchart: Oval, Jajar Genjang, Persegi Panjang, dan Belah Ketupat](https://i.imgur.com/wmkF5Yb.png)

![Diagram simbol-simbol dasar flowchart: Oval, Jajar Genjang, Persegi Panjang, dan Belah Ketupat](https://i.imgur.com/Q1SK0bR.png)

![Diagram simbol-simbol dasar flowchart: Oval, Jajar Genjang, Persegi Panjang, dan Belah Ketupat](https://i.imgur.com/BWAXhX1.png)
Here are the 6 standard flowchart symbols we will use:
**1. Terminal Symbol (Oval):** Indicates the starting or stopping point in the logic. Every flowchart should begin and end with a terminal symbol.
**2. Input/Output Symbol (Parallelogram):** Represents an input or output process in an algorithm, such as reading input or writing output.
**3. Process Symbol (Rectangle):** Represents any single process in an algorithm, such as assigning a value or performing a calculation. The flow of control is sequential.
**4. Decision Symbol (Diamond):** Represents a decision point in the logic where the flow of control branches into different paths. This can be a simple true/false condition (IF-ELSE) or a multi-way branch (CASE structure).
**5. Predefined Process Symbol (Rectangle with vertical lines):** Represents a module in an algorithm — that is, a predefined process that has its own flowchart.
**6. Connector Symbol (Circle):** Used as a connector to show a jump from one point in the process flow to another. Connectors are usually labeled with capital letters (A, B, AA) to show matching jump points.

**Flowlines (Arrows):** Connect various symbols in a flowchart, and contain an arrowhead only when the flow of control is not from top to bottom or left to right.

---
## 2. The Three Basic Control Structures
![image](https://i.imgur.com/mJqnZ0l.png)
Algorithms have three basic control structures:
1. **Sequence:** The straightforward execution of one processing step after another. Instructions are executed one by one, from top to bottom, without branching.
2. **Selection:** The presentation of a condition and the choice between two actions, the choice depending on whether the condition is true or false. This structure uses the Decision (Diamond) symbol.
3. **Repetition:** The presentation of a set of instructions to be performed repeatedly, as long as a condition is true. (We will cover this in future missions!)

### Sequence Control Structure
![image](https://i.imgur.com/mJqnZ0l.png)
**Sequence** is the most fundamental control structure. In sequence control, instructions are executed one after another in the exact order they are written, from top to bottom. There is no branching or jumping—each step follows the previous step directly.

**Example of Sequence Structure:**
```
START
READ student_name
READ test_score
SET grade_points = test_score * 0.1
WRITE student_name
WRITE grade_points
STOP
```

In this example, each instruction follows the previous one in sequence:
1. Program starts
2. Read student name
3. Read test score
4. Calculate grade points
5. Display student name
6. Display grade points
7. Program stops

This straightforward, step-by-step execution is the foundation of all algorithms. Even complex programs with selections and repetitions are built upon this basic sequential flow.

### Selection Control Structure Examples
![image](https://i.imgur.com/2tXScFj.png)
![image](https://i.imgur.com/5sT0E5W.png)
**Simple IF Statement:** Used when a choice is made between two alternative paths, depending on the result of a condition being true or false.
![image](https://i.imgur.com/R9skRje.png)
**Null ELSE Statement:** A variation of the simple IF structure. Used when a task is performed only when a particular condition is true. If the condition is false, no processing will take place.
![image](https://i.imgur.com/NzzK9RH.png)
**Combined IF Statement:** Contains multiple conditions in the decision symbol, each connected with logical operators AND or OR. If AND is used, both conditions must be true for the combined condition to be true.
![image](https://i.imgur.com/erTFi0k.png)
**Nested IF Statement:** Used when a field is being tested for various values, with different action to be taken for each value. Represented by a series of decision symbols in a flowchart.
![Diagram flowchart CASE Structure](https://i.imgur.com/ncvQ7fc.png)
**Case Structure:** Another way of expressing a nested IF statement. It extends the basic selection control structure to be a choice between multiple values. Expressed in a flowchart by a decision symbol with multiple paths leading from it.

---

## 3. Pseudocode

Pseudocode is another way of representing algorithms using simple English, without being bound by the syntax rules of any specific programming language. There is no standard pseudocode at present, but common conventions include:

* Statements are written in simple English
* Each instruction is written on a separate line
* Keywords such as `IF`, `THEN`, `ELSE`, `ENDIF`, `READ`, `WRITE`, `SET` are often used and written in capital letters
* Indentation is used to signify particular control structures
* Each set of instructions is written from top to bottom, with only one entry and one exit

**Example Pseudocode for service charge calculation:**
```
READ account_balance
    IF account_balance < 300 
        THEN SET service_charge = 5.00 
        ELSE SET service_charge = 2.00 
    ENDIF
WRITE service_charge
```

---

## Important Note: Terminology Framework

**Cadet, attention!** As you progress through your training missions, you'll notice that our terminology becomes more precise and specialized.

**In this foundational mission**, we use simplified, general terms:
- **READ** - getting data input
- **WRITE** - producing output  
- **SET** - assigning values

**In advanced missions**, you'll learn more precise terminology:
- **INPUT/GET** - reading from keyboard
- **READ** - reading from files
- **DISPLAY/OUTPUT** - showing on screen
- **WRITE** - writing to storage devices  
- **PRINT** - sending to printer

Think of this like learning basic military commands before specialized operations. We build your understanding in layers, just as real cadets master fundamentals before advanced protocols. This isn't changing the rules—it's expanding your operational vocabulary as your skills develop!

## QUIZ

**Q1: What is the best definition of an Algorithm?**
A. Code written in C language.
B. A set of detailed, unambiguous, and ordered instructions to solve a problem.
C. A visual diagram using geometric symbols.
D. A single line command.
**Answer: B**

**Q2: In a flowchart, which symbol is used to represent mathematical calculations or value assignment (e.g., `total = 10`)?**
A. Diamond
B. Parallelogram  
C. Rectangle
D. Oval
**Answer: C**

**Q3: What is the Diamond symbol in a flowchart used for?**
A. Starting or ending a program.
B. Performing calculations (e.g., `total = a + b`).
C. Reading input from the user (e.g., `READ value`).
D. Representing decision points or branching logic in an algorithm.
**Answer: D**

**Q4: In pseudocode, which keyword is most commonly used for producing output?**
A. READ
B. WRITE
C. SET
D. IF
**Answer: B** (Note: In this foundational mission, WRITE represents general output. In advanced missions, we'll learn specific terms like DISPLAY for screen output.)

**Q5: (Logic Challenge) Which pseudocode is most appropriate to determine if someone "Passes" if their grade is 70 or more, and "Fails" if less?**
A.
```
READ grade
IF grade >= 70 THEN
    WRITE "Fail"
ELSE
    WRITE "Pass"
ENDIF
```
B.
```
WRITE "Pass"
READ grade
IF grade < 70 THEN
    WRITE "Fail"
ENDIF
```
C.
```
READ grade
IF grade >= 70 THEN
    WRITE "Pass"
ELSE
    WRITE "Fail"
ENDIF
```
D.
```
READ grade
SET grade = 70
WRITE "Pass"
```
**Answer: C**

**Q6: Which of the following represents the correct order of the program development process?**
A. Code → Test → Define Problem
B. Define Problem → Outline Solution → Develop Algorithm → Test → Code → Run → Document
C. Test → Code → Run
D. Outline → Code → Document
**Answer: B**

**Q7: What does the Predefined Process symbol (rectangle with vertical lines) represent in a flowchart?**
A. A mathematical calculation
B. A decision point
C. A module or subroutine that has its own flowchart
D. Input or output operation
**Answer: C**