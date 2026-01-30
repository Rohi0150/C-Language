# Basic Concepts of C Language

---

# 1️⃣ C Language vs English Language

Programming languages are structured just like human languages.

| English Language | C Language |
|------------------|------------|
| Alphabets (26) | Keywords (32) |
| Words | Operators (45) |
| Sentences | Separators (14) |
| Grammar | Syntax |

### Think About It
- Can we form correct English without grammar?
- Can we write a correct C program without syntax?

Both will produce errors.

---

# 2️⃣ Constants in C

A **constant** is a fixed value that does not change during program execution.

## 🔹 Types of Constants

### 1. Integer (int)
Whole numbers without decimal point.

Examples:
```
100
-25
0
```

---

### 2. Float (float)
Numbers with decimal point.

Examples:
```
6.2
-8.0
3.14
.3
```

---

### 3. Character (char)
A single character enclosed in single quotes. ' '

Examples:
```
'A'
'm'
'7'
```

---

## ✅ Valid Examples

```
100        → int
6.2        → float
-8.0       → float
'm'        → char
0          → int
25         → int
3.14       → float
'Z'        → char
```

---

## ❌ Invalid Examples

```
'3184'   → Error (char can store only one character)
abc      → Error (not declared, not in quotes)
'110.35' → Error (char can store only character)
k        → Error (Sinle Quote is missing)
 
```

---

## 🧠 Self Check

❓ Is `.3` valid in C?  
Yes. It is treated as `0.3` (float).

❓ Why is `'3184'` invalid?  
Because a `char` stores only one character.

---

# 3️⃣ Primitive Data Types

To represent any type of basic data in C, we use primitive data types:

- `int`
- `float`
- `char`

These are called **basic primitive data types**.

---

# 4️⃣ Format Specifiers

Format specifiers are used in `printf()` to display values.

| Data Type | Format Specifier |
|------------|------------------|
| int | %d or %i |
| float | %f |
| char | %c |

Example:

```c
#include <stdio.h>

int main() {
    int a = 10;
    float b = 5.2;
    char c = 'A';

    printf("%d %f %c", a, b, c);
    return 0;
}
```

`%d`, `%f`, `%c` are called **format specifiers**.

---

# 5️⃣ Assignment Operator (=)

The assignment operator is used to assign values to variables.

## Rules:

1. `=` must contain two operands.
2. The left side must be a variable.  
   → This is called **L-value**.
3. The right side can be:
   - Constant
   - Variable
   - Expression

---

## ✅ Valid Examples

```c
a = 5;        // constant
b = a;        // variable
c = 2 + 3;    // expression
```

Explanation:
- `5` is assigned to `a`
- Value of `a` is assigned to `b`
- Result of `2 + 3` is assigned to `c`

---

## ❌ Invalid Examples

```c
a = ;        // invalid
= 0;         // invalid
10 = 20;     // L-value error indicates Leftside value is required 
```

Why is `10 = 20;` invalid?

Because the left side must be a variable.  
A constant cannot receive a value.

---

# 🔁 Summary

- C follows strict syntax rules.
- Constants are fixed values.
- int, float, char are primitive data types.
- Format specifiers display values.
- Assignment operator requires a valid L-value.
