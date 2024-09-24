#include <stdio.h>
#include <string.h>

// Define a structure to hold employee info
struct Employee {
    int id;
    char name[50];
    float salary;
};

int main() {
    struct Employee emp[4], temp;
    int i, j;

    // Step 1: Input details for 10 employees
    for (i = 0; i < 4; i++) {
        printf("Enter ID, Name, Salary for employee %d: ", i + 1);
        scanf("%d %s %f", &emp[i].id, emp[i].name, &emp[i].salary);
    }

    // Step 2: Sort employees by name
    for (i = 0; i < 3; i++) {
        for (j = i + 1; j < 4; j++) {
            if (strcmp(emp[i].name, emp[j].name) > 0) {
                // Swap employees if names are not in order
                temp = emp[i];
                emp[i] = emp[j];
                emp[j] = temp;
            }
        }
    }

    // Step 3: Display sorted employee details
    printf("\nSorted Employee List:\n");
    for (i = 0; i < 4; i++) {
        printf("ID: %d, Name: %s, Salary: %.2f\n", emp[i].id, emp[i].name, emp[i].salary);
    }

    return 0;
}
