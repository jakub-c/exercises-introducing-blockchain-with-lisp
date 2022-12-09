# Introducing Blockchain with Lisp

![book cover](https://github.com/Apress/introducing-blockchain-with-lisp/raw/main/9781484269688.jpg)

## Chapter 1

### Exercise 1-1

`f(x) = 2x - 1`

| `x` | `f(x)` |
| --- | ------ |
| -1  | -3     |
| 0   | -1     |
| 1   | 0      |

Fund employee by id

| `id` | `f(id)` |
| ---- | ------- |
| 001  | Albert  |
| 002  | Marcus  |
| 003  | Zeno    |

### Exercise 1-2

Three properties of symetric cryptography with in Racket syntax:

|     |                 |                           |
| --- | --------------- | ------------------------- |
| 1   | `E(x) !== x`    | `(not (eq? (E x) x))`     |
| 2   | `E(x) !== D(x)` | `(not (eq? (E x) (D x)))` |
| 3   | `D(E(x)) === x` | `(eq? (D (E(x))) x)`      |

Check compatibility of a Caesar cypher:

`E("abc") === "bcd"`
`D("bcd") === "abc"`

This passes rules 1, 2 and 3.

### Exercise 1-3

Encryption: Use ASCII number of a letter and multiply it by two.
Decryption: Divide the number by two and look it up in ASCII table.

### Exercise 1-4

#### Asymetric encoding

- Common key: 10 (c)
- Private key: 4 (s)
- Public key: 6 (p)

Formulas:

- `E(x,p) = (x + p) % c`
- `D(x', s) = (x' + s) % c`

Encode `5`: (5 + 6) % 10 = 1
Decode `1`: (1 + 4) % 10 = 5

#### Signing

- Sign a message: `S(x,s) = (x +s) % c`
- Verify a message: `V(x', sig, p) = (x' + p) === sig`

- Sign `5`: (5 + 4) % 10 = 9
- Verify `9`: (9 + 6) % 10 = 5
