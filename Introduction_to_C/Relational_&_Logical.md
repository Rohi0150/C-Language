# C Language: Relational & Logical Operators

## Table of Contents
- [Relational Operators](#relational-operators)
- [Boolean Values in C](#boolean-values-in-c)
- [Relational Operator Examples](#relational-operator-examples)
- [Common Pitfall: Chaining Relational Operators](#common-pitfall-chaining-relational-operators)
- [Logical Operators](#logical-operators)
- [Truth Table](#truth-table)
- [Logical Operator Examples](#logical-operator-examples)
- [Operator Priority Order](#operator-priority-order)

---

## Relational Operators

C Language provides six relational operators:

| Operator | Description |
|----------|-------------|
| `>`      | Greater than |
| `<`      | Less than |
| `>=`     | Greater than or equal to |
| `<=`     | Less than or equal to |
| `==`     | Equal to |
| `!=`     | Not equal to |

---

## Boolean Values in C

**Important Note:** C language does not have a `bool` datatype (it exists in C++ and other languages).

In C:
- **True** is represented as `1` (int datatype)
- **False** is represented as `0` (int datatype)

---

## Relational Operator Examples
```c
4 > 3       // Returns 1 (true)
8 < 9       // Returns 1 (true)
-5 > -3     // Returns 0 (false)
3.5 > 4.5   // Returns 0 (false)
4 > 5       // Returns 0 (false)
4 < 5       // Returns 1 (true)
4 <= 5      // Returns 1 (true)
5 > 5       // Returns 0 (false)
5 < 5       // Returns 0 (false)
4 = 5       // L-value error (assignment, not comparison)
5 == 5      // Returns 1 (true)
```

---

## Common Pitfall: Chaining Relational Operators

### ⚠️ Problem Example
```c
void main() {
    int a;
    a = 4 > 3 > 2;
    printf("%d", a);
}
```

**Output:** `0`

### Why?

Most people think this statement checks if `4 > 3 > 2` is true, but that's **wrong**!

**Step-by-step evaluation:**
1. `4 > 3` → `1` (true)
2. `1 > 2` → `0` (false) ❌

**Conclusion:** In C, you **cannot** combine 2 relational operators directly.

### ✅ Solution

To combine 2 or more relational operators, use **Logical Operators**.

---

## Logical Operators

C provides three logical operators:

| Operator | Name | Description |
|----------|------|-------------|
| `!`      | Logical NOT | Negation |
| `&&`     | Logical AND | Both conditions must be true |
| `\|\|`   | Logical OR  | At least one condition must be true |

---

## Truth Table

| ARG1 | ARG2 | ARG1 && ARG2 | ARG1 \|\| ARG2 | !ARG1 | !ARG2 |
|------|------|--------------|----------------|-------|-------|
| 0    | 0    | 0            | 0              | 1     | 1     |
| 0    | 1    | 0            | 1              | 1     | 0     |
| 1    | 0    | 0            | 1              | 0     | 1     |
| 1    | 1    | 1            | 1              | 0     | 0     |

---

## Logical Operator Examples

### Logical AND (`&&`)

**Rule:** If both arguments are non-zero, the result is `1`
```c
a = 10 && 8;      // Returns 1 (true)
a = 0 && 7;       // Returns 0 (false)
a = 0.00 && 100;  // Returns 0 (false)
a = 7.2 && -8.2;  // Returns 1 (true)
```

**Important Note:** If the first argument is `0`, the second argument is **not evaluated** (short-circuit evaluation).
```c
a = 0 && ++a;  // ++a is NOT performed
```

### Logical OR (`||`)

**Rule:** If at least one argument is non-zero, the result is `1`
```c
a = 5 || 3;     // Returns 1 (true)
a = 0 || 6;     // Returns 1 (true)
a = 0 || 0.00;  // Returns 0 (false)
```

### Logical NOT (`!`)

**Rule:**
- `!(non-zero)` = `0`
- `!(zero)` = `1`
```c
!(-8)   // Returns 0
!(0.0)  // Returns 1
```

### Correct Solution to the Earlier Problem
```c
a = 4 > 3 && 3 > 2;  // Returns 1 (true) ✅
```

---

## Operator Priority Order

From highest to lowest priority:

| Priority | Operators | Description |
|----------|-----------|-------------|
| 1        | `!`       | Logical NOT |
| 2        | `*` `/` `%` | Multiplication, Division, Modulus |
| 3        | `+` `-`   | Addition, Subtraction |
| 4        | `>` `<` `>=` `<=` | Relational operators |
| 5        | `==` `!=` | Equality operators |
| 6        | `&&`      | Logical AND |
| 7        | `\|\|`    | Logical OR |
| 8        | `=`       | Assignment |

---

## Summary

- C uses `1` for true and `0` for false
- Relational operators cannot be chained directly
- Use logical operators (`&&`, `||`, `!`) to combine multiple conditions
- Logical operators support short-circuit evaluation
- Understanding operator precedence is crucial for correct expression evaluation

---
