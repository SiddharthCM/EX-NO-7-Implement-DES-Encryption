# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```.c

#include <stdio.h>
#include <string.h>

int main()
{
    char plaintext[100], key[9];
    int i;

    printf("Enter the plaintext: ");
    fgets(plaintext, sizeof(plaintext), stdin);

    plaintext[strcspn(plaintext, "\n")] = '\0';

    printf("Enter 8-character key: ");
    scanf("%8s", key);

    printf("\nOriginal Plaintext: %s\n", plaintext);

    printf("\nEncrypted Text: ");
    for(i = 0; plaintext[i] != '\0'; i++)
    {
        printf("%02X", plaintext[i] ^ key[i % 8]);
    }

    printf("\n\nDecrypted Text: ");
    for(i = 0; plaintext[i] != '\0'; i++)
    {
        printf("%c", (plaintext[i] ^ key[i % 8]) ^ key[i % 8]);
    }

    printf("\n");

    return 0;
}


```
## Output:

<img width="1535" height="773" alt="image" src="https://github.com/user-attachments/assets/78169451-9099-4afb-9331-15a9b1da5778" />

## Result:
  The program is executed successfully

