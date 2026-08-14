# XOR

XOR *(exclusive OR)* is a logical operation that returns true (1) only when the inputs differ. It is a fundamental binary operation in cryptography.

| A | B | A XOR B |
| - | - | :-----: |
| 0 | 0 | 0       |
| 0 | 1 | 1       |
| 1 | 0 | 1       |
| 1 | 1 | 0       |

For example, to encrypt the word "HELLO" using the key "KEY", you first need to convert `HELLO` to binary form...

| Char | ASCII | Binary   |
| ---- | ----- | -------- |
| H    | 72    | 01001000 |
| E    | 69    | 01000101 |
| L    | 76    | 01001100 |
| L    | 76    | 01001100 |
| O    | 79    | 01001111 |

...then convert `KEY` to binary form...

| Char | ASCII | Binary   |
| ---- | ----- | -------- |
| K    | 75    | 01001011 |
| E    | 69    | 01000101 |
| Y    | 89    | 01011001 |

...and finally perform encryption – XOR each character with the key, repeating the key as many times as necessary:

```text
H ⊕ K: 01001000 ⊕ 01001011 = 00000011 (ASCII 3)
E ⊕ E: 01000101 ⊕ 01000101 = 00000000 (ASCII 0)
L ⊕ Y: 01001100 ⊕ 01011001 = 00010101 (ASCII 21)
L ⊕ K: 01001100 ⊕ 01001011 = 00000111 (ASCII 7)
O ⊕ E: 01001111 ⊕ 01000101 = 00001010 (ASCII 10)
```

The resulting ciphertext consists of ASCII non-printable characters with decimal values 3, 0, 21, 7, and 10. If we represent these as binary, the result would be a binary string: 00000011000000000001010100000111000010100.

To decrypt the ciphertext, you need to XOR the ciphertext with the same key:

```text
3  ⊕ K: 00000011 ⊕ 01001011 = 01001000 (ASCII 72 → H)
0  ⊕ E: 00000000 ⊕ 01000101 = 01000101 (ASCII 69 → E)
21 ⊕ Y: 00010101 ⊕ 01011001 = 01001100 (ASCII 76 → L)
7  ⊕ K: 00000111 ⊕ 01001011 = 01001100 (ASCII 76 → L)
10 ⊕ E: 00001010 ⊕ 01000101 = 01001111 (ASCII 79 → O)
```

The XOR operation is self-inverse — applying XOR twice with the same key returns the original data.

In practice, reusing the same key for multiple messages makes XOR encryption vulnerable to frequency analysis and other attacks. However, for educational purposes and basic demonstrations of cryptographic principles, XOR is simple and ideal.

## First assignment

Create a console application in any programming language to encrypt and decrypt messages using the XOR operation.

The allowed alphabet for messages (both for plaintext and key) contains only lowercase letters of the English alphabet:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Spaces, uppercase letters, numbers, and other characters are not allowed.

In the first line of input there is a message `m` of at most one hundred ASCII characters for plaintext or 800 bits for ciphertext. In the second line there is a key `k`. In the third line there is an integer `s` (1 for encryption, 2 for decryption).

### Test Example 1

If the input is:

```text
nikolatesla
ser
1
```

the output should be:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
```

### Test Example 2

If the input is:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
ser
2
```

the output should be:

```text
nikolatesla
```

## Do the assignment

[Implement the cypher here ](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142947)

## Solution hints

Each character is stored in memory as an 8-bit ASCII value (for lowercase letters a–z, codes range from 97 to 122). To encrypt, convert each character to its ASCII value, convert that to binary (8 bits), XOR with the corresponding key character's binary representation (repeating the key as needed), and output the result as binary text (no spaces between bits).

For decryption, follow the reverse process: take each 8-bit binary block from the ciphertext, convert it back to an integer (0–255), XOR with the ASCII value of the corresponding key character, and convert the result back to a character.

## More complex XOR Assignments (optional)

### Expand the allowed alphabet

Allow lowercase and uppercase letters, spaces, numbers, and punctuation marks. Non-letters are XORed with the key in the same way as letters.

## Use functions

Create two functions: `encrypt()` for encrypting messages and `decrypt()` for decrypting messages. Use the created functions in your main program.

### Create a class

Create a `XorCipher` class that:

- stores the key,
- provides `encrypt()` and `decrypt()` methods,
- optionally contains a private helper method for repeating the key over the length of the message.

Use the created class in the main program.

### Accept command-line arguments

Instead of waiting for user input, create a console application that accepts the following command-line arguments:

1. argument `m` for the message,
2. argument `k` for the key, and
3. argument `s` for the operation (`1` for encryption, `2` for decryption).

### Encrypt and decrypt files

Use your knowledge so far to create a program that can:

- read plaintext or binary ciphertext from a file,
- encrypt or decrypt it with a given key, and
- write the result to a new file.
