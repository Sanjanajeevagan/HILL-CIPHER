# EX. NO: 3 HILL CIPHER
HILL CIPHER

## AIM 
To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```PY
#include <stdio.h>

int main() {
    int key[3][3], pt[3], ct[3];
    char plaintext[4];
    int i, j;

    printf("Enter 3-letter plaintext (CAPS): ");
    scanf("%s", plaintext);

    printf("Enter 3x3 key matrix:\n");
    for(i = 0; i < 3; i++) {
        for(j = 0; j < 3; j++) {
            scanf("%d", &key[i][j]);
        }
    }

    // Convert plaintext to numbers
    for(i = 0; i < 3; i++) {
        pt[i] = plaintext[i] - 'A';
    }

    // Encryption
    for(i = 0; i < 3; i++) {
        ct[i] = 0;
        for(j = 0; j < 3; j++) {
            ct[i] += key[i][j] * pt[j];
        }
        ct[i] = ct[i] % 26;
    }

    printf("Cipher Text: ");
    for(i = 0; i < 3; i++) {
        printf("%c", ct[i] + 'A');
    }

    return 0;
}


```

## OUTPUT
<img width="438" height="253" alt="image" src="https://github.com/user-attachments/assets/e51ef061-b80d-4446-953c-75f9606dc113" />


## RESULT
Thus te program has been implemented successfully using hill Cipher.
