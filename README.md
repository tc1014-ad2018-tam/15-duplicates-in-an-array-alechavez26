# 15-duplicates-in-an-array-alechavez26
15-duplicates-in-an-array-alechavez26 created by GitHub Classroom
/*This program will ask to the user n number of integer value
 * and return how many of that numbers are duplicate.
 *
 *
 * Alejandra Chavez Cruz
 * A01411970@itesm.mx
 * 15/oct/18
 */

#include <stdio.h>
#include <stdlib.h>

//1st function
int Compare (const void * a, const void * k) {
    return (*(int *) a - *(int *) k);
}
//variables
int main() {
    int count;
    int n;
    int dup = 0;

    //we ask for the number of values that the user would like
    printf("Welcome user,this program will help you. How many numbers would you like? : ");
    scanf("%d", &n);

    // In this part we declare the variable for the value of numbers that the user wants
    int numbers[n];

    for(int k = 0; k < n; k++){
        printf("%d:", k+1);
        scanf("%d", &numbers[k]);
    }

    // In this part we declare the function sorting for the duplicate in an array
    qsort(numbers, n, sizeof(int), Compare);

    for(int a = 0; a < n; a+=count+1){
        count = 0;
        for(int c = a + 1; c < n; c++){
            if(numbers[a] == numbers[c]){
                count++;
            }
        }
        if(count > 0){
            dup++;
        }
    }

    //in this part, we bring to the user the result of the numbers that are repeated
    printf("The amount of duplicate/repeated values is: %d.", dup);

    return 0;
}
