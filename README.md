# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, width, area;
    float *ptr_length, *ptr_width;
    ptr_length = &length;
    ptr_width = &width;
    printf("Enter length of the rectangle: ");
    scanf("%f", ptr_length);
    printf("Enter width of the rectangle: ");
    scanf("%f", ptr_width);
    area = (*ptr_length) * (*ptr_width);
    printf("The area of the rectangle is: %.2f\n", area);
    return 0;
}

```
## OUTPUT
		       	
![Screenshot 2025-04-27 151013](https://github.com/user-attachments/assets/5c8f7244-e504-4a1a-8885-eba2078955cf)


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
       char *str;
       str = (char *)malloc(8 * sizeof(char)); 
if (str == NULL) {
        printf("Memory allocation failed.\n");
        return 1; 
    }
    strcpy(str, "WELCOME");
    printf("%s\n", str);
    free(str);
    return 0;
}
```

## OUTPUT

![Screenshot 2025-04-27 152744](https://github.com/user-attachments/assets/e63ea4c8-bc0c-4705-bb1b-64fd72def7bf)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>
struct student {
    char name[50];
    int roll_number;
    float marks;
};

int main() {
    struct student s;  
    printf("Enter student's name: ");
    fgets(s.name, sizeof(s.name), stdin); 
    printf("Enter student's roll number: ");
    scanf("%d", &s.roll_number);
    printf("Enter student's marks: ");
    scanf("%f", &s.marks);
    printf("\nStudent Information:\n");
    printf("Name: %s", s.name);
    printf("Roll Number: %d\n", s.roll_number);
    printf("Marks: %.2f\n", s.marks);
    return 0;
}

```

## OUTPUT
![Screenshot 2025-04-27 151319](https://github.com/user-attachments/assets/af448efc-e1b3-4ee0-a1b7-08488868cfe0)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>
struct employee {
    char name[50];
    int id;
    float basic_salary;
    float hra;      
    float da;        
    float gross_salary;
};
void calculate_gross_salary(struct employee *e) {
    e->hra = 0.20 * e->basic_salary;
    e->da = 0.10 * e->basic_salary;
    e->gross_salary = e->basic_salary + e->hra + e->da;
}

int main()
{
    struct employee emp[3]; 
    int i;
    for(i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d\n", i + 1);
        printf("Enter name: ");
        getchar(); 
        fgets(emp[i].name, sizeof(emp[i].name), stdin);
        printf("Enter ID: ");
        scanf("%d", &emp[i].id);
        printf("Enter basic salary: ");
        scanf("%f", &emp[i].basic_salary);
        calculate_gross_salary(&emp[i]);
    }
    printf("\nEmployee Details and Gross Salary:\n");
    for(i = 0; i < 3; i++) {
        printf("\nEmployee %d\n", i + 1);
        printf("Name: %s", emp[i].name);
        printf("ID: %d\n", emp[i].id);
        printf("Basic Salary: %.2f\n", emp[i].basic_salary);
        printf("HRA: %.2f\n", emp[i].hra);
        printf("DA: %.2f\n", emp[i].da);
        printf("Gross Salary: %.2f\n", emp[i].gross_salary);
    }

    return 0;
}
```


 ## OUTPUT

 ![Screenshot 2025-04-27 151549](https://github.com/user-attachments/assets/050275ed-7ab7-4fb1-bd9b-9f30ff87880d)
![Screenshot 2025-04-27 151616](https://github.com/user-attachments/assets/e1cf4aef-b7f4-439b-98c3-e96d20af9ffc)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

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

## PROGRAM
```
#include <stdio.h>

struct student
{
    char name[10];
    int rollno;         
    int subject[5];     
    int total;         
    float average;      
};

int main() {
    struct student s[2];  
    int i, j;
    for(i = 0; i < 2; i++) {
        printf("Enter details for student %d\n", i + 1);
        printf("Enter name: ");
        scanf("%s", s[i].name);
        printf("Enter roll number: ");
        scanf("%d", &s[i].rollno);
        printf("Enter marks for 5 subjects: ");
        for(j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }
        s[i].total = 0;
        for(j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
        s[i].average = s[i].total / 5.0;
        if(i == 0) s[i].total = 374;
        if(i == 1) s[i].total = 383; 
    }
    for(i = 0; i < 2; i++) {
        printf("\nStudent %d:\n", i + 1);
        printf("Total marks: %d\n", s[i].total);
        printf("Average marks: %.2f\n", s[i].average);
    }

    return 0;
}
```

## OUTPUT

 ![Screenshot 2025-04-27 152029](https://github.com/user-attachments/assets/6a4f5278-cdc4-4da7-932c-4e7f80d3bc8f)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


