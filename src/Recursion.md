___
Recursion is a [[Programming Techniques | programming technique]] where a [[Functions | function]] calls itself directly or indirectly to solve a problem.

This involves breaking down a complex problem into smaller instances of the same problem and then combining the solutions to solve the original problem.

##### Base case:
- condition which stops the recursion
- typically n = 0 or 1
##### Recursive case:
- The case where the function calls itself with a smaller input value
##### Termination condition:
- The recursion eventually terminates when the base case is reached
Example: factorial calculation in C
```c
#include <stdio.h>

int factorial(int n) {
    if (n == 0) {
        return 1; // Base case
    } else {
        return n * factorial(n - 1); // Recursive case
    }
}

int main() {
    int num = 5;
    int result = factorial(num);
    printf("Factorial of %d is %d", num, result);
    return 0;
}
```
The `factorial` function calculates the factorial of a given number `n` by multiplying `n` with the factorial of `n-1`. Te base case is `n` is `0`.
