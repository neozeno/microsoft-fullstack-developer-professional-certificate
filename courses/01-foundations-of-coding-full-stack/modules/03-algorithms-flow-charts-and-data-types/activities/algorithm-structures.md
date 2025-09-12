# Implementing Conditional and Binary-Decision Structures

**Objective:** Demonstrate how developers can use conditional (if/then)
and binary-decision structures to manage and navigate choices in programming.

**Description:** This activity involves analyzing scenarios, selecting
appropriate algorithm structures, and then writing pseudocode
to implement those structures.

## Problem 1: Discount Eligibility

**Scenario:** You are tasked with creating a program to determine if
a customer is eligible for a discount. The program should check the total
amount a customer has spent and decide if they qualify for a discount.

**Instructions:**
1. Write a program that takes the total spending amount as input.
2. If the customer has spent $100 or more, print "10% discount applied."
3. If the customer has spent less than $100, print "No discount."

### Discount Eligibility Problem Solution

#### Problem Statement

Create a program that determines customer discount eligibility based on their
total spending amount. The system needs to evaluate whether a customer
qualifies for a 10% discount by checking if their total spending meets or
exceeds $100.

**Requirements:**
- Accept total spending amount as input
- Apply 10% discount for spending ≥ $100
- No discount for spending < $100
- Provide clear feedback to customer

#### Identify Key Processes

**Input Process:**
- Receive customer's total spending amount
- Validate input is a valid monetary value

**Decision Process:**
- Compare spending amount against $100 threshold
- Determine discount eligibility using conditional logic

**Output Process:**
- Display appropriate discount message
- Inform customer of their discount status

**Data Flow:**
- Input: Total spending amount
- Comparison: Amount vs. $100 threshold
- Decision: Eligible or not eligible
- Output: Discount message

#### Explanation

This problem uses a conditional statement structure (if/then) to make a
binary decision based on a single criterion. The algorithm follows a simple
decision tree where the spending amount is evaluated against a fixed
threshold.

**Logic Flow:**

- The program receives the total spending amount as input
- It compares this amount to the $100 threshold using a conditional statement
- If the condition (spending ≥ $100) is true, it applies the 10% discount
- If the condition is false, no discount is applied
- The program outputs the appropriate message based on the decision

**Algorithm Type:** This is a straightforward conditional algorithm that
demonstrates binary decision-making. There are only two possible outcomes,
making it an ideal example of if/else conditional logic.

**Real-world Application:** This type of logic is commonly used in e-commerce
systems, loyalty programs, and point-of-sale systems where automatic
discounts are applied based on purchase thresholds.

#### Pseudocode

```
BEGIN DiscountEligibility

  // Input Process
  PRINT "Enter total spending amount: $"
  INPUT totalSpending
  
  // Validation (optional but good practice)
  IF totalSpending < 0 THEN
      PRINT "Invalid amount. Please enter a positive value."
      EXIT
  END IF
  
  // Decision Process - Discount Eligibility Check
  IF totalSpending >= 100 THEN
      PRINT "10% discount applied."
  ELSE
      PRINT "No discount."
  END IF

END DiscountEligibility
```

Alternative implementation with more detail:

```
BEGIN EnhancedDiscountEligibility

    PRINT "=== Discount Eligibility Checker ==="
    PRINT "Enter your total spending amount: $"
    INPUT totalSpending
    
    // Input validation
    WHILE totalSpending < 0 DO
        PRINT "Please enter a valid positive amount: $"
        INPUT totalSpending
    END WHILE
    
    // Discount calculation and messaging
    IF totalSpending >= 100 THEN
        discount = totalSpending * 0.10
        finalAmount = totalSpending - discount
        PRINT "Congratulations! 10% discount applied."
        PRINT "Discount amount: $" + discount
        PRINT "Final amount: $" + finalAmount
    ELSE
        PRINT "No discount available."
        PRINT "Spend $" + (100 - totalSpending) + " more to qualify!"
    END IF

END EnhancedDiscountEligibility
```

## Problem 2: Book Categorization

**Scenario:** A library needs to categorize books based on their genre.
You need to develop a program that helps categorize each book correctly.

**Instructions:**
1. Write a program that takes the genre of a book as input.
2. If the genre is "Fiction," print "Category: Fiction."
3. If the genre is "Non-Fiction," print "Category: Non-Fiction."
4. If the genre is "Science Fiction," print "Category: Science Fiction."
5. If the genre does not match any of these, print "Category: Unknown."

### Book Categorization Problem Solution

#### Problem Statement

Create a program that categorizes library books based on their genre input.
The system needs to classify books into predefined categories and handle
unknown genres appropriately.

**Requirements:**

- Accept book genre as input
- Categorize into: Fiction, Non-Fiction, Science Fiction
- Handle unknown genres with default category
- Provide clear categorization feedback

**Expected Outputs:**

- "Fiction" → "Category: Fiction"
- "Non-Fiction" → "Category: Non-Fiction"
- "Science Fiction" → "Category: Science Fiction"
- Any other input → "Category: Unknown"

#### Key Processes

**Input Process:**

- Receive book genre as text input
- Handle case sensitivity considerations
- Validate input is not empty

**Classification Process:**

- Compare input against known genre categories
- Match exact genre strings
- Determine appropriate category assignment

**Decision Process:**

- Use multi-way conditional logic (switch-like structure)
- Check each known genre sequentially
- Default to "Unknown" for unmatched inputs

**Output Process:**

- Display formatted category message
- Maintain consistent output format

#### Explanation

This problem uses a *multi-way conditional statement structure* (if/else if/
else chain) to handle multiple possible outcomes. Unlike binary decisions,
this algorithm evaluates against several specific criteria before reaching a
default case.

**Logic Flow:**

- The program receives a genre string as input
- It compares this input against three known categories sequentially
- Each comparison checks for an exact match with predefined genre names
- If a match is found, the corresponding category message is displayed
- If no matches are found, the default "Unknown" category is assigned

**Algorithm Type:** This demonstrates categorical classification logic
where data is sorted into predefined groups based on specific attributes.
It's essentially a switch statement implemented with if/else if chains.

**Key Considerations:**

- Case sensitivity: "fiction" vs "Fiction" - should be handled
- Input validation: Empty strings or null inputs
- Exact matching: "Sci-Fi" wouldn't match "Science Fiction"
- Extensibility: Easy to add new genres by adding more conditions

**Real-world Application:** This pattern is widely used in content management
systems, inventory categorization, data classification, and any system
requiring organized data grouping.

#### Pseudocode

```
BEGIN BookCategorization

    // Input Process
    PRINT "Enter book genre: "
    INPUT bookGenre
    
    // Input validation
    IF bookGenre IS EMPTY THEN
        PRINT "Category: Unknown"
        EXIT
    END IF
    
    // Convert to consistent case for comparison
    bookGenre = TRIM(bookGenre)
    
    // Classification Process - Multi-way Conditional
    IF bookGenre EQUALS "Fiction" THEN
        PRINT "Category: Fiction"
    ELSE IF bookGenre EQUALS "Non-Fiction" THEN
        PRINT "Category: Non-Fiction"
    ELSE IF bookGenre EQUALS "Science Fiction" THEN
        PRINT "Category: Science Fiction"
    ELSE
        PRINT "Category: Unknown"
    END IF

END BookCategorization
```

Enhanced implementation with case-insensitive matching:

```
BEGIN EnhancedBookCategorization

    PRINT "=== Library Book Categorization System ==="
    PRINT "Enter the book's genre: "
    INPUT bookGenre
    
    // Input validation and preprocessing
    IF bookGenre IS EMPTY OR bookGenre IS NULL THEN
        PRINT "Error: No genre provided."
        PRINT "Category: Unknown"
        EXIT
    END IF
    
    // Normalize input - remove extra spaces and convert to title case
    bookGenre = TRIM(bookGenre)
    bookGenre = TO_TITLE_CASE(bookGenre)
    
    // Classification with detailed feedback
    IF bookGenre EQUALS "Fiction" THEN
        PRINT "Category: Fiction"
    ELSE IF bookGenre EQUALS "Non-Fiction" THEN
        PRINT "Category: Non-Fiction"
    ELSE IF bookGenre EQUALS "Science Fiction" THEN
        PRINT "Category: Science Fiction"
    ELSE
        PRINT "Category: Unknown"
        PRINT "Please consult librarian for proper classification"
        PRINT "Entered genre: '" + bookGenre + "'"
    END IF

END EnhancedBookCategorization
```

Switch statement alternative:

```
BEGIN BookCategorizationSwitch

    INPUT bookGenre
    bookGenre = TRIM(TO_TITLE_CASE(bookGenre))
    
    SWITCH bookGenre:
        CASE "Fiction":
            PRINT "Category: Fiction"
            BREAK
        CASE "Non-Fiction":
            PRINT "Category: Non-Fiction"
            BREAK
        CASE "Science Fiction":
            PRINT "Category: Science Fiction"
            BREAK
        DEFAULT:
            PRINT "Category: Unknown"
            BREAK
    END SWITCH

END BookCategorizationSwitch
```

## Problem 3: Even or Odd Number

**Scenario:** You need to create a program that determines whether a given
number is even or odd.

**Instructions:**
1. Write a program that takes a number as input.
2. If the number is even, print "Even number."
3. If the number is odd, print "Odd number."

### Even or Odd Number Problem Solution

#### Problem Statement

Create a program that determines whether a given number is even or odd. The
system needs to evaluate any integer input and classify it into one of two
categories based on its mathematical properties.

**Requirements:**

- Accept any integer as input
- Determine if the number is even or odd
- Provide clear classification feedback
- Handle the mathematical logic correctly

**Expected Outputs:**

- Even numbers (2, 4, 6, 8...) → "Even number."
- Odd numbers (1, 3, 5, 7...) → "Odd number."

#### Key Processes

**Input Process:**

- Receive integer value from user
- Validate input is a valid number
- Handle negative numbers appropriately

**Mathematical Analysis Process:**

- Apply modulo operation (remainder division)
- Check remainder when divided by 2
- Determine even/odd based on remainder value

**Decision Process:**

- Use binary conditional logic (if/else)
- Evaluate remainder result (0 = even, 1 = odd)
- Select appropriate output message

**Output Process:**

- Display classification result
- Maintain consistent message format

#### Explanation

This problem uses a binary conditional statement structure combined with
mathematical modulo operation to classify numbers into two mutually
exclusive categories. The algorithm leverages the fundamental mathematical
property that even numbers are divisible by 2 with no remainder.

**Mathematical Logic:**

- Even numbers: When divided by 2, remainder = 0 (e.g., 8 ÷ 2 = 4 R 0)
- Odd numbers: When divided by 2, remainder = 1 (e.g., 7 ÷ 2 = 3 R 1)
- Modulo operator (%): Returns the remainder of division operation

**Algorithm Flow:**

- The program receives an integer input
- It applies the modulo operation: `number % 2`
- If the result equals 0, the number is even
- If the result equals 1, the number is odd
- The appropriate message is displayed

**Algorithm Type:** This is a binary classification algorithm using
mathematical properties. It demonstrates how arithmetic operations can be
used within conditional statements to make logical decisions.

**Key Considerations:**

- Negative numbers: -4 % 2 = 0 (even), -3 % 2 = 1 (odd)
- Zero: 0 % 2 = 0, so zero is considered even
- Input validation: Ensure input is an integer

**Real-world Applications:** This pattern is used in array indexing,
pagination systems, alternating row colors in tables, load balancing
algorithms, and any system requiring alternating behavior.

#### Pseudocode

```
BEGIN EvenOddChecker

    // Input Process
    PRINT "Enter a number: "
    INPUT number
    
    // Input validation
    IF number IS NOT INTEGER THEN
        PRINT "Please enter a valid integer."
        EXIT
    END IF
    
    // Mathematical Analysis and Decision Process
    IF number % 2 = 0 THEN
        PRINT "Even number."
    ELSE
        PRINT "Odd number."
    END IF

END EvenOddChecker
```

Enhanced implementation with additional features:

```
BEGIN EnhancedEvenOddChecker

    PRINT "=== Even/Odd Number Checker ==="
    PRINT "Enter an integer: "
    INPUT userInput
    
    // Input validation and conversion
    IF userInput IS NOT NUMERIC THEN
        PRINT "Error: Please enter a valid integer."
        EXIT
    END IF
    
    number = CONVERT_TO_INTEGER(userInput)
    
    // Mathematical analysis with detailed feedback
    remainder = number % 2
    
    IF remainder = 0 THEN
        PRINT number + " is an even number."
        PRINT "Mathematical proof: " + number + " ÷ 2 = " + (number/2) + " R 0"
    ELSE
        PRINT number + " is an odd number."
        PRINT "Mathematical proof: " + number + " ÷ 2 = " + (number/2) + " R 1"
    END IF
END EnhancedEvenOddChecker
```

Alternative implementation using bitwise operations:

```
BEGIN BitwiseEvenOddChecker

    INPUT number
    
    // Bitwise AND operation with 1
    // Even numbers have 0 in the least significant bit
    // Odd numbers have 1 in the least significant bit
    IF (number & 1) = 0 THEN
        PRINT "Even number."
    ELSE
        PRINT "Odd number."
    END IF
    
    // Note: This is more efficient but less readable
    // number & 1 checks the last binary digit

END BitwiseEvenOddChecker
```

