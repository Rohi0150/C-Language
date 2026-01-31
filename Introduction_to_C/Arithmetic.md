# Arithmetic Operators

## Operators -> 45

```c
a = 2 + 3; // 5
```

```c
a = 3 + 2 + 5; // order of associativity
// 5 + 5 // 10
```

```c
a = 6 - 4 + 2 + 3; // 2 + 2 + 3 // left to right // 7
```

```c
a = 2 + 3 * 5; // follows priority order
// 2 + 15 // 17
```

```c
a = 2 * 3 + 3 * 2; // 6 + 6 // 12
```

## Parentheses () -> Used to change the priority order

```c
a = (2 + 3) * 5; // 5 * 5 // 25
```

## Division (/) Operator

```c
a = 5 / 2; // 2.5 or 2 (depends upon data type of a)
```

- If `a` is `int` → 2 is stored
- If `a` is `float` → 2.5 is stored

### Division Rules:
- `int / int` → `int`
- `float / int` → `float`
- `int / float` → `float`
- `float / float` → `float`

### Examples:

```c
a = 5.0 / 2;    // 2.5
a = 5 / 2.0;    // 2.5
a = 5.0 / 2.0;  // 2.5
a = -5 / 2;     // -2
a = 5 / -2;     // -2
a = -5 / -2;    // +2
a = 5.0 / -2;   // -2.5
a = 2 / 5;      // 0
a = 2 / 5.0;    // 0.4
a = -2 / 5.0;   // -0.4
```

```c
a = 13 * 2 / 5; // left to right // 26 / 5 // 5 (since int)
a = 13 / 2 * 5; // 6 * 5 // 30
```

```c
a = 21 / 5 / 2;
// 4 / 2
// 2 (left to right)
```

## Modulus (%) Operator

Used for **Remainder after division**

### Examples:

```c
a = 5 % 2;      // 1
a = 37 % 5;     // 2
a = 5 % -2;     // 1
a = -5 % -2;    // -1
```

### Modulus Sign Rule:
**Remainder's sign is completely dependent upon numerator sign**

`% sign(remainder) = sign(numerator) / (denominator)`

### Sign Rules:

| Operation | Result |
|-----------|--------|
| `+ / +`   | `+`    |
| `- / +`   | `-`    |
| `+ / -`   | `-`    |
| `- / -`   | `+`    |
| `+ % +`   | `+`    |
| `+ % -`   | `+`    |
| `- % +`   | `-`    |
| `- % -`   | `-`    |

### Important Note:
**Float is NOT applicable on % operator**

```c
a = 5.0 % 2;    // Compiler error
```

### More Examples:

```c
a = 6 % 3;      // 0
a = 15 % 3;     // 0
a = 13 % 10;    // 3
a = 781 % 100;  // 81
a = 781 % 10;   // 1
c = 1249 % 10;  // 9
a = 18 % 25;    // 18
a = 6 % 12;     // 6
```

```c
a = 3.5 * 2 % 7; // 7.0 % 7 // Compilation Error
```

## Modulus Use Case

**Consider a bank that provides multiples of 100:**

```c
if (cash % 100 == 0) {
    withdraw;
} else {
    enter the multiples of 100;
}
```

---

## Priority Order

1. `*`  `/`  `%`
2. `+`  `-`
3. `=`
