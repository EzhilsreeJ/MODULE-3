## EXPERIMENT-17-AGE CALCULATOR

### AIM:
To create a program that calculates a person's age in years, months, and days based on their birthdate and the current date.

### ALGORITHM:
1. Begin the program.
2. Define a function `calculateAge()` that takes six parameters: `birth_day`, `birth_month`, `birth_year`, `current_day`, `current_month`, and `current_year`.
3. Inside the function:
   - Calculate the difference in years, months, and days between the birthdate and the current date.
   - Adjust the age if the current day or month is less than the birth day or month respectively.
   - Print the calculated age in years, months, and days.
4. In the `main()` function:
   - Define variables `birth_day`, `birth_month`, `birth_year`, `current_day`, `current_month`, and `current_year` with predefined values representing the birthdate and the current date.
   - Call the `calculateAge()` function with these variables as arguments.
5. End the program.

## PROGRAM:
``` 
#include <stdio.h>

void calculateAge(int birth_day, int birth_month, int birth_year, int current_day, int current_month, int current_year) {
    int age_years, age_months, age_days;

    age_years = current_year - birth_year;
    age_months = current_month - birth_month;
    age_days = current_day - birth_day;

    if (age_days < 0) {
        age_months--;
        age_days += 31;
    }
    if (age_months < 0) {
        age_years--;
        age_months += 12;
    }

    printf("Present Age Years: %d Months: %d Days: %d\n", age_years, age_months, age_days);
}

int main() {
    int birth_day = 12, birth_month = 12, birth_year = 1990;
    int current_day = 8, current_month = 10, current_year = 2020;

    calculateAge(birth_day, birth_month, birth_year, current_day, current_month, current_year);

    return 0;
}
    

```
## SAMPLE OUTPUT :

![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/02b9f6e0-11f3-45d3-a586-4d699fc14e05)


## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/861592f3-908b-4c7e-871c-0450b1177953)




## RESULT:
Thus the required program is written and executed successfully.



## EXPERIMENT-18-DATE VALIDITY CHECKER

### AIM:
To develop a program that checks the validity of a given date.

### ALGORITHM:
1. Begin the program.
2. Define a function `checkDateValidity(int d, int m, int y)` that takes three parameters representing the day, month, and year of the date to be checked.
3. Inside the function:
   - Declare an array `daysInMonth[]` to store the number of days in each month.
   - Check if the year is valid (between 1900 and 9999).
   - Check if the month is valid (between 1 and 12).
   - Adjust the number of days in February for leap years.
   - Check if the day is valid based on the number of days in the given month.
   - Print whether the day is valid or invalid.
4. In the `main()` function:
   - Declare variables `d`, `m`, and `y` to store the day, month, and year respectively.
   - Prompt the user to input the date in the format "dd/mm/yyyy".
   - Read the input date using `scanf()` function.
   - Call the `checkDateValidity()` function with the input date as arguments.
5. End the program.

## PROGRAM:
``` 
#include <stdio.h>

void checkDateValidity(int d, int m, int y) {
    int daysInMonth[] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

    
    if (y < 1900 || y > 9999) {
        printf("Year is not valid.\n");
        return;
    }

    
    if (m < 1 || m > 12) {
        printf("Month is not valid.\n");
        return;
    }

    
    if (y % 400 == 0 || (y % 4 == 0 && y % 100 != 0)) {
        daysInMonth[1] = 29;
    }

    
    if (d < 1 || d > daysInMonth[m - 1]) {
        printf("Day is invalid.\n");
        return;
    }

    printf("Day is valid.\n");
}

int main() {
    int d, m, y;

    
    scanf("%d/%d/%d", &d, &m, &y);

    checkDateValidity(d, m, y);

    return 0;
}
```
## SAMPLE OUTPUT :

![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/fd02a487-eaee-49fa-9bfe-8900e80caa93)


## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/c9d475a6-2e78-42fe-8d01-a40df4579fe3)




## RESULT:
Thus the required program is written and executed successfully.


## EXPERIMENT-19-PATTERN PRINTER

### AIM:
To create a program that prints a specific pattern of numbers.

### ALGORITHM:
1. Begin the program.
2. Use nested for loops to iterate over rows and columns:
   - Outer loop (`r` loop) iterates from 1 to 5.
   - Inner loop (`c` loop) iterates from 1 to 5.
   - Inside the inner loop, use conditional statements to determine the value to be printed based on the row and column indices:
     - If `r` and `c` are both 3, print "1 ".
     - If `r` or `c` is 1, 2, 4, or 5, print "3 ".
     - If `r` or `c` is 2, 3, or 4, print "2 ".
   - Print a newline character after each row.
3. End the program.
## PROGRAM:
``` 
#include<stdio.h>
int main(){
    
    for(int r=1;r<=5;r++)
    {
        for(int c=1;c<=5;c++)
        {
            if(r==3&& c==3)
            printf("1 ");
            else if(c==1 || r==1 || c==5 || r==5)
            printf("3 ");
            else if(r==2 || r==3 || r==4 || c==2 || c==3 || c==4)
            printf("2 ");
            else
            printf("3 ");

        }
        printf("\n");
    }
}

```
## SAMPLE OUTPUT :

![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/8b2418b8-56a4-4f82-a67b-f617d21d5d4e)



## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/aeb82f20-0042-47ba-b344-570bac6cb8e0)



## RESULT:
Thus the required program is written and executed successfully.


## EXPERIMENT-20-SQUARE NUMBERS IN RANGE

### AIM:
To develop a program that prints the square numbers within a given range `[a, b]`.

### ALGORITHM:
1. Begin the program.
2. Declare variables `a`, `b`, and `sum` of type int to store the range limits and the square of each number.
3. Prompt the user to input two integers `a` and `b` representing the range.
4. Read the input values for `a` and `b` using `scanf()` function.
5. Use a for loop with loop variable `i` initialized to `a` and terminating condition `i <= b`.
6. Inside the loop:
   - Calculate the square of `i` and store it in `sum`.
   - Check if `sum` is within the range `[a, b]`:
     - If true, print `sum`.
7. End the program.

## PROGRAM:
``` 
#include<stdio.h>
int main()
{
    int a,b,sum=0;
    scanf("%d%d",&a,&b);
    for(int i=a;i<=b;i++)
    {
        sum=i*i;
        if(sum>=a && sum <= b)
        printf("%d ",sum);
    }
    
}
```
## SAMPLE OUTPUT :

![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/cec50cf6-d369-47a7-8218-c0a7989ac462)



## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/c6831dfb-8768-4af5-882d-7a62f6e21644)





## RESULT:
Thus the required program is written and executed successfully.


## EXPERIMENT-21-DIAGONAL ELEMENTS PRINTER

### AIM:
To develop a program that prints the diagonal elements of a square matrix in reverse order.

### ALGORITHM:
1. Begin the program.
2. Declare variables `n`, `i`, and `j` of type int to store the size of the square matrix and loop indices.
3. Prompt the user to input the size of the square matrix `n`.
4. Read the input value for `n` using `scanf()` function.
5. Declare a 2D array `matrix` of size `n x n`.
6. Use nested for loops to input the elements of the square matrix:
   - Outer loop (`i` loop) iterates over rows from 0 to `n-1`.
   - Inner loop (`j` loop) iterates over columns from 0 to `n-1`.
   - Inside the inner loop, input the matrix element at position `(i, j)`.
7. Use a reverse for loop to print the diagonal elements of the matrix:
   - Start the loop from `n-1` and iterate until 0.
   - Print the element `matrix[i][i]` at position `(i, i)` of the diagonal.
8. End the program.
## PROGRAM:
``` 
#include <stdio.h>

int main() {
    int n, i, j;
    scanf("%d", &n);
    int matrix[n][n];
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = n - 1; i >= 0; i--) {
        printf("a[%d][%d] is %d\n", i, i, matrix[i][i]);
    }
    return 0;
}

```
## SAMPLE OUTPUT :

![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/512e7d43-45c3-4354-8a60-5b01a4c9384b)



## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/ba9b5fc1-1fce-4a61-bc06-e994caf8783f)



## RESULT:
Thus the required program is written and executed successfully.



## EXPERIMENT-22-ODD ELEMENTS FINDER

### AIM:
To create a program that identifies and prints the odd elements of a square matrix.

### ALGORITHM:
1. Begin the program.
2. Declare variables `n`, `i`, and `j` of type int to store the size of the square matrix and loop indices.
3. Prompt the user to input the size of the square matrix `n`.
4. Read the input value for `n` using `scanf()` function.
5. Declare a 2D array `matrix` of size `n x n`.
6. Use nested for loops to input the elements of the square matrix:
   - Outer loop (`i` loop) iterates over rows from 0 to `n-1`.
   - Inner loop (`j` loop) iterates over columns from 0 to `n-1`.
   - Inside the inner loop, input the matrix element at position `(i, j)`.
7. Use nested for loops to traverse the matrix and identify odd elements:
   - Outer loop (`i` loop) iterates over rows from 0 to `n-1`.
   - Inner loop (`j` loop) iterates over columns from 0 to `n-1`.
   - Inside the inner loop, check if the element at position `(i, j)` is odd (i.e., `matrix[i][j] % 2 != 0`).
   - If the element is odd, print its position and value.
8. Print a newline after each row is traversed.
9. End the program.

## PROGRAM:
``` 
#include <stdio.h>

int main() {
    int n, i, j;
    scanf("%d", &n);
    int matrix[n][n];
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            if (matrix[i][j] % 2 != 0) {
                printf("a[%d][%d] is %d\n", i, j, matrix[i][j]);
            }
        }
        printf("\n");
    }
    return 0;
}

```
## SAMPLE OUTPUT :

![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/d253d835-4bc5-4af4-88a1-4b1a873880a9)




## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/6eb2119e-c3ee-48c2-8782-d4b0cced3a30)





## RESULT:
Thus the required program is written and executed successfully.


## EXPERIMENT-23-ARRAY STATISTICS CALCULATOR

### AIM:
To create a program that calculates and prints the sum, count of even numbers, and count of odd numbers in an array.

### ALGORITHM:
1. Begin the program.
2. Prompt the user to input the size of the array `size`.
3. Declare an array `arr` of size `size`.
4. Use a for loop to input elements into the array:
   - Iterate `i` from 0 to `size-1`.
   - Read the input value for `arr[i]` using `scanf()` function.
5. Initialize variables `sum`, `evenCount`, and `oddCount` to store the sum, count of even numbers, and count of odd numbers respectively.
6. Use a for loop to traverse the array and calculate the sum and count of even and odd numbers:
   - Iterate `i` from 0 to `size-1`.
   - Update `sum` by adding `arr[i]`.
   - If `arr[i]` is even (i.e., `arr[i] % 2 == 0`), increment `evenCount`.
   - Otherwise, increment `oddCount`.
7. Print the calculated sum, count of even numbers, and count of odd numbers.
8. End the program.

## PROGRAM:
``` 
#include <stdio.h>

int main() {
    int size;
    scanf("%d", &size);
    
    int arr[size];
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }
    
    // Initialize variables to store sum, count of even and odd numbers
    int sum = 0;
    int evenCount = 0;
    int oddCount = 0;
    
    // Iterate through the array to calculate sum and count of even and odd numbers
    for (int i = 0; i < size; i++) {
        sum += arr[i];
        if (arr[i] % 2 == 0)
            evenCount++;
        else
            oddCount++;
    }
    
    // Print the results
    printf("Total Sum: %d\n", sum);
    printf("Even numbers: %d\n", evenCount);
    printf("Odd numbers: %d\n", oddCount);
    
    return 0;
}

```
## SAMPLE OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/f137923e-e9f9-462b-8339-b017edc0bcb9)




## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/41209e49-3f8f-4f08-a225-eea27f906784)





## RESULT:
Thus the required program is written and executed successfully.


## EXPERIMENT-24-DUPLICATE ELEMENTS FINDER

### AIM:
To develop a program that identifies and counts duplicate elements in an array.

### ALGORITHM:
1. Begin the program.
2. Prompt the user to input the size of the array `size`.
3. Declare an array `arr` of size `size`.
4. Use a for loop to input elements into the array:
   - Iterate `i` from 0 to `size-1`.
   - Read the input value for `arr[i]` using `scanf()` function.
5. Initialize a variable `count` to store the count of duplicate elements.
6. Use nested for loops to compare each element of the array with all subsequent elements:
   - Outer loop (`i` loop) iterates from 0 to `size-1`.
   - Inner loop (`j` loop) iterates from `i+1` to `size-1`.
   - Inside the inner loop, check if `arr[i]` is equal to `arr[j]`.
   - If a duplicate element is found, increment the `count` and break out of the inner loop.
7. Print the total number of duplicate elements found in the array.
8. End the program.
## PROGRAM:
``` 
#include <stdio.h>

int main() {
    int size;
    scanf("%d", &size);

    int arr[size];
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    int count = 0;
    for (int i = 0; i < size; i++) {
        for (int j = i + 1; j < size; j++) {
            if (arr[i] == arr[j]) {
                count++;
                break;
            }
        }
    }

    printf("Total number of duplicate elements found in array = %d\n", count);

    return 0;
}

```
## SAMPLE OUTPUT :

![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/03c88ebc-8f4d-42fa-8c0b-c52f6fc28b28)




## OUTPUT :
![image](https://github.com/EzhilsreeJ/MODULE-3/assets/144870412/cc182deb-c95e-49a1-986c-8d792491d5f7)






## RESULT:
Thus the required program is written and executed successfully.



















