EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
         #include<stdio.h> 
         #include<math.h>
         int main()
         {
              int n;
              scanf("%d",&n);
              if(n>=1 && n<=pow(4,3))
              {
              switch(n)
              {
                case 5:
                printf("seventy one");
                break;
                case 6:
                printf("seventy two");
                break;
                case 13:
                printf("seventy three");
                break;
                case 14:
                printf("seventy four");
                break;
                case 15:
                printf("seventy five");
                break;
                case 16:
                printf("seventy six");
                break;
                case 5:
                printf("seventy seven");
                break;
                case 6:
                printf("seventy eight");
                break;
                case 13:
                printf("seventy nine");
                break;
                default:
                printf("Greater than 13");
              }
```
Output:

![image](https://github.com/user-attachments/assets/025d6c05-ee1f-4db0-8510-250ba1b35e9a)


Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[1001];
    int freq[10] = {0}; 
    scanf("%s", str);
    for (int i = 0; i < strlen(str); i++) {
        if (str[i] >= '0' && str[i] <= '9') {
            freq[str[i] - '0']++; 
        }
    }

    for (int i = 0; i < 10; i++) {
        printf("%d ", freq[i]);
    }
    printf("\n"); 
    
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/2588dcd1-4363-4aac-a424-772cc19b1c45)

Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int compare(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}

void generate_permutations(char **strings, int n) {
    int i, j, k;
    qsort(strings, n, sizeof(char *), compare);
    do {
        for (i = 0; i < n; i++) {
            printf("%s ", strings[i]);
        }
        printf("\n");
        i = n - 2;
        while (i >= 0 && strcmp(strings[i], strings[i + 1]) >= 0) {
            i--;
        }
        if (i == -1) return;
        j = n - 1;
        while (strcmp(strings[i], strings[j]) >= 0) {
            j--;
        }
        swap(&strings[i], &strings[j]);
        for (k = i + 1, j = n - 1; k < j; k++, j--) {
            swap(&strings[k], &strings[j]);
        }
    } while (1);
}

int main() {
    int n, i;
    scanf("%d", &n);
    char **strings = (char **)malloc(n * sizeof(char *));
    for (i = 0; i < n; i++) {
        strings[i] = (char *)malloc(101 * sizeof(char)); // assuming maximum string length is 100
        scanf("%s", strings[i]);
    }
    generate_permutations(strings, n);
    for (i = 0; i < n; i++) {
        free(strings[i]);
    }
    free(strings);
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/094cdee0-bf2e-4177-87d4-fce42df946dc)

Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>

void printPattern(int n) {
    int size = 2 * n - 1;
    int pattern[size][size];

    
    for (int i = 0; i < n; i++) {
        for (int j = i; j < size - i; j++) {
            pattern[i][j] = n - i;
            pattern[j][i] = n - i;
            pattern[size - i - 1][j] = n - i;
            pattern[j][size - i - 1] = n - i;
        }
    }

   
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            printf("%d ", pattern[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int n;
    scanf("%d", &n);
    printPattern(n);
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/e59e9df0-617a-4b64-9dba-ac6f6767946e)

Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
```
#include <stdio.h>
void square();
int main(){
    
    square();
    return 0;
}
void square(){
    int a;
    scanf("%d",&a);
    float ans = a*a;
    printf("The square of %d is : %.2f",a,ans);
}
```
Output:

![image](https://github.com/user-attachments/assets/ed5fe4e2-ce15-41a7-882b-ca8eceb1f294)

Result:
Thus, the program is verified successfully
