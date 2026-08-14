# Skytale

The Skytale (skytale) is one of the oldest known tools for encryption, dating back to ancient Greece around 400 BC. It was a simple cylindrical device used by the Spartans to send secret messages during military campaigns.

A strip of parchment or leather was wrapped around a wooden rod (*skytale*) of a certain diameter. The message was then written lengthwise across the wrapped strip. To decrypt, the receiver wrapped the strip around a rod of the same diameter and read the message vertically.

If you want to encrypt the message:

```text
attackatdawn
```

and you choose a rod that allows **4 letters per wrap**, you first write the message vertically in columns, forming a table:

```text
a t t a
c k a t
d a w n
```

The encrypted text is then obtained by reading row by row:

```text
acdtkatawatn
```

To decrypt the message, the receiver wraps the strip around a rod of the same diameter and reads vertically again to reconstruct the original message.

## First assignment

Create a console application in any programming language to encrypt and decrypt messages using the Skytale cipher.

The allowed alphabet for messages contains only lowercase letters of the English alphabet:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Spaces, uppercase letters, numbers, and other characters are not allowed!

In the first line of input there is a message `m` of at most one hundred characters. In the second line there is an integer `k` (the number of columns in the table for encryption). In the third line there is an integer `s` (1 for encryption, 2 for decryption).

### Test Example 1

If the input is:

```text
attackatdawn
4
1
```

the output should be:

```text
acdtkatawatn
```

### Test Example 2

If the input is:

```text
acdtkatawatn
4
2
```

the output should be:

```text
attackatdawn
```

## Solution hints

For **encryption**, write the plaintext vertically in a table with `k` columns. Read the table row by row to get the ciphertext.

For **decryption**, write the ciphertext row by row into a table with `k` columns, read the table vertically to reconstruct plaintext.

## More complex Skytale Assignments (optional)

### Expand the allowed alphabet

Include uppercase letters, spaces, numbers, and punctuation marks.

### Use functions

Create `encrypt()` and `decrypt()` functions to make the code modular.

### Create a class

Implement a `SkytaleCipher` class that stores `k` and provides methods for encryption and decryption.

### Encrypt and decrypt files

Modify the program so that it reads plaintext or ciphertext from a file and writes the result to another file.

### Handle incomplete rows

Modify the program so that if the last row is shorter than `k`, it still encrypts and decrypts correctly, handling incomplete rows appropriately.
