#include <stdio.h>

struct Expense {
    char category[30];
    float amount;
};

int main() {
    struct Expense expenses[100];
    int n = 0, choice, i;
    float total = 0;

    while (1) {
        printf("\n--- Hostel Expense Tracker ---\n");
        printf("1. Add Expense\n");
        printf("2. View Expenses\n");
        printf("3. Total Expenses\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter expense category (Food/Travel/Laundry/etc.): ");
                scanf("%s", expenses[n].category);
                printf("Enter amount: ");
                scanf("%f", &expenses[n].amount);
                n++;
                printf("Expense added successfully!\n");
                break;

            case 2:
                printf("\n--- Expense List ---\n");
                for (i = 0; i < n; i++) {
                    printf("%d. %s - Rs. %.2f\n", i + 1,
                           expenses[i].category, expenses[i].amount);
                }
                break;

            case 3:
                total = 0;
                for (i = 0; i < n; i++) {
                    total += expenses[i].amount;
                }
                printf("\nTotal Hostel Expenses: Rs. %.2f\n", total);
                break;

            case 4:
                printf("Exiting... Thank you!\n");
                return 0;

            default:
                printf("Invalid choice! Try again.\n");
        }
    }

    return 0;
}
