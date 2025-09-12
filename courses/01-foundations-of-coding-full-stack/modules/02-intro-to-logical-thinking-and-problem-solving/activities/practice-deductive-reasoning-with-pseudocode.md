# Activity: Practice Deductive Reasoning with Pseudocode

**Objective:** Use pseudocode to outline the logical flow of a program
by applying principles of deductive reasoning.
This process helps systematically solve problems
by breaking them down into premises, drawing conclusions,
and testing those conclusions.

**Description:** In this activity, you'll apply deductive reasoning to write pseudocode.
We'll start with two guided examples to illustrate the process. Then,
you'll solve two problems independently, outlining the logical flow
and writing the pseudocode to implement your solutions.

## Problem 1: Leap Year

**Problem Statement:**

You are tasked with creating a program to check if a given year is a leap year.
A year is a leap year if it is divisible by 4,
but not every year divisible by 100 is a leap year
unless it is also divisible by 400.

**Applying Deductive Reasoning:**

1. Identify the premises

   1. A year is a leap year if it is divisible by 4
   2. However, a year divisible by 100 is NOT a leap year
   3. UNLESS that year is also divisible by 400, in which case it IS a leap year

2. Analyze the premises

   These premises create a hierarchical decision structure:

   1. The basic rule is divisibility by 4
   2. This is overridden by divisibility by 100 (negating the leap year status)
   3. Which is itself overridden by divisibility by 400 (restoring the leap year status)

3. Draw conclusions

   Based on the analysis, the conditions for checking leap years
   can be structured logically to cover all cases.

4. Test the conclusions

   Examples to verify this logic:

   - 2020: Divisible by 4, not by 100 → Leap year
   - 1900: Divisible by 4 and 100, but not by 400 → Not a leap year
   - 2000: Divisible by 4, 100, and 400 → Leap year
   - 2022: Not divisible by 4 → Not a leap year

5. Explanation

   This logic creates a priority order for our conditional checks,
   with the more specific conditions (divisibility by 400, then divisibility by 100)
   taking precedence over the more general condition (divisibility by 4).

6. Pseudocode

   ```plaintext
   FUNCTION IsLeapYear(year):
       IF year is divisible by 400 THEN
           RETURN true
       ELSE IF year is divisible by 100 THEN
           RETURN false
       ELSE IF year is divisible by 4 THEN
           RETURN true
       ELSE
           RETURN false
       END IF
   END FUNCTION
   ```

   This pseudocode follows the hierarchical decision structure we identified:

   1. First, we check if the year is divisible by 400.
      If it is, it's a leap year regardless of other conditions.
   2. If it's not divisible by 400, we check if it's divisible by 100.
      If it is, it's not a leap year.
   3. If it's neither divisible by 400 nor 100, we check if it's divisible by 4.
      If it is, it's a leap year.
   4. If none of these conditions are met, it's not a leap year.

   The order of checks is crucial here.
   We start with the most specific override (divisibility by 400)
   and move to more general rules.
   This ensures that exceptions to rules are handled before the rules themselves.

## Problem 2: Simple Grading System

**Problem Statement:**

Imagine you are creating a program to determine the letter grade for a student
based on their numerical score. The grading system is as follows:

- A score of 90 or above is an "A".
- A score of 80 to 89 is a "B".
- A score of 70 to 79 is a "C".
- A score of 60 to 69 is a "D".
- A score below 60 is an "F".

**Applying Deductive Reasoning:**

1. Identify the premises

   1. A score ≥ 90 corresponds to grade "A"
   2. A score in range [80-89] corresponds to grade "B"
   3. A score in range [70-79] corresponds to grade "C"
   4. A score in range [60-69] corresponds to grade "D"
   5. A score < 60 corresponds to grade "F"

2. Analyze the premises

   These premises create a hierarchical structure based on numerical thresholds:

   1. Each grade has a minimum score threshold
   2. Grades are assigned in descending order (A, B, C, D, F) as scores decrease
   3. The ranges are mutually exclusive and collectively exhaustive, covering all possible scores
   4. The decision process can be structured as a series of comparisons against thresholds

3. Draw conclusions

   The deductive reasoning here involves checking if a given score meets or exceeds each threshold, starting from the highest grade's threshold, and working downward until a match is found.

4. Test the conclusions

   Test the logic with different scores to see if they fall
   into the correct grading category
   (e.g., 95 should be "A", 85 should be "B").

5. Explanation

   1. **Input:** The user is prompted to input a numerical score.
   2. **Conditional checks:** The score is checked against different ranges
      to determine the corresponding letter grade.
   3. **Output:** The program displays the letter grade based on the score.

6. Pseudocode

   ```plaintext
   FUNCTION DetermineGrade(score):
       IF score >= 90 THEN
           RETURN "A"
       ELSE IF score >= 80 THEN
           RETURN "B"
       ELSE IF score >= 70 THEN
           RETURN "C"
       ELSE IF score >= 60 THEN
           RETURN "D"
       ELSE
           RETURN "F"
       END IF
   END FUNCTION
   ```

   The pseudocode implements a cascade of conditional checks,
   evaluating from the highest threshold downward.
   Since each condition checks if the score is greater than or equal to a threshold,
   we don't need to explicitly specify the upper bounds of each range.
   This approach ensures a single,
   definitive grade is assigned to any possible numerical score.

## Problem 3: Integers

**Problem Statement:**

Write pseudocode to create a program that determines whether a number is positive,
negative, or zero.
Use deductive reasoning to establish the logical flow of the program.

**Applying Deductive Reasoning:**

1. Identify the premises

   1. A number can only be in one of three states: positive, negative, or zero
   2. A positive number is greater than zero
   3. A negative number is less than zero
   4. Zero is neither positive nor negative, it equals exactly zero

2. Analyze the premises

   These premises create a mutually exclusive and collectively exhaustive set of conditions:

   1. If a number is greater than zero, it must be positive
   2. If a number is less than zero, it must be negative
   3. If a number is neither greater than nor less than zero, it must equal zero

   The conditions are straightforward mathematical comparisons
   that can be directly implemented as conditional statements.

3. Draw conclusions

   Given the premises, we can deduce that:

   1. To determine if a number is positive, we check if it's greater than zero
   2. To determine if a number is negative, we check if it's less than zero
   3. If the number fails both tests, it must be zero

4. Test the conclusions

   Let's verify this with sample values:

   - For input 5: 5 > 0, so it's positive
   - For input -3: -3 < 0, so it's negative
   - For input 0: 0 is not > 0 and not < 0, so it's zero

5. Explanation

   The solution uses a simple hierarchy of conditional checks:

   1. First, check if the number is greater than zero (positive)
   2. If not, check if it's less than zero (negative)
   3. If neither condition is true, the number must be zero

   This covers all possible numeric inputs with no overlapping conditions.

6. Pseudocode

   ```plaintext
   FUNCTION DetermineNumberSign(number):
        IF number > 0 THEN
            RETURN "Positive"
        ELSE IF number < 0 THEN
            RETURN "Negative"
        ELSE
            RETURN "Zero"
        END IF
    END FUNCTION
   ```

   This pseudocode implements the logical flow derived from our deductive reasoning,
   providing a clear and concise solution
   that correctly categorizes any number as positive, negative, or zero.

## Problem 4: Senior Discount

**Problem Statement:**

Write pseudocode to create a program that checks
whether a person is eligible for a senior citizen discount.
The program should take the person's age as input.
If the age is 65 or older, print "Eligible for senior discount";
otherwise, print "Not eligible for senior discount".

**Applying Deductive Reasoning:**

1. Identify the premises

   1. A person is eligible for a senior citizen discount if they are 65 years or older
   2. A person is not eligible for a senior citizen discount if they are younger than 65
   3. The program takes a person's age as input

2. Analyze the premises

   This creates a binary classification based on a single threshold:

   1. The threshold value is age 65
   2. Ages equal to or above this threshold qualify for the discount
   3. Ages below this threshold do not qualify for the discount

3. Draw conclusions

   We can deduce that:

   1. If a person's age is greater than or equal to 65, they are eligible
   2. If a person's age is less than 65, they are not eligible

4. Test the conclusions

   Let's check some examples:

   - For input 70: 70 ≥ 65, so "Eligible for senior discount"
   - For input 65: 65 = 65, so "Eligible for senior discount"
   - For input 64: 64 < 65, so "Not eligible for senior discount"

5. Explanation

   The solution requires a single conditional check against the age threshold of 65:

   - If the age meets or exceeds 65, the person is eligible
   - Otherwise (if age is less than 65), the person is not eligible

6. Pseudocode

   ```plaintext
   FUNCTION CheckSeniorDiscountEligibility(age):
        IF age >= 65 THEN
            PRINT "Eligible for senior discount"
        ELSE
            PRINT "Not eligible for senior discount"
        END IF
    END FUNCTION
   ```

   This pseudocode implements a straightforward conditional check based on our deductive reasoning,
   producing the correct output message for any given age input.
