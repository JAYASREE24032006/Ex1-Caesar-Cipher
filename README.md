
# EX1 - CAESAR CIPHER


## AIM :

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.

## THEORY :
The Hill cipher is a polygraphic substitution cipher that encrypts blocks of plaintext using matrix multiplication. By converting letters into numerical vectors and applying an invertible key matrix, it produces ciphertext. While more secure than simple ciphers, it is vulnerable to known-plaintext attacks and requires careful key management.

## ALGORITHM :


### STEP 1 :
In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
### STEP 2 :
For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
### STEP 3 :
The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
scheme, A = 0, B = 1, Z = 25.
### STEP 4 :
Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
### STEP 5 :
Decryption is performed similarly,
                       Dn (x)=(x - n) mod26



## PROGRAM :
```
#include <stdio.h>
#include <stdlib.h>
void caesarEncrypt(char *text, int key)
{
    for (int i = 0; text[i] != '\0'; i++)
    {
        char c = text[i];
        if (c >= 'A' && c <= 'Z')
        {
            text[i] = ((c - 'A' + key) % 26 + 26) % 26 + 'A';
        }
        else if (c >= 'a' && c <= 'z')
        {
            text[i] = ((c - 'a' + key) % 26 + 26) % 26 + 'a';
        }
    }
}
void caesarDecrypt(char *text, int key)
{
    caesarEncrypt(text, -key);
}
int main()
{
    char message[100];
    int key;
    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin);
    printf("Enter the Caesar Cipher key (an integer): ");
    scanf("%d", &key);
    caesarEncrypt(message, key);
    printf("Encrypted Message: %s", message);
    caesarDecrypt(message, key);
    printf("Decrypted Message: %s", message);
    return 0;
}
```



## OUTPUT :

![Screenshot 2024-09-02 221322](https://github.com/user-attachments/assets/75d79761-d0f6-49fc-a98f-b7bb97b18ee9)




## RESULT :
The program is To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm is executed successfully.

