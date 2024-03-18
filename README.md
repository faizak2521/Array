
```
// Using multiple arrays to store data. //Faiza Khan

#include <stdio.h> // Include standard input/output library

// Prototypes for all functions 
void fillProductIdArray(int productIdArray[]); // Function prototype to fill product ID array
void updateSaleArray(int productIdArray[], float saleArray[]); // Function prototype to update sales array
int linearSearch(const int productIdArray[], int searchProductId); // Function prototype for linear search
void updateSales(float salesArray[], int index); // Function prototype to update sales value
void displayArrays(int productIdArray[], float salesArray[]); // Function prototype to display arrays

#define SIZE 3 // Symbolic constant for array size

// Main 
int main() {
    int productIdArray[SIZE]; // Declare array to store product IDs
    float saleArray[SIZE] = {0}; // Declare array to store sales data, initialized to 0

    // Call function to fill product ID array
    fillProductIdArray(productIdArray);

    // Call function to update sales array
    updateSaleArray(productIdArray, saleArray);

    // Call function to display arrays
    displayArrays(productIdArray, saleArray);

    return 0;
}

// Function 1 to fill the product ID array 
void fillProductIdArray(int productIdArray[SIZE]){
    for(int i = 0; i < SIZE; ++i){ // Loop through each element of the array
        printf("Product id to store in array: "); // Prompt user for product ID
        scanf("%d", &productIdArray[i]); // Read product ID from user input
        fflush(stdout); // Flush buffers
    }
}

// Function 2 to update the sales array 
void updateSaleArray(int productIdArray[SIZE], float saleArray[SIZE]){
    int productId; // Declare variable to store product ID
    int index; // Declare variable to store index

    printf("\nProduct id to enter sales: "); // Prompt user for product ID
    scanf("%d", &productId); // Read product ID from user input
    fflush(stdout); // Flush buffers

    while (productId != -99) { // Continue loop until user inputs -99
        index = linearSearch(productIdArray, productId); // Search for product ID in array
        if (index != -1) { // If product ID found
            updateSales(saleArray, index); // Update sales for corresponding product
        } else { // If product ID not found
            printf("Product not found\n"); // Print message indicating product not found
        }
        printf("\nEnter a product id for sales: "); // Prompt user for next product ID
        scanf("%d", &productId); // Read next product ID from user input
        fflush(stdout); // Flush buffers
    }
}

// Function 3 to perform linear search 
int linearSearch(const int productIdArray[], int searchProductId) {
    for (int i = 0; i < SIZE; ++i) { // Loop through each element of the array
        if (productIdArray[i] == searchProductId) { // If product ID matches search ID
            return i; // Return index of product ID
        }
    }
    return -1; // Return -1 if product ID not found
}

// Function 4 to update sales value 
void updateSales(float salesArray[], int index) {
    float sales; // Declare variable to store sales
    printf("Enter the sales: "); // Prompt user for sales value
    scanf("%f", &sales); // Read sales value from user input
    fflush(stdout); // Flush buffers
    salesArray[index] += sales; // Update sales value for corresponding product
    printf("Sales updated\n"); // Print message indicating sales updated
}

// Function 5 to display arrays 
void displayArrays(int productIdArray[], float salesArray[]) {
    printf("\nProduct Id Sales\n\n"); // Print header for product ID and sales
    for (int i = 0; i < SIZE; ++i) { // Loop through each element of the arrays
        printf("%d%23.2f\n", productIdArray[i], salesArray[i]); // Print product ID and sales value
    }
}
```
