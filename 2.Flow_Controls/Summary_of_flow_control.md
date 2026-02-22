# Summary of Flow Control in C

This document provides a comprehensive overview of flow control mechanisms in C, including their classification, purpose, and usage.

---

## Definition

**Flow control** refers to the **order in which the statements are executed** or the **order of execution of statements** within a program.

---

## Classification of Flow Control

Flow control is broadly divided into **two main categories**: **Conditional** and **Unconditional**.

```
Flow Control
│
├── Conditional
│   ├── Selective
│   │   ├── if
│   │   ├── if-else
│   │   ├── Conditional Operator (?:)
│   │   └── switch
│   │
│   └── Iterative
│       ├── while
│       ├── for
│       └── do-while
│
└── Unconditional
    ├── goto
    ├── break
    ├── continue
    └── return
```

---

## 1. Conditional Flow Control

Conditional flow control is further subdivided into two types: **Selective** and **Iterative**.

---

### A. Selective Flow Control

In selective flow control, **specific pieces of code are selected for execution based on a condition**.

#### `if` Statement

If the condition is **true**, the statement is executed; otherwise, it is not.

```c
if (condition) {
    // Execute this block if condition is true
}
```

**Example:**
```c
int a = 5;
if (a > 3) {
    printf("a is greater than 3");
}
```

---

#### `if-else` Statement

Allows for a **choice between two paths**—executing one block if the condition is true and another if it is false.

```c
if (condition) {
    // Execute if true
} else {
    // Execute if false
}
```

**Example:**
```c
int a = 2;
if (a > 3) {
    printf("Greater");
} else {
    printf("Not Greater");
}
```

---

#### Conditional Operator (`?:`)

A **shorthand way** to handle simple conditional selections.

```c
result = (condition) ? value_if_true : value_if_false;
```

**Example:**
```c
int a = 5, b = 3;
int max = (a > b) ? a : b;  // max = 5
```

---

#### `switch` Statement

Used when there are **multiple (n) choices** available, allowing the selection of a single choice among them.

```c
switch (expression) {
    case constant1:
        // Code
        break;
    case constant2:
        // Code
        break;
    default:
        // Code
}
```

**Example:**
```c
int choice = 2;
switch (choice) {
    case 1:
        printf("One");
        break;
    case 2:
        printf("Two");
        break;
    default:
        printf("Other");
}
```

---

### B. Iterative Flow Control

**Iteration** occurs when the program reaches the end of a loop and needs to **return to the starting point** of that loop.

#### `while` Loop

Checks the condition **before** executing the loop body. Executes **zero or more times**.

```c
while (condition) {
    // Loop body
}
```

**Example:**
```c
int i = 1;
while (i <= 5) {
    printf("%d ", i);
    i++;
}
// Output: 1 2 3 4 5
```

---

#### `for` Loop

Compact loop structure with initialization, condition, and increment/decrement in one line. Ideal when the **number of iterations is known**.

```c
for (initialization; condition; increment) {
    // Loop body
}
```

**Example:**
```c
for (int i = 1; i <= 5; i++) {
    printf("%d ", i);
}
// Output: 1 2 3 4 5
```

---

#### `do-while` Loop

Checks the condition **after** executing the loop body. Executes **at least once**.

```c
do {
    // Loop body
} while (condition);
```

**Example:**
```c
int i = 1;
do {
    printf("%d ", i);
    i++;
} while (i <= 5);
// Output: 1 2 3 4 5
```

---

## 2. Unconditional Flow Control

Unconditional flow control statements **redirect the program's execution** without checking a specific true/false condition at that moment.

---

### `goto` Statement

Takes the control from **one specific place to another place** within the same function.

```c
goto label;
// Code (skipped)
label:
    // Code (executed)
```

**Example:**
```c
printf("A");
goto skip;
printf("B");  // Skipped
skip:
printf("C");
// Output: AC
```

**Use Cases:**
- Exiting nested loops
- Error handling and cleanup

**Warning:** Can lead to "spaghetti code" if overused.

---

### `break` Statement

Used to **immediately come out of** a loop or a switch statement.

```c
while (condition) {
    if (exit_condition) {
        break;  // Exit loop
    }
}
```

**Example:**
```c
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break;  // Exit when i is 5
    }
    printf("%d ", i);
}
// Output: 1 2 3 4
```

**Valid in:**
- `while` loop
- `for` loop
- `do-while` loop
- `switch` statement

---

### `continue` Statement

Used to **skip the current iteration** and move directly to the **next iteration** of a loop.

```c
while (condition) {
    if (skip_condition) {
        continue;  // Skip to next iteration
    }
    // Code
}
```

**Example:**
```c
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;  // Skip iteration when i is 3
    }
    printf("%d ", i);
}
// Output: 1 2 4 5
```

**Valid in:**
- `while` loop
- `for` loop
- `do-while` loop

**Not valid in:** `switch` statement (unless switch is inside a loop)

---

### `return` Statement

This statement is used to **return control from a function**. It can optionally return a value to the calling function.

```c
int function_name() {
    // Code
    return value;  // Return value and exit function
}
```

**Example:**
```c
int add(int a, int b) {
    return a + b;  // Return sum
}

int main() {
    int result = add(5, 3);  // result = 8
    return 0;  // Return from main
}
```

> **Note:** Detailed discussion on `return` is usually handled within the "Functions" concept.

---

## Comparison Table

### Selective vs. Iterative

| Feature           | Selective Flow Control                  | Iterative Flow Control                    |
|-------------------|-----------------------------------------|-------------------------------------------|
| **Purpose**       | Choose which code to execute            | Repeat code multiple times                |
| **Statements**    | `if`, `if-else`, `?:`, `switch`        | `while`, `for`, `do-while`               |
| **Condition**     | Evaluated once                          | Evaluated repeatedly                      |

### Conditional vs. Unconditional

| Feature           | Conditional Flow Control                | Unconditional Flow Control                |
|-------------------|-----------------------------------------|-------------------------------------------|
| **Condition**     | Requires a condition to be evaluated    | No condition evaluation required          |
| **Statements**    | `if`, `else`, `?:`, `switch`, loops    | `goto`, `break`, `continue`, `return`    |
| **Execution**     | Based on true/false evaluation          | Direct jump or control transfer           |

---

## Quick Reference

### When to Use What?

| Scenario                                      | Use                    |
|-----------------------------------------------|------------------------|
| Execute code only if condition is true        | `if`                   |
| Choose between two blocks                     | `if-else`              |
| Simple conditional assignment                 | `?:`                   |
| Multiple discrete choices (menu)              | `switch`               |
| Repeat with known iterations                  | `for`                  |
| Repeat with unknown iterations                | `while`                |
| Execute at least once                         | `do-while`             |
| Exit loop/switch immediately                  | `break`                |
| Skip current iteration                        | `continue`             |
| Jump to specific location                     | `goto`                 |
| Exit function and return value                | `return`               |

---

## Summary

Flow control mechanisms in C provide the tools necessary to create dynamic, responsive programs. Understanding the distinction between conditional and unconditional control, as well as selective versus iterative execution, is fundamental to writing effective C code.

**Key Points:**
- **Conditional flow control**: Execution depends on conditions (selective) or repetition (iterative)
- **Unconditional flow control**: Direct control transfer without condition evaluation
- **Selective**: Choose which code to execute (`if`, `if-else`, `?:`, `switch`)
- **Iterative**: Repeat code (`while`, `for`, `do-while`)
- **Jump statements**: Alter normal flow (`goto`, `break`, `continue`, `return`)

---

**Happy Coding! 🚀**
