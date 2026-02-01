# C Language Tokens and `printf()` Behavior

## 1. Understanding Program Formatting

### Program 1

```c
void main() {
    printf("hello");
}
```

### Program 2

```c
void
     main
        (
)
              {
    printf(
        "hello"
    );
}
```

Both programs are **valid in C**.

### Why?

* C language ignores extra spaces, tabs, and new lines between tokens.
* A statement is generally considered complete when a **semicolon (`;`)** is encountered.
* Proper indentation (as in Program 1) is recommended for readability and maintainability.

---

## 2. What Are Tokens in C?

A **token** is the smallest individual unit in a C program.

Everything in C is built from tokens.

### Types of Tokens in the Example

| Category    | Example          |
| ----------- | ---------------- |
| Keyword     | `void`           |
| Identifiers | `main`, `printf` |
| Operators   | `()`             |
| Separators  | `{`, `}`, `;`    |
| Constants   | `"Hello"`        |

### Important Rule

* Any number of spaces or tabs can be placed between tokens without causing errors.

---

## 3. Understanding `printf()`

### Basic Rules

1. `printf()` prints the **first argument** to the screen.
2. The first argument must be inside **double quotes** (format string).
3. If more than one argument is present, arguments must be separated by commas.

### Format Specifier Mapping Rule

* 1st format specifier → 2nd argument
* 2nd format specifier → 3rd argument
* nth format specifier → (n+1)th argument

---

## 4. `printf()` Examples Explained

```c
printf("hello");          // Output: hello
printf("  hello  ");      // Output:   hello  
printf("%d %d %d ", 10, 20, 30);   // Output: 10 20 30
printf("%d", 3+2);        // Output: 5
printf("3+2");            // Output: 3+2
```

### Missing Arguments → Garbage Value (GV)

```c
printf("%d %d %d ", 10);  // 10 GV GV
printf("%d +%d ", 3+2);   // 5 + GV
```

**GV = Garbage Value** (undefined value due to missing arguments)

---

### Correct Usage

```c
printf("%d * %d = %d ", 3, 2, 3+2);  // 3 * 2 = 5
```

---

## 5. Type Mismatch and Errors

```c
printf("%d", 5.5);      // Garbage Value (type mismatch)
printf("%f", 5);        // Garbage Value
printf("%f", 5/2);      // Garbage Value (integer division gives 2)
printf("%f", 5.0 % 2);  // Compilation Error (modulus not allowed on float)
```

**CE = Compilation Error**

---

## 6. Extra Arguments

```c
printf("Hai", "Hello", "How are you");  
// Output: Hai
```

Extra arguments are ignored if no format specifiers exist.

```c
printf("%d %d %d ", "%d %d ", 10, 20, 30, 40, 50);
```

* First `%d` gets garbage value (string passed instead of integer)
* Next values: 10, 20
* Remaining values (30, 40, 50) are unused

---

## 7. Variables and `printf()`

```c
int ts = 7500;

printf("ts");            // Output: ts
printf(ts);              // Compilation Error (no format string)
printf("%d", ts);        // Output: 7500
printf("ts= %d");       // ts= GV (missing argument)
printf("%d +1000", ts);  // 7500 +1000
printf("%d", ts+1000);   // 8500
```

---

# Summary

* Tokens are the smallest units in C.
* C ignores extra spaces between tokens.
* `printf()` requires proper format specifiers.
* Missing arguments lead to garbage values.
* Type mismatch may produce garbage values or compilation errors.
* Proper indentation improves readability.

---

**End of Document**
