# Remedial Mission: Building Blocks 101
Hello Cadet! M.E.C.H.A. has detected anomalies in data transfer during the last mission. Our modules aren't communicating properly. This is a common issue related to *how* we send data between modules.

Let's review the two main ways to send data: **Pass-by-Value** and **Pass-by-Reference**. Understanding these is key to building robust *sub-routines*.

## 1. Pass-by-Value (Passing a Copy)
This is the most common and safest way to send data.

* **Analogy:** Imagine you have an important note. Instead of giving your *original* note to M.E.C.H.A., you **make a copy (photocopy)** of that note and give it to me.
* **Explanation:** I can take that copy, scribble on it, or even burn it. What happens to your original note? **Nothing!** Your *original* note remains safe and unchanged in your hands.
* **Technical Concept:** When you call a module with *pass-by-value*, the computer makes a **copy** of your variable's value and gives it to the module. The module works using that copy. Any changes to the value inside the module are lost when the module finishes, and your original variable in the main program remains intact.

**Failed Example from Last Mission:**
```pseudocode
MODULE AddOne(counter) // 'counter' here is a COPY
    SET counter = counter + 1 // This changes the copy, not the original
END MODULE

// Main Program
SET my_value = 5
AddOne(my_value) // We send '5', not the variable 'my_value'
WRITE my_value
```
**The output is `5`**, because the original `my_value` was never changed.

---
## 2. Pass-by-Reference (Passing an Address)
This is a more powerful, but also more "dangerous", way to send data.

- **Analogy:** Instead of giving me a copy of the note, you give me the **address (location) of the safe** where you store your original note.
- **Explanation:** I now have direct access to your _original_ safe. If I go to that location, open the safe, and change the note inside, then your **original** note has been changed.
- **Technical Concept:** When you call a module with _pass-by-reference_ (often marked with `REF` or `&`), the computer gives the **memory address** of your original variable to the module. The module can now directly access and modify the data at that address. These changes are **permanent** and will be visible in the main program.

**Successful Example (Fixing Last Mission):**
```pseudocode
MODULE AddOne(REF counter) // 'REF' means we receive an ADDRESS
    SET counter = counter + 1 // This changes data at the original address
END MODULE

// Main Program
SET my_value = 5
AddOne(my_value) // We send the address of 'my_value'
WRITE my_value
```
**The output is now `6`**, because the module directly changed the original `my_value` variable.

---
### When to Use Each?
- Use **Pass-by-Value** (default) if you only want the module to _read_ data or use it for calculations.
- Use **Pass-by-Reference** if the module's purpose is to _change_ the original variable's value.

Let's make sure this concept sticks!

## QUIZ

**Q1: What is actually sent to a module when using 'Pass-by-Value'?**
A. The memory address of the original variable.
B. A copy (photocopy) of the variable's value.
C. The original variable itself.
D. The variable name.
**Answer: B**

**Q2: What is actually sent to a module when using 'Pass-by-Reference'?**
A. The memory address of the original variable.
B. A copy (photocopy) of the variable's value.
C. The original variable itself.
D. The variable name.
**Answer: A**

**Q3: Consider this pseudocode:**
```pseudocode
MODULE ChangeValue(REF value_x)
    SET value_x = 100
END MODULE

// Main Program
SET my_number = 25
ChangeValue(my_number)
WRITE my_number
```
**What is the output?**
A. 25
B. 100
C. 0
D. Error
**Answer: B** (Explanation: Because it uses REF (Pass-by-Reference), the ChangeValue module changes the original my_number variable.)

**Q4: When should you use 'Pass-by-Reference'?**
A. When you don't want the original value to change.
B. When you want the module to return more than one value or change the original variable's value.
C. When you only want to print values.
D. When you're working with numbers, not text.
**Answer: B**

**Q5: Consider this pseudocode (this is tricky!):**
```pseudocode
MODULE ChangeValue(value_x) // Notice, no 'REF'
    SET value_x = 100
END MODULE

// Main Program
SET my_number = 25
ChangeValue(my_number)
WRITE my_number
```
**What is the output?**
A. 25
B. 100
C. 0
D. Error
**Answer: A** (Explanation: Because there's no REF, the system uses the default, which is Pass-by-Value. The module only changes a copy of my_number.)

**Q6: Which parameter passing method is considered safer?**
A. Pass-by-Reference
B. Pass-by-Value
C. Both are equally safe
D. Neither is safe
**Answer: B**

**Q7: If you want a module to calculate a result without modifying the input data, which method should you use?**
A. Pass-by-Reference
B. Pass-by-Value
C. Global variables only
D. Local variables only
**Answer: B**