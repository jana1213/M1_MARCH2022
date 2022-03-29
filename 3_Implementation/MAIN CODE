//  Examination DATA in c program
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int opt = 0;
int x = 0;
int y = 0;
int n = 0;
float t_d = 1;
float pre = 80.00;
char bill = 'y';


// Structure of Stu
struct stu {
	char name[20];
	char fe;
	int rollno;
	float days;
	float atnd;
} s[50];

// Functions
void add(struct stu s[]);
void eligibleStu(struct stu s[]);
void execute();
void printStu(struct stu s[]);
void deleteRecord(struct stu s[]);

// Function to execute the software
// for the stu examination
// registration system
void execute()
{
	printf(
		" Enter the serial number"
		"to select the option \n");
	printf(" 1. To show Eligible"
		"candidates \n");
	printf(" 2. To delete the "
		"student record \n");
	printf(" 3. To change the "
		"eligibility criteria \n");
	printf(" 4. Reset the "
		"eligibility criteria \n");
	printf(" 5. Print the list "
		"of all the student \n");
	printf(" Enter 0 to exit \n");

	scanf("%d", &opt);

	// Switch Statement for choosing
	// the desired option for the user
	switch (opt) {
	case 1:
		eligibleStu(s);
		execute();
		break;

	case 2:
		deleteRecord(s);
		execute();
		break;

	case 3:
		printf("Old Attendance "
			"required = %f",
			pre);
		printf(
			"\n Enter the updated "
			"attendence required \n");
		scanf("%f", &pre);
		printf("fe status required"
			" was %c \n",
			bill);
		printf("Enter the new fees "
			"status 'Y' for paid 'Not' "
			"for not paid and "
			"'B' for both \n");
		scanf("%c", &bill);
		printf("Eligibility Criteria updated \n");
		execute();
		break;

	case 4:
		pre = 80.00;
		bill = 'y';
		printf("Eligibility creitria reset \n");
		execute();
		break;

	case 5:
		printStu(s);
		execute();
		break;

	case 6:
		execute();
		break;

	case 0:
		exit(0);

	default:
		printf("Enter number only from 0-4 \n");
		execute();
	}
}

// Function to print the students record
void printStu(struct stu s[])
{
	// Loop to iterate over the students
	// students records
	for (x = 0; x < n; x++) {

		printf("Name of student %s \n",
			s[x].name);
		printf("Student roll number = %d \n",
			s[x].rollno);
		printf("Student fees status = %c \n",
			s[x].fe);
		printf("Student number of days "
			"present = %f \n",
			s[x].days);
		printf("Student attendence = %f \n",
			s[x].atnd);
	}
}

// Function to Student Record
void deleteRecord(struct stu s[])
{
	int p = 0;
	printf("Enter the roll number of "
		"the student to delete it ");
	scanf("%d", &p);

	// Loop to iterate over the students
	// records to delete the Data
	for (x = 0; x <= n; x++) {
		// Condition to check the current
		// student roll number is same as
		// the user input roll number
		if (s[x].rollno == (p)) {

			// Update record at ith index
			// with (i + 1)th index
			for (y = x; y < n; y++) {
				strcpy(s[y].name, s[y + 1].name);
				s[y].rollno = s[y + 1].rollno;
				s[y].fe = s[y + 1].fe;
				s[y].days = s[y + 1].days;
				s[y].atnd = s[y + 1].atnd;
			}
			printf("Stu Record deleted");
		}
	}
}

// Function to print the stu
// details of the eligible stu
void eligibleStu(struct stu s[])
{
	printf("________________"
		"________________"
		"_______________"
		"_____________ \n");
	printf("Qualified stu are = \n");

	// Iterate over the list
	// of the stu records
	for (x = 0; x < n; x++) {
		// Check for the eligibility
		// of the student
		if (s[x].fe == bill || 'B' == bill) {
			if (s[x].atnd >= pre) {
				printf("Stu name = %s \n",
					s[x].name);
				printf("Student roll no. = %d \n",
					s[x].rollno);
				printf(" Student fe = %c \n",
					s[x].fe);
				printf(" Student attendence = %f \n",
					s[x].atnd);
			}
		}
	}
}

// Function to add the stu record
void add(struct stu s[50])
{
	printf("Enter the total ");
	printf("number of working days \n");
	scanf("%f", &t_d);

	printf("Enter the number");
	printf("of students \n");
	scanf("%d", &n);

	for (x = 0; x < n; x++) {

		printf("Student number %d \n",
			(x + 1));

		printf("Enter the name of"
			" the student \n");
		scanf("%s", s[x].name);

		printf("Enter the roll number \n");
		scanf(" %d", &s[x].rollno);

		printf("Enter the fe of the"
			"student 'Paid' for paid "
			", 'Not' for not paid \n");
		scanf(" %c", &s[x].fe);

		printf("Enter the number of"
			"days the student was "
			"pre \n");
		scanf("%f", &s[x].days);

		s[x].atnd = (s[x].days
					/ t_d)
					* 100;
		printf("student attendence = %f \n",
			s[x].atnd);
	}
	execute();
}

// Driver Code
int main()
{
	printf("Welcome to Stu "
		"database registration \n");

	printf("Enter 0 to exit \n");
	printf("Enter 1 to add stu"
		" record \n");

	scanf("%d", &opt);

	// Switch Statements
	switch (opt) {
	case 0:
		exit(0);

	case 1:
		add(s);
		break;

	default:
		printf("Only enter 0 or 1");
		execute();
	}
	return 0;
}
