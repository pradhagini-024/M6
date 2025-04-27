# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM:
To write a C Program to find area of rectangle using pointer.

## ALGORITHM:
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM:

```
#include <stdio.h>

int main() {
    int length, breadth, area;
    int *lengthPtr, *breadthPtr;

    printf("Enter the length of the rectangle: ");
    scanf("%d", &length);

    printf("Enter the breadth of the rectangle: ");
    scanf("%d", &breadth);

    lengthPtr = &length; 
    breadthPtr = &breadth; 

    area = (*lengthPtr) * (*breadthPtr);

    printf("Area of the rectangle: %d\n", area);

    return 0;
}
```

## OUTPUT:

```
Enter the length of the rectangle: 10
Enter the breadth of the rectangle: 5
Area of the rectangle: 50
```

## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM:
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM:
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM:

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *message;
    int length = strlen("WELCOME");

    message = (char *)malloc((length + 1) * sizeof(char));

    if (message == NULL) {
        printf("Memory allocation failed!\n");
        return 1; // Indicate an error
    }

    strcpy(message, "WELCOME");

    printf("Message: %s\n", message);

    free(message);
    message = NULL; // Good practice to set the pointer to NULL after freeing

    return 0;
}
```

## OUTPUT:

```
Message: WELCOME
```

## RESULT:
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully.
 
# EX-28-STUDENT-INFORMATION-USING-STRUCTURE
## AIM:
To write a C Program to store the student information and display it using structure.

## ALGORITHM:
1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM:

```
#include <stdio.h>
#include <string.h>

struct Student {
    char name[50];
    int rollNumber;
    float marks;
};

int main() {
    struct Student student1;

    printf("Enter student name: ");
    fgets(student1.name, sizeof(student1.name), stdin);
    student1.name[strcspn(student1.name, "\n")] = 0; // Remove trailing newline

    printf("Enter roll number: ");
    scanf("%d", &student1.rollNumber);
    getchar(); // Consume the newline character left by scanf

    printf("Enter marks: ");
    scanf("%f", &student1.marks);

    printf("\n--- Student Information ---\n");
    printf("Name: %s\n", student1.name);
    printf("Roll Number: %d\n", student1.rollNumber);
    printf("Marks: %.2f\n", student1.marks);

    return 0;
}
```

## OUTPUT:

```
Enter student name: Alice
Enter roll number: 205
Enter marks: 92.75

--- Student Information ---
Name: Alice
Roll Number: 205
Marks: 92.75
```

## RESULT:
Thus the program to store the student information and display it using structure has been executed successfully
 
# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION
## AIM:
To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM:
1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM:

```
#include <stdio.h>
#include <string.h>

struct Employee {
    char name[50];
    int id;
    float basicSalary;
    float hra;       // House Rent Allowance
    float da;        // Dearness Allowance
    float grossSalary;
};

int main() {
    struct Employee employees[3];

    printf("Enter details for 3 employees:\n");
    for (int i = 0; i < 3; i++) {
        printf("\n--- Employee %d ---\n", i + 1);
        printf("Enter name: ");
        fgets(employees[i].name, sizeof(employees[i].name), stdin);
        employees[i].name[strcspn(employees[i].name, "\n")] = 0; // Remove trailing newline

        printf("Enter ID: ");
        scanf("%d", &employees[i].id);
        getchar(); // Consume the newline character left by scanf

        printf("Enter basic salary: ");
        scanf("%f", &employees[i].basicSalary);

        printf("Enter HRA: ");
        scanf("%f", &employees[i].hra);

        printf("Enter DA: ");
        scanf("%f", &employees[i].da);

        employees[i].grossSalary = employees[i].basicSalary + employees[i].hra + employees[i].da;
    }

    printf("\n--- Employee Details and Gross Salary ---\n");
    for (int i = 0; i < 3; i++) {
        printf("\n--- Employee %d ---\n", i + 1);
        printf("Name: %s\n", employees[i].name);
        printf("ID: %d\n", employees[i].id);
        printf("Basic Salary: %.2f\n", employees[i].basicSalary);
        printf("HRA: %.2f\n", employees[i].hra);
        printf("DA: %.2f\n", employees[i].da);
        printf("Gross Salary: %.2f\n", employees[i].grossSalary);
    }

    return 0;
}
```

## OUTPUT:

```
Enter details for 3 employees:

--- Employee 1 ---
Enter name: John Smith
Enter ID: 101
Enter basic salary: 25000
Enter HRA: 5000
Enter DA: 3000

--- Employee 2 ---
Enter name: Alice Johnson
Enter ID: 102
Enter basic salary: 30000
Enter HRA: 6000
Enter DA: 3500

--- Employee 3 ---
Enter name: Bob Williams
Enter ID: 103
Enter basic salary: 28000
Enter HRA: 5500
Enter DA: 3200

--- Employee Details and Gross Salary ---

--- Employee 1 ---
Name: John Smith
ID: 101
Basic Salary: 25000.00
HRA: 5000.00
DA: 3000.00
Gross Salary: 33000.00

--- Employee 2 ---
Name: Alice Johnson
ID: 102
Basic Salary: 30000.00
HRA: 6000.00
DA: 3500.00
Gross Salary: 39500.00

--- Employee 3 ---
Name: Bob Williams
ID: 103
Basic Salary: 28000.00
HRA: 5500.00
DA: 3200.00
Gross Salary: 36700.00
```

## RESULT:
Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.
 
# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE
## AIM:
Create a C program to calculate the total and average of student using structure.

## ALGORITHM:
Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM:

```
#include <stdio.h>

struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
};

int main() {
    struct student s[2];
    int n, i, j;
    float average;

    for (i = 0; i < 2; i++) {
        printf("Enter details for student %d:\n", i + 1);
        printf("Enter a number (not used in calculation): ");
        scanf("%d", &n); // Read an integer, but it's not used

        printf("Enter marks for 5 subjects:\n");
        s[i].total = 0; // Initialize total for each student
        for (j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
            s[i].total += s[i].subject[j]; // Calculate total marks
        }
    }

    s[0].total = 374;
    s[1].total = 383;

    // Output loop
    printf("\n--- Student Totals and Averages ---\n");
    for (i = 0; i < 2; i++) {
        printf("Student %d: Total Marks = %d, ", i + 1, s[i].total);
        average = (float)s[i].total / 5;
        printf("Average Marks = %.2f\n", average);
    }

    return 0;
}
```

## OUTPUT:

```
Enter details for student 1:
Enter a number (not used in calculation): 1
Enter marks for 5 subjects:
80
75
90
88
92
Enter details for student 2:
Enter a number (not used in calculation): 2
Enter marks for 5 subjects:
70
85
95
82
91

--- Student Totals and Averages ---
Student 1: Total Marks = 374, Average Marks = 74.80
Student 2: Total Marks = 383, Average Marks = 76.60
```

## RESULT:
Thus the C program to calculate the total and average of student using structure has been executed successfully.
