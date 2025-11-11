# Mission 2: The Selection Gate

Welcome back, Cadet. In Mission 1, our logic flow was as straight as a laser beam—each instruction executed sequentially (*Sequence*). But in the real world, we must make **decisions**.

In this mission, we will unlock "The Selection Gate." We will learn how algorithms can choose different paths based on specific conditions.

## 1. Foundations: How to Write Pseudocode

Before diving into selection structures, let's master the fundamentals of pseudocode. When designing a solution algorithm, remember that a computer will eventually perform the instructions you write. Using words and phrases that correspond to basic computer operations makes translation to programming languages much simpler.

### The Six Basic Computer Operations

Every computer program is built from these six fundamental operations:

#### 1. A computer can receive information
When a computer needs to receive input, we use these verbs:
- **Read**: Used when receiving input from a file
- **Get**: Used when receiving input from keyboard

Example: `Get student_name`, `Read number_1, number_2`

#### 2. A computer can put out information  
When a computer needs to output information, we use:
- **Print**: For output to printer
- **Write**: For output to file  
- **Put/Output/Display**: For output to screen
- **Prompt**: To request user input

Example: `Display "Enter your age"`, `Print total_amount`

#### 3. A computer can perform arithmetic
For mathematical operations, use these symbols:
- `+` for addition
- `-` for subtraction  
- `*` for multiplication
- `/` for division
- `()` for parentheses

Example: `total = price + tax`

#### 4. A computer can assign values to variables
Three ways to assign values:
- **Initialize/Set**: Give initial values (`Set counter to 0`)
- **=** or **←**: Assign results of processing (`total = cost + tax`)
- **Save/Store**: Keep variables for later use (`Store result in memory`)

#### 5. A computer can compare and select actions
This is our main focus! Use **IF**, **THEN**, **ELSE** keywords for decision-making.

#### 6. A computer can repeat actions
Use **DOWHILE** and **ENDDO** for repetition (covered in future missions).

## 2. Selection Control Structure

**Selection Control Structure** allows algorithms to choose between different paths based on whether a condition is **True** or **False**.

In *flowcharts*, this uses the **Diamond (Decision)** symbol. In *pseudocode*, we use keywords `IF`, `THEN`, `ELSE`, and `ENDIF`.

### Relational Operators
To create conditions, we use **Relational Operators** to compare two values:
* `<` (less than)
* `>` (greater than)  
* `=` (equal to)
* `<=` (less than or equal to)
* `>=` (greater than or equal to)
* `<>` (not equal to)

### Logical Operators
We can combine conditions using **Logical Operators**:
* `AND` (both conditions must be True)
* `OR` (at least one condition must be True)  
* `NOT` (reverses the condition value)

## 3. Types of Selection Structures

There are several variations of selection structure you must master.

### A. Simple Selection (IF-THEN-ELSE)
This is the most common form. "IF condition is True, do A, OTHERWISE (False), do B."

**Example Pseudocode:**
```
START
DECLARE REAL account_balance
DECLARE REAL service_charge

READ account_balance
    IF account_balance < 300 THEN
        SET service_charge = 5.00
    ELSE
        SET service_charge = 2.00
    ENDIF
WRITE service_charge
STOP
```
Here, only one block (either between `THEN` and `ELSE`, or between `ELSE` and `ENDIF`) will be executed.

### B. Null ELSE (IF-THEN)
This structure is used when we only want to do something if the condition is True. If False, no action is taken.

**Example Pseudocode:**
```
START
DECLARE STRING student_attendance
DECLARE INTEGER part_time_count

READ student_attendance
    IF student_attendance = "part_time" THEN
        SET part_time_count = part_time_count + 1
    ENDIF
WRITE part_time_count
STOP
```
If `student_attendance` is not "part_time", the algorithm will jump directly to `ENDIF` without doing anything.

### C. Combined Selection (Combined IF Statement)
A combined IF statement contains multiple conditions connected with logical operators AND or OR.

**Example Pseudocode:**
```
START
DECLARE STRING student_attendance
DECLARE STRING student_gender
DECLARE INTEGER female_part_time_count

IF student_attendance = "part_time" AND student_gender = "female" THEN
    SET female_part_time_count = female_part_time_count + 1
ENDIF
STOP
```
If connector AND is used, both conditions must be true for the combined condition to be true.

### D. Nested Selection (Nested IF Statement)
This occurs when one `IF` structure is inside another `IF` structure. Used for more complex scenarios.

* **Linear Nested IF:** Used when a field is being tested for various values and a different action is taken for each value.
    ```
    START
    DECLARE CHARACTER record_code
    DECLARE INTEGER counter_A
    DECLARE INTEGER counter_B
    DECLARE INTEGER counter_C
    DECLARE INTEGER error_counter

    read record_code
    IF record_code = 'A' THEN
        SET counter_A = counter_A + 1
    ELSE
        IF record_code = 'B' THEN
            SET counter_B = counter_B + 1
        ELSE
            IF record_code = 'C' THEN
                SET counter_C = counter_C + 1
            ELSE
                SET error_counter = error_counter + 1
            ENDIF
        ENDIF
    ENDIF
    STOP
    ```

* **Non-Linear Nested IF:** Occurs when multiple different conditions need to be satisfied before a particular action can occur.
    ```
    START
    DECLARE STRING student_attendance
    DECLARE STRING student_gender
    DECLARE INTEGER student_age
    DECLARE INTEGER mature_female_pt_students
    DECLARE INTEGER young_female_pt_students
    DECLARE INTEGER male_pt_students
    DECLARE INTEGER full_time_students

    READ student_attendance, student_gender, student_age
    IF student_attendance = "part_time" THEN
        IF student_gender = "female" THEN
            IF student_age > 21 THEN
                SET mature_female_pt_students = mature_female_pt_students + 1
            ELSE
                SET young_female_pt_students = young_female_pt_students + 1
            ENDIF
        ELSE
            SET male_pt_students = male_pt_students + 1
        ENDIF
    ELSE
        SET full_time_students = full_time_students + 1
    ENDIF
    STOP
    ```

### E. Case Structure
The case structure is another way of expressing a linear nested IF statement. It makes pseudocode easier to write and understand.

**Example Pseudocode:**
```
START
DECLARE CHARACTER record_code
DECLARE INTEGER counter_A
DECLARE INTEGER counter_B
DECLARE INTEGER counter_C
DECLARE INTEGER error_counter

READ record_code
CASE OF record_code
    'A' : SET counter_A = counter_A + 1
    'B' : SET counter_B = counter_B + 1
    'C' : SET counter_C = counter_C + 1
    other : SET error_counter = error_counter + 1
ENDCASE
STOP
```
This logic is **identical** to the Linear Nested IF example above, but much cleaner.

### F. Boolean Variables
Boolean variables contain only one of two possible values (true or false). When using IF statements with Boolean variables, the IF statement can be simplified:

Instead of: `IF valid_input_fields = true THEN`
Write: `IF valid_input_fields THEN`

## 4. Checking the Solution Algorithm (Desk Checking)

After establishing a solution algorithm, it must be tested for correctness. Desk checking involves tracing through the logic with chosen test data.

### Steps in Desk Checking:
1. Choose simple input test cases that are valid (2-3 test cases are usually sufficient)
2. Establish what the expected result should be for each test case
3. Make a table of relevant variable names within the algorithm
4. Walk the first test case through the algorithm, line by line
5. Repeat with other test data cases until the algorithm reaches its logical end
6. Check that expected results match actual results

You now have the tools to make your algorithms make decisions. Test your understanding in the quiz below!

## QUIZ
**Q1: Which pseudocode is most appropriate for "Simple Selection" (IF-THEN-ELSE)?**
A. `IF condition THEN ... ENDIF`
B. `CASE OF variable ... ENDCASE`
C. `IF condition THEN ... ELSE ... ENDIF`
D. `DOWHILE condition ... ENDDO`
**Answer: C**

**Q2: You want to give a +100 point bonus only if a player has `level > 10`. If the level is 10 or less, nothing happens. Which structure is most efficient for this?**
A. Simple Selection (IF-THEN-ELSE)
B. Nested IF
C. Case Structure
D. Null ELSE (IF-THEN)
**Answer: D**

**Q3: What logical operator is used if you want to execute an action only if `conditionA` AND `conditionB` are both True?**
A. OR
B. AND
C. NOT
D. THEN
**Answer: B**

**Q4: The `CASE OF` structure is a cleaner way to replace...**
A. Non-Linear Nested IF
B. Simple IF
C. Linear Nested IF (ELSE IF Chain)
D. All types of loops
**Answer: C**

**Q5: (Logic Quiz) Consider the following case study: A grading program assigns grades. If score >= 90, grade 'A'. If score 80-89, grade 'B'. If score 70-79, grade 'C'. Which pseudocode is most appropriate?**
A.
```
START
DECLARE INTEGER score
DECLARE CHARACTER grade

READ score
IF score >= 90 THEN
	SET grade = 'A'
ENDIF
IF score >= 80 THEN
	SET grade = 'B'
ENDIF
IF score >= 70 THEN
	SET grade = 'C'
ENDIF
WRITE grade
STOP
```
B.
```
START
DECLARE INTEGER score
DECLARE CHARACTER grade

READ score
CASE OF score
	90 : SET grade = 'A'
	80 : SET grade = 'B'
	70 : SET grade = 'C'
ENDCASE
WRITE grade
STOP
```
C.
```
START
DECLARE INTEGER score
DECLARE CHARACTER grade

READ score
IF score >= 90 THEN
	SET grade = 'A'
ELSE
	IF score >= 80 THEN
		SET grade = 'B'
	ELSE
		IF score >= 70 THEN
			SET grade = 'C'
		ENDIF
	ENDIF
ENDIF
WRITE grade
STOP
```
D.
```
START
DECLARE INTEGER score
DECLARE CHARACTER grade

READ score
IF score >= 90 THEN
	SET grade = 'A'
ELSE
	SET grade = 'B'
ELSE
	SET grade = 'C'
ENDIF
WRITE grade
STOP
```
**Answer: C**
