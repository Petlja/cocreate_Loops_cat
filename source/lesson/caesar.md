# Caesar Cipher

One of the great military commanders who used encrypted messages was Julius Caesar, around 50 BC. He used a simple cipher known as the Caesar cipher to protect military communications. This cipher is also known as a shift cipher because each letter in the plaintext is replaced by a letter some fixed number of positions down or up the alphabet.

For example, if you write `NIKOLATESLA` and shift each letter three places to the right:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
```

Letter `N` becomes `K`, `I` becomes `F`, and so on. So each letter is replaced by another letter which is a certain distance away in the alphabet.

**Decryption** works the same way, but in reverse. To decrypt the ciphertext, shift each letter back three places to the left:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
```

Letter `K` becomes `N`, `F` becomes `I`, and so on. The result of this shift is the original decrypted message `NIKOLATESLA`.

![Caesar Cipher Left Shift](./images/caesar1.png)

## Assignment to think about

Think about how you would create a console application in any programming language that will encrypt and decrypt messages using a Caesar cipher.

```{infonote}
The first student (*driver*) should focus on syntax while typing the code to encrypt the message. The second student (*navigator*) should watch the code, suggest improvements, and ask questions. After encrypting, switch roles to decrypt.
```

The allowed alphabet for messages (both for plaintext and ciphertext) can contain only lowercase letters of the English alphabet:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Spaces, uppercase letters, numbers, and other characters are not allowed.

In the first line of input there is a message `m` of at most one hundred characters, in the second line an integer `n` which represents the shift value (1–25), and in the third line an integer `s`, which represents the encryption direction. If `s=1` then `m` should be encrypted, and if `s=2`, then `m` should be decrypted.

### Test Example 1

If the input is:

```text
nikolatesla
3
1
```

the output should be:

```text
kfhlixqbpix
```

### Test Example 2

If the input is:

```text
kfhlixqbpix
3
2
```

the output should be:

```text
nikolatesla
```

## Solution hints

Since the English alphabet has 26 letters, the position of each letter can be represented by a number from 0 to 25.

* a → 0
* b → 1
* c → 2
* ...
* z → 25

To **encrypt** a letter, you can use the following formula:

```text
new_letter_position = (current_letter_position + shift_value) mod 26
```

`original_position` represents the numeric value of the letter in the alphabet, `shift_value` represents the number of positions to shift (1–25), and `mod 26` ensures the value wraps around the alphabet.

To **decrypt** a letter, you can use the following formula:

```text
new_letter_position = (current_letter_position - shift_value + 26) mod 26
```

Similarly to encryption, but the shift value is subtracted, and `+ 26` ensures the value does not become negative.

## More complex Caesar Cipher Assignments (optional)

### Expand the allowed alphabet

Create a console application in any programming language that will encrypt and decrypt messages using the Caesar cipher, but with an expanded alphabet.

The application should encrypt or decrypt only lowercase and uppercase letters. Spaces, numbers, and punctuation marks should remain unchanged.

In the first line of input there is a message `m` of at most one hundred characters, in the second line an integer `n` (the shift value from 1–25), and in the third line an integer `s` (1 for encryption, 2 for decryption).

## Use the functions 

Create two functions: one for encrypting messages and one for decrypting messages. Use the created functions in your main program.

Here you can work in pairs - one person should encrypt the message, and the other should decrypt it!

## Create a Class

Create a `CaesarCipher` class that contains:

- a constructor with a parameter that accepts a shift value and ensures that the value is in the allowed range (0–25),
- a private property for storing the shift value, with getter and setter methods,
- a public method for encrypting a message,
- a public method for decrypting a message, and
- optionally, a private method for processing messages that is used by both methods.

Use the created class in the main program.

## Accept command-line arguments

Instead of waiting for user input, create a console application that accepts the following command-line arguments:

1. argument `m` for the message,
2. argument `n` for the shift value (`0` to `25`), and
3. argument `s` for the encryption direction (`1` for encryption, `2` for decryption).

## Encrypt and decrypt files

Use your knowledge so far to create a console application for encrypting and decrypting text files using the Caesar cipher.

The application should accept the following command-line arguments:

1. argument `m` for the file name (or path),
2. argument `n` for the shift value (`0` to `25`), and
3. argument `s` for the encryption direction (`1` for encryption, `2` for decryption).
