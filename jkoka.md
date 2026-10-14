- **NetID:** jkoka
- **Major:** Computer Science
- **Favorite CS Topic:** Object Orineted Programming 
- **Topic I Find Challenging / Want to Learn:** Data Structures and Algorithms

#include <stdio.h>

int nthFibonacciUtil(int n, int arr[]) {
    
    // Base case that checks if n = 1
    if (n <= 1) {
        return n;
    }

    // Check if the result is already stored in the arr array (already been calculated)
    if (arr[n] != -1) {
        return arr[n];
    }

    // calculate Fibonacci number and store it in arr array (only happens if it hasn't been previously calculated)
    arr[n] = nthFibonacciUtil(n - 1, arr) 
          + nthFibonacciUtil(n - 2, arr);

    return arr[n];
}

int nthFibonacci(int n) {

    // Create a arr array and initialize with invalid values 
    int arr[n + 1];
    for (int i = 0; i <= n; i++) arr[i] = -1;

    return nthFibonacciUtil(n, arr);
}

int main() {
    int n = 5;
    int result = nthFibonacci(n);
    printf("%d", result);
    return 0;
}
