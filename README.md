# HILL CIPHER
HILL CIPHER

```
GEERTHIVASH J.D. - 212223060067
```
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

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
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
#define SIZE 3
int charToNum(char c) {
return toupper(c) - 'A';
}
char numToChar(int n) {
return (n % 26) + 'A'; }
int main() {
char text[100];
int key[SIZE][SIZE];
int len, i, j, k;
printf("Enter the plain text (only alphabets): ");
fgets(text, sizeof(text), stdin);
text[strcspn(text, "\n")] = '\0'; // remove newline
len = strlen(text);
while (len % SIZE != 0) {
text[len++] = 'X';
text[len] = '\0';
}
printf("Enter the 3x3 key matrix (row by row, 9 numbers):\n");
for (i = 0; i < SIZE; i++) {
for (j = 0; j < SIZE; j++) {
scanf("%d", &key[i][j]);
}
}
printf("\nCipher text: ");
for (i = 0; i < len; i += SIZE) {
int P[SIZE], C[SIZE
for (j = 0; j < SIZE; j++) {
P[j] = charToNum(text[i + j]);
}
for (j = 0; j < SIZE; j++) {
C[j] = 0;
for (k = 0; k < SIZE; k++) {
C[j] += key[j][k] * P[k];
}
C[j] %= 26; // mod 26
}
for (j = 0; j < SIZE; j++) {
printf("%c", numToChar(C[j]));
}
}
printf("\n");
return 0;
}
```
## OUTPUT
<img width="626" height="262" alt="image" src="https://github.com/user-attachments/assets/4c42a010-a495-4ce8-af12-138c8d355345" />

## RESULT
Thus the implementation of hill cipher substitution had been executed successfully
