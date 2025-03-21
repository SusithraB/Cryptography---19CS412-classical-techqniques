# Cryptography---19CS412-classical-techqniques
# Caeser Cipher
# NAME - SUSITHRA.B
# REG NO - 212223220113

Caeser Cipher using with different key values

# AIM:

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.


## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

1.	In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2.	For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
3.	The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
    scheme, A = 0, B = 1, Z = 25.
4.	Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
5.	Decryption is performed similarly,
                       Dn (x)=(x - n) mod26


## PROGRAM:
```

#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char plain[100], cipher[100];
    int key, i, length;

    printf("\nEnter the plain text: ");
    scanf("%99s", plain); // Limiting input to prevent buffer overflow

    printf("\nEnter the key value: ");
    scanf("%d", &key);

    length = strlen(plain);

    printf("\n\n\tPLAIN TEXT: %s", plain);
    printf("\n\n\tENCRYPTED TEXT: ");

    for (i = 0; i < length; i++) {
        cipher[i] = plain[i] + key;

        // Adjust for uppercase letters
        if (isupper(plain[i]) && cipher[i] > 'Z') {
            cipher[i] -= 26;
        }
        // Adjust for lowercase letters
        if (islower(plain[i]) && cipher[i] > 'z') {
            cipher[i] -= 26;
        }

        printf("%c", cipher[i]);
    }
    cipher[length] = '\0'; // Null-terminate the encrypted string

    printf("\n\n\tAFTER DECRYPTION: ");

    for (i = 0; i < length; i++) {
        plain[i] = cipher[i] - key;

        // Adjust for uppercase letters
        if (isupper(cipher[i]) && plain[i] < 'A') {
            plain[i] += 26;
        }
        // Adjust for lowercase letters
        if (islower(cipher[i]) && plain[i] < 'a') {
            plain[i] += 26;
        }

        printf("%c", plain[i]);
    }
    plain[length] = '\0'; // Null-terminate the decrypted string

    printf("\n");

    return 0; // Use return 0 instead of getch();

}
```
## OUTPUT:
 ![Uploading image.png…]()

## RESULT:
  The program is executed successfully
