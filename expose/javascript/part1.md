1. values added:  20
2. final result:  20
3. `var` has no block scope and can lead to unintended behaviors like variable hoisting. It makes your code harder to debug and maintain.
4. values added:  20
5. Error. When using let, variables declared inside a code block cannot be accessed outside that block. Therefore, when the program tried to access `result` outside of the block, the variable is undefined and results in an error. 
6. Error. Constant variables cannot be reassigned so line 7 will cause an error.
7. Error. There would already be an error because of line 7, as mentioned in question 6. However if if line 7 wasn't there, the error would be because constant variables cannot be accessed outside of the block it's assigned in.