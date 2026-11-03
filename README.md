# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100], rail[10][100];
    int i, j, k = 0, row = 0, dir = 1;
    int key, len;

    printf("Enter the plain text: ");
    scanf("%s", str);

    printf("Enter the number of rails: ");
    scanf("%d", &key);

    len = strlen(str);

    for(i = 0; i < key; i++)
    {
        for(j = 0; j < len; j++)
            rail[i][j] = '\0';
    }

    for(i = 0; i < len; i++)
    {
        rail[row][i] = str[i];

        if(row == key - 1)
            dir = -1;
        else if(row == 0)
            dir = 1;

        row += dir;
    }

    printf("Encrypted text: ");

    for(i = 0; i < key; i++)
    {
        for(j = 0; j < len; j++)
        {
            if(rail[i][j] != '\0')
                printf("%c", rail[i][j]);
        }
    }

    return 0;
}
```

# OUTPUT
<img width="452" height="305" alt="Screenshot 2026-11-03 100323" src="https://github.com/user-attachments/assets/bec8112e-550b-40ec-8930-2609f86a11e7" />


# RESULT
Implementation of the Rail Fence Transposition Technique was successfully executed, and the encrypted text was obtained.
