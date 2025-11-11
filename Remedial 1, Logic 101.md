# Remedial Mission: Logic 101

Hello Cadet, M.E.C.H.A. here. It seems there was a slight hiccup in the last mission. Don't worry! Let's go back to the fundamentals. Every algorithm, no matter how complex, always follows one core pattern: **Input, Process, Output**.

Let's review this concept.

## The I-P-O Model (Input-Process-Output)

Think of a computer as a "processing box." For that box to work, it needs three things:

1. **Input:** Raw data that we *provide* to the computer for processing. These are the "ingredients" of your recipe.
2. **Process:** The steps or instructions the computer performs to *transform* the input into something useful. This is the "cooking method" of your recipe.
3. **Output:** The finished result that is *displayed* by the computer after processing is complete. This is the "finished cake."

### Simple Example: Calculating Rectangle Area

Let's apply the I-P-O model to a simple problem: "Create a program to calculate the area of a rectangle."

* **What do we need to start? (Input):**
    We need to know the `length` and `width` of the rectangle.
* **What must the computer do? (Process):**
    It must perform a mathematical calculation: `area = length * width`.
* **What result do we want? (Output):**
    We want the computer to display the calculated `area` value.

### I-P-O Flowchart Pattern

Visually, the flow will always look like this:
![Flowchart I-P-O Sederhana](https://i.imgur.com/r5J9Brm.png)
1. **Start** (Oval)
2. **Input** `base`, `height` (Parallelogram)
3. **Process** `area = (base * height) / 2` (Rectangle)
4. **Output** `area` (Parallelogram)
5. **Stop** (Oval)

This pattern is the foundation of *all* algorithms we will build. If you can identify I-P-O, you can solve any problem.

Let's try a short quiz to make sure you understand!
## QUIZ

**Q1: You want to create an algorithm to calculate the total shopping price after discount. What would be the 'INPUT' for this algorithm?**
A. The final total price amount.
B. The discount formula (`price * 0.10`).
C. The original item price and discount percentage.
D. The "Start" symbol.
**Answer: C**

**Q2: Using the same scenario (calculating price after discount), what would be the 'PROCESS'?**
A. Displaying the final price on screen.
B. Calculating discount amount (`discount = original_price * discount_percent`) and final price (`final_price = original_price - discount`).
C. Reading the original price from the user.
D. Saving data to database.
**Answer: B**

**Q3: And finally, what would be the 'OUTPUT' of the discount price algorithm?**
A. The original item price.
B. The discount percentage.
C. The final price to be paid.
D. The calculation formula.
**Answer: C**

**Q4: What is the correct order of the I-P-O model?**
A. Process → Input → Output
B. Output → Process → Input
C. Input → Process → Output
D. Input → Output → Process
**Answer: C**

**Q5: In the I-P-O model, which component represents the "ingredients" or raw materials needed to solve a problem?**
A. Input
B. Process
C. Output
D. Algorithm
**Answer: A**

**Q6: When designing an algorithm to calculate employee salary (basic pay + overtime), what would be the INPUT components?**
A. The final salary amount
B. Basic pay rate, hours worked, and overtime rate
C. The salary calculation formula
D. The employee's name only
**Answer: B**