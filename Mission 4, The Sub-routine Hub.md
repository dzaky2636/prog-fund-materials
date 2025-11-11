# Mission 4: The Sub-routine Hub

Cadet, so far the algorithms we've written have been one long block of code from top to bottom. This works, but it's highly inefficient. Imagine having to rewrite "calculate tax" code 10 times in different places? That's repetitive and bug-prone.

Welcome to the "Sub-routine Hub". Here we'll learn **Modularization**, the art of breaking down complex problems into smaller, manageable, and reusable components.

## 1. What is Modularization?
**Modularization** is the process of dividing a large algorithm into several smaller modules (or *sub-routines*). Each module is designed to perform **one specific task** (for example, `Calculate_Gross_Pay`, `Print_Error_Message`).

The main program (often called the *mainline*) then "calls" these modules when needed, instead of trying to do everything itself.

As programming problems become more complex, it becomes increasingly difficult to consider the solution as a whole. When presented with a complex problem, you need to divide the problem into smaller parts.
![Diagram Program Monolitik vs Program Modular](https://i.imgur.com/t2z6EM8.png)
### Benefits of Modular Design
* **Ease of Understanding:** It's much easier to understand one small module that does one thing than one massive block of code that does 20 things. Each module should perform just one function.
* **Reusable Code:** The `Calculate_Tax` module you write can be used in other programs without needing to rewrite it. Modules used in one program can also be used in other programs.
* **Elimination of Redundancy:** If you need to calculate tax in 5 places, you simply call the `Calculate_Tax` module 5 times, instead of copy-pasting the code. This helps avoid repetition of writing the same code segment more than once.
* **Efficiency of Maintenance:** If there's a change in how taxes are calculated, you only need to fix it in **one place** (inside the `Calculate_Tax` module), and all parts of the program will be automatically updated. Each module should be self-contained and have little or no effect on other modules within the program.

---
## 2. Modularization in Flowcharts
![Flowchart dengan Simbol Predefined Process](https://i.imgur.com/F7C97Vj.png)
In *flowcharts*, we use the **Predefined Process** symbol to represent a module. This symbol looks like a rectangle with two vertical lines inside it.

When the main flow reaches this symbol, the logic will "jump" to a separate *flowchart* for that module, execute it, then return to the main flow.

The predefined process symbol represents a module in an algorithm – that is, a predefined process that has its own flowchart.

---
## 3. Module Names and Design Principles
A module's name should be **descriptive enough** so that anyone reading your code can reasonably guess what the module does.

Because modules **perform actions**, most programmers prefer to use **verbs** in module names. For example, a module that calculates gross pay might be named `calculateGrossPay`.

**Important naming rules:**
- Module names **cannot contain spaces**
- Cannot typically contain punctuation characters  
- Usually cannot begin with a number

---
## 4. Communication Between Modules
When the main module calls a sub-module, how do they communicate? There are several ways:

### A. Scope of Variables
* **Global Data:** Variables defined in the main program that can be used by all modules. The scope of a global variable is the whole program.
* **Local Data:** Variables defined within a submodule. The scope of a local variable is limited to the execution of the single submodule in which it is defined.

### B. Passing Parameters (Best Practice)
The best way to communicate is by **passing parameters** (arguments). The main module "gives" the sub-module the data it needs to work.

Parameters are data items transferred from a calling module to its subordinate module at the time of calling.

**Two types of parameter passing:**
* **Passing by Value:** You give a **copy** of the data to the module. If the module changes that data, the original data in the main program **does not** change.
* **Passing by Reference:** You give the **memory address** of the data. If the module changes that data, the original data in the main program **also changes**.
### Example: From Monolithic to Modular
**Non-modular (monolithic) algorithm:**
```pseudocode
DECLARE hours_worked AS INTEGER
DECLARE hourly_rate AS REAL
DECLARE weekly_pay AS REAL
DECLARE overtime_hours AS INTEGER
DECLARE overtime_pay AS REAL

START
READ hours_worked
READ hourly_rate

IF hours_worked <= 35 THEN
    SET weekly_pay = hourly_rate * hours_worked
ELSE
    SET overtime_hours = hours_worked - 35
    SET overtime_pay = overtime_hours * hourly_rate * 1.5
    SET weekly_pay = (hourly_rate * 35) + overtime_pay
ENDIF

WRITE weekly_pay
STOP
```

**Now, let's make it modular:**
```pseudocode
// Main Program (Mainline)
DECLARE hours_worked AS INTEGER
DECLARE hourly_rate AS REAL

START
READ hours_worked
READ hourly_rate

// Call module and pass parameters
Calculate_Employee_Pay(hours_worked, hourly_rate)
STOP
```

```pseudocode
// --- Separate Module Definition ---
MODULE Calculate_Employee_Pay(hours, rate)
    DECLARE weekly_pay AS REAL
    DECLARE overtime_hrs AS INTEGER
    DECLARE overtime_pay AS REAL

    IF hours <= 35 THEN
        SET weekly_pay = rate * hours
    ELSE
        SET overtime_hrs = hours - 35
        SET overtime_pay = overtime_hrs * rate * 1.5
        SET weekly_pay = (rate * 35) + overtime_pay
    ENDIF
    
    WRITE weekly_pay
END MODULE
```

See how much cleaner the main program is? All the complex calculation logic has been "hidden" within its own module.

---
## 5. Hierarchy Charts
Once tasks have been grouped into functions or modules, these modules can be represented graphically in a **hierarchy chart** (also called a **structure chart**).

This diagram shows not only the names of all modules but also their **hierarchical relationship** to each other. The hierarchy chart uses a tree-like diagram of boxes where:
- Each box represents a module in the program
- Lines connecting the boxes represent the relationship of modules to others in the program hierarchy

### Steps in Modularization
1. **Define the problem** by dividing it into its three components: input, output, and processing
2. **Group the activities** into subtasks or functions to determine the modules that will make up the program
3. **Construct a hierarchy chart** to illustrate the modules and their relationship to each other
4. **Establish the logic** of the mainline of the algorithm in pseudocode/flowchart
5. **Develop the pseudocode/flowchart** for each successive module in the hierarchy chart
6. **Desk check** the solution algorithm

## QUIZ

**Q1: What is the main benefit of Modularization?**
A. Makes programs run faster.
B. Uses less memory.
C. Breaks large programs into small, manageable, maintainable, and reusable parts.
D. Eliminates the need for IF-THEN-ELSE statements.
**Answer: C**

**Q2: In a Flowchart, which symbol is used to represent a module (sub-routine) call?**
A. Diamond (Decision)
B. Parallelogram (Input/Output)
C. Rectangle with two vertical lines (Predefined Process)
D. Circle (Connector)
**Answer: C**

**Q3: What does "Passing by Value" mean?**
A. The module changes the original data in the main program.
B. The module receives a copy of the data, and changes within the module do not affect the original data.
C. The module can only receive one value.
D. The module can only be used once.
**Answer: B**

**Q4: Variables defined within a module and can only be used within that module are called...**
A. Global Variables
B. Parameter Variables
C. Constant Variables
D. Local Variables
**Answer: D**

**Q5: (Logic Challenge) Consider this pseudocode:**
```pseudocode
MODULE AddOne(counter)
    SET counter = counter + 1
END MODULE

// Main Program
DECLARE my_value AS INTEGER

START
SET my_value = 5
AddOne(my_value) // Assume this is 'Passing by Value'
WRITE my_value
STOP
```
**What is the output from the main program?**
A. 6
B. 5
C. 1
D. Error
**Answer: B** (Explanation: Because my_value is passed "by value", the AddOne module only changes a copy of that value. The original my_value variable in the main program remains 5.)

**Q6: What is a hierarchy chart used for?**
A. To show the execution time of modules
B. To represent the graphical relationship between modules in a program
C. To display input and output data
D. To show memory usage of the program
**Answer: B**

**Q7: Which of the following is NOT a step in modularization?**
A. Define the problem by dividing it into input, output, and processing
B. Group activities into subtasks or functions
C. Write the entire program in one large module
D. Construct a hierarchy chart
**Answer: C**