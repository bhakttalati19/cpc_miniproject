#include <stdio.h>
#include <stdlib.h>
#include <string.h>

//  Structure of supermart
struct supermart {
    char product[20];
    char company[20];
    int available_quantity;
    float price;
};

// Driver Code
int main()
{
    struct supermart sup[100];

    char company[30];

    int i, input, count;

    i = input = count = 0;

    // loop
    while (input != 5) {

        printf("\n\n****######"
               "WELCOME TO SUPERMART "
               "#####****\n");
        printf("\n\n1. Add product information\n2. Display product information\n");
        printf("3. List all products of a given company\n");
        printf("4. List the count of products in the supermart\n");
        printf("5. Exit");

        // product details
        printf("\n\nEnter one of the above: ");
        scanf("%d", &input);

        // Process the input
        switch (input) {

        // Add product
        case 1:
            printf("Enter product name = ");
            scanf("%s", sup[count].product);

            printf("Enter company name = ");
            scanf("%s", sup[count].company);

            printf("Enter available quantity = ");
            scanf("%d", &sup[count].available_quantity);

            printf("Enter price = ");
            scanf("%f", &sup[count].price);
            count++; // Increment count to track added products
            break;

        // Print product information
        case 2:
            printf("You have entered the following information\n");
            for (i = 0; i < count; i++) {
                printf("Product name = %s\n", sup[i].product);
                printf("Company name = %s\n", sup[i].company);
                printf("Available quantity = %d\n", sup[i].available_quantity);
                printf("Price = %.2f\n", sup[i].price);
            }
            break;

        // List products by company
        case 3:
            printf("Enter company name: ");
            scanf("%s", company);
            printf("Products from company %s:\n", company);
            for (i = 0; i < count; i++) {
                if (strcmp(company, sup[i].company) == 0) {
                    printf("Product: %s, Quantity: %d, Price: %.2f\n",
                           sup[i].product, sup[i].available_quantity, sup[i].price);
                }
            }
            break;

        // Print total count
        case 4:
            printf("\nNo. of products available in the supermart: %d\n", count);
            break;

        case 5:
            exit(0);
            break;

        default:
            printf("Invalid choice, please try again.\n");
            break;
        }
    }

    return 0;
}
