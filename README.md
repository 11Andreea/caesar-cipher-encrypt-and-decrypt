# Caesar Cipher

A simple Python implementation of the **Caesar cipher**, a substitution
cipher that encrypts text by shifting each letter through the alphabet.

## Features

-   Encrypts and decrypts text using a configurable shift.
-   Preserves uppercase and lowercase letters.
-   Leaves spaces, punctuation, numbers, and other non-alphabetic
    characters unchanged.
-   Validates the shift value (an integer from `1` to `25`).

## Requirements

-   Python 3
-   No external dependencies

## Getting Started

1.  Clone or download this repository.

2.  Save the code in a Python file, for example `caesar_cipher.py`.

3.  Run it from your terminal:

    ``` bash
    python caesar_cipher.py
    ```

## Usage

``` python
from caesar_cipher import encrypt, decrypt

message = "Hello, World!"

encrypted = encrypt(message, 3)
print(encrypted)  # Khoor, Zruog!

decrypted = decrypt(encrypted, 3)
print(decrypted)  # Hello, World!
```

You can also use the main `caesar()` function directly:

``` python
from caesar_cipher import caesar

print(caesar("Hello, World!", 3))                 # Khoor, Zruog!
print(caesar("Khoor, Zruog!", 3, encrypt=False))   # Hello, World!
```

> Replace `caesar_cipher` with the name of your Python file if it is
> different.

## How It Works

Each letter is mapped to a letter a fixed number of positions away in
the alphabet. For example, with a shift of `3`, `A` becomes `D`, `B`
becomes `E`, and `X` becomes `A`.

Decryption applies the same process in the opposite direction. The
implementation uses Python's `str.translate()` and `str.maketrans()` to
perform the character substitution.

## Input Validation

The shift must be an integer between `1` and `25`, inclusive. Invalid
values return an explanatory error message.

## Security Note

The Caesar cipher is intended for learning about classical cryptography,
not for protecting sensitive information. Its small key space makes it
easy to break.
