# If-Else Conditional Construct

## 1. Concept and Introduction

The if-else construct is used when a program needs to perform a specific job if a condition is true and a different job if the condition is false.

- **Example**: In an ATM, if the PIN is correct, you login (true); if the PIN is incorrect, an error message is displayed (false).
- **Note**: `if` and `else` are separate keywords; "if-else" is the name of the concept, not a single keyword itself.

## 2. Syntax and Execution Flow

The basic structure is:

```c
if (condition) {
    // If body
} else {
    // Else body
}
```

- **True Condition**: The program executes the `if` body and then skips the `else` block to continue with the remaining statements.
- **False Condition**: The program skips the `if` body, executes the `else` block, and then continues with the remaining statements.
- **Always Executed**: Statements located above the `if` and below the `else` block will always execute regardless of whether the condition is true or false.

## 3. Truthiness in C

In C, the result of a condition is determined by numerical values:

- **Non-zero values** (e.g., 20, 1, -5) are treated as **true**.
- **Zero (0)** is treated as **false**.
- **Missing Conditions**: If no condition is provided (e.g., `if ()`), the compiler will throw an "expression syntax" error.

## 4. Body Rules and Compilation Errors

### Implicit Bodies

If curly braces `{}` are not provided, the body of an `if` or `else` statement is limited to the first statement ending in a semicolon.

### The "Misplaced Else" Rule

The `else` keyword must be written immediately after the `if` body.

- If there is any statement between the end of the `if` body and the `else` keyword, a compilation error such as "misplaced else" or "else without if" will occur.
- **Semicolon Warning**: Placing a semicolon immediately after an `if` condition (e.g., `if (3 > 2);`) effectively makes the `if` body empty. If a statement follows that semicolon before an `else`, it will cause a compilation error.

## 5. Logical Operators vs. Nested If-Else

To find the maximum of three integers (A, B, C), two main approaches can be used:

### Approach A: Logical Operators

Use `&&` (AND) to check multiple conditions at once.

```c
if (A > B && A > C) {
    max = A;
} else {
    // A is not max; check B and C
    if (B > C) 
        max = B; 
    else 
        max = C;
}
```

If both conditions are true, the result is 1 (true); if any condition fails, the result is 0 (false).

### Approach B: Nested If-Else

Check conditions one inside another.

```c
if (A > B) {
    if (A > C) 
        max = A; 
    else 
        max = C;
} else {
    if (B > C) 
        max = B; 
    else 
        max = C;
}
```

This logic systematically eliminates candidates until the maximum is found.

## 6. Important Pitfalls: Assignment vs. Comparison

A common source of errors is confusing the assignment operator (`=`) with the comparison operator (`==`).

- **Comparison (==)**: Checks if two values are equal and returns true or false. It does not change the value of the variable.
- **Assignment (=)**: Performs two jobs:
  1. Assigns the right-side value to the left-side variable.
  2. Replaces the entire expression with the assigned value.
     - **Example**: `if (a = 0)` assigns 0 to `a`. Since the expression is now 0 (false), the `else` block will execute.
     - **Example**: `if (a = 1)` assigns 1 to `a`. Since 1 is non-zero (true), the `if` block will execute.

### Data Type Truncation

When assigning a float to an integer variable (e.g., `int a = 0.75;`), the value is truncated. In this case, `a` becomes `0`, which is treated as false in a conditional.

## 7. Operator Priority

Logical operators like `&&` have higher priority than the assignment operator `=`.

- **Error Example**: `c = a && b = 30;` causes a compilation error ("L value required") because the compiler tries to assign 30 to the result of `(a && b)`, which is a constant value (0 or 1).
- **Solution**: Use parentheses to ensure the assignment happens first: `c = a && (b = 30);`.

---

## Summary

The if-else construct is fundamental to decision-making in C programming. Understanding truthiness, operator precedence, and common pitfalls like the assignment vs. comparison confusion will help you write robust conditional logic. Always be mindful of proper syntax and the placement of `else` keywords to avoid compilation errors.
