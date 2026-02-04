# C Programming Notes - Variables and Data Types

## Error: Undefined Symbol

```c
void main(){
    a = 5;
    printf("%d", a);
}
```

**Error:** `Undefined Symbol 'a'`

**Reason:** Whenever we are using a variable, we must define its datatype.

---

## Corrected Code

```c
void main(){
    int a;
    a = 5;
    printf("%d", a);
}
```

**Description:** `a` is a variable of integer type.

**Note:** We can assign any type of value to any type of datatype.

---

## Type Conversion Examples

### Example 1: Float Variable with Integer Value

```c
void main(){
    float f;
    f = 5;
    printf("%f", f);
}
// Output: 5.0
```

### Example 2: Integer Variable with Float Value

```c
void main(){
    int i;
    i = 5.5;
    printf("%d", i);
}
// Output: 5
```

### Example 3: Integer Division Assigned to Integer

```c
void main(){
    int i;
    i = 5/2;
    printf("%d", i);
}
// Output: 2
// Internally 5/2 -> 2.5 and printing the int value it prints 2
```

### Example 4: Integer Division Assigned to Float

```c
void main(){
    float f;
    f = 5/2;
    printf("%f", f);
}
// Output: 2.0
// Internally 5/2 converted into 2 and printing the float value 2.0
```

---

## Variable Declaration Methods

### Method 1 & 2 (Preferred)

```c
int a;  // a is variable of int
int b;  // b is variable of int
```

### Method 3

```c
int a, b;  // a & b are variables of int
```

**Why Method 1 & 2 are preferred:**
- We can change it in future
- Better for commenting purposes

---

## Variable Declaration Rules and Examples

### Valid Declarations

```c
int a1, a2, a3;  // Valid
```

### Invalid Declarations

```c
int 1a, 2a, 3a;  // Invalid - variable names cannot start with numbers
```

### Declaration vs Initialization

```c
int a;       // Garbage value is assigned to a
a = 5;       // Assignment of value 5 to variable a

int a = 5;   // Both declaration and initialization

int a = 7.5; // Output: 7 (decimal part truncated)

int a = 21/5/19;  // Order of precedence left to right
                  // 21/5 -> 4
                  // 4/19 -> 0

int a = 5+2;  // Output: 7
```

### Multiple Assignment - Invalid

```c
int a = b = c = 10;  // Invalid
```

**Correct way:**

```c
int a, b, c;
a = b = c = 10;  // 10 is assigned to c, then b, then a
```

### Multiple Assignment - Valid

```c
int a, b, c = b = a = 10;  // Valid
// a -> Garbage Value -> 10
// b -> Garbage Value -> 10
// c = 10
```

---

## Declaration Edge Cases

| Declaration | Validity | Reason |
|------------|----------|---------|
| `int a = a;` | Valid | Syntactically correct but no use (Garbage value to garbage value) |
| `int a, a;` | Invalid | Multiple declarations |
| `int a, A;` | Valid | Case sensitive |
| `int a+b;` | Invalid | No arithmetic operators should be present |
| `int if;` | Invalid | `if` is a keyword |
| `int avg of space;` | Invalid | Spaces not allowed |
| `int avg_of_space;` | Valid | Underscores are allowed |

---

## Practice Questions: Valid or Invalid?

### Questions

1. `int a1, b2, c3;`
2. `int 1a, 2b, 3c;`
3. `char 'a', 'b', 'c';`
4. `char ch1;`
5. `float 3.75;`
6. `Float f2;`
7. `int INt, InT, iNT;`
8. `char int1, int2, int3;`
9. `float charint, intchar;`
10. `float _;`
11. `char _1, _2_3;`
12. `int abcdefghijklmnopqrstuvwxyz;`

### Answers

1. **Valid** ✓
2. **Invalid** ✗ - Variable names cannot start with numbers
3. **Invalid** ✗ - Incorrect syntax, should not use quotes in declaration
4. **Valid** ✓
5. **Invalid** ✗ - Variable name cannot be a number
6. **Invalid** ✗ - `Float` should be lowercase `float` (case sensitive)
7. **Valid** ✓ - Variable names are case sensitive
8. **Valid** ✓ - `int1`, `int2`, `int3` are valid variable names
9. **Valid** ✓
10. **Valid** ✓ - Underscore is allowed
11. **Valid** ✓
12. **Valid** ✓ - Long variable names are allowed

---

## Key Takeaways

- Always declare variables with their datatype before using them
- Variable names cannot start with numbers
- Variable names cannot contain spaces (use underscore instead)
- Keywords cannot be used as variable names
- C is case-sensitive
- Type conversion happens automatically but may result in data loss
- Integer division always returns an integer result
