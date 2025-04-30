1. Line 12 will print `3`. Even though `var i = 0` is declared inside a `for` loop, `var` is function-scoped, so `i` is accessible outside the loop. After the loop completes, `i` is 3, so that’s what gets printed.
2. Line 13 will print `150`, which is the last value assigned to `discounted` inside the loop (`300 * (1 - 0.5) = 150`). Since `var` is function-scoped, `discountedPrice` remains accessible outside the loop. `var` also tolerates redeclarations so redeclaring `discountedPrice` multiple times will not result in an error. 
3. Line 14 prints the last value of `finalPrice`, which is `Math.round(150 * 100) / 100 = 150`. Even though it was declared inside the loop, it uses `var`, so it is function-scoped and accessible here.
4. The function returns `[50, 100, 150]`. For each price, it calculates the discounted value and rounds it, adding it to the `discounted` array. All variables are declared with `var`, so scoping does not interfere with the return value.

5. Line 12 will cause an error. Since `i` is defined using `let`, which is block-scoped, it only exists inside the for loop. You can’t access it outside the loop. 
6. Line 13 will cause an error. `discountedPrice` was declared using `let` inside the loop block, so it’s not accessible outside that block. 
7. Line 14 prints the value of `finalPrice`. This works because `finalPrice` was declared outside the loop with `let` and is in scope here. It does not throw an error and will print `150`.
8. This function returns `[50, 100, 150]`. Each price in the `prices` array (`[100, 200, 300]`) is multiplied by `(1 - discount)`, which is `0.5`. The resulting discounted prices `[50, 100, 150]` are rounded and pushed into the `discounted` array. Since the variables are properly defined and used within their scopes, no errors are thrown, and the function successfully returns the array.
   
9. Line 11 will cause an error. Since `i` is defined using `let`, which is block-scoped, it only exists inside the for loop. This means `i` is not accessible outside the loop, so trying to log it results in an error.
10. Line 12 will print `3`. The variable `length` was declared using `const` in the function’s outer scope, so it's accessible at line 12. The value of `length` was also not reassigned. It holds the value `3` because `prices.length` is 3. No error occurs.
11. The function will return `[50, 100, 150]`. It takes each price from the input array `[100, 200, 300]`, applies a 50% discount using the formula `price * (1 - discount)`, and pushes each result into the `discounted` array. Since all variables are properly declared and scoped using `const` and `let`, the function runs without error and returns the array of discounted values.

12. 
    A. `student.name`   <br>
    B. `student['Grad Year']`   <br>
    C. `student.greeting()` <br>
    D. `student['Favorite Teacher'].name`   <br>
    E. `student.courseLoad[0]`  <br>

13. 
    A. `32` <br>
        `+` triggers string concatenation if either operand is a string. `'3'` is a string, so `2` is coerced to `'2'`, resulting in `'32'`.
    B. `1`  <br>
        `-` forces numeric conversion. `'3'` becomes `3`, so `3 - 2 = 1`. <br>
    C. `3`  <br>
        `null` is coerced to `0` in arithmetic, so `3 + 0 = 3`. <br>
    D. `3null`  <br>
        `+` with a string triggers string coercion. `null` becomes `'null'`, resulting in `'3null'`. <br>
    E. `4`  <br>
        `true` is coerced to `1`, so `1 + 3 = 4`. <br>
    F. `0`  <br>
        `false → 0`, `null → 0`, so `0 + 0 = 0`. <br>
    G. `3undefined` <br>
        `+` with a string converts both to strings. `undefined` becomes `'undefined'`, so `'3' + 'undefined'`. <br>
    H. `NaN`    <br>
        `undefined` cannot be converted to a number, so `'3' - undefined = NaN`.

14. 
    A. `true`   <br>
        `'2'` is coerced to `2`, and `2 > 1` is true. <br>
    B. `false`  <br>
        Both are strings, so this does lexicographic comparison. `'2'` > `'1'` so `'2' < '12'` is false.  <br>
    C. `true`   <br>
        `==` allows type coercion. `'2'` becomes `2`, so `2 == 2`. <br>
    D. `false`  <br>
        `===` checks the equality without type conversion. Since they are different types (one is a number, the other a string), the output is false. <br>
    E. `false`  <br>
        `true` is `1`, so `1 == 2` → false. <br>
    F. `true`   <br>
        `Boolean(2)` is `true`, and `true === true`. <br>

15. The `==` operator checks for value equality, allowing type coercion if the operands are of different types.  
The `===` operator checks for strict equality, meaning both value and type must match.

16. (in part2-question16.js)

17. The result is `[2, 4, 6]`. The `modifyArray` function takes each element of the input array and passes it to the `doSomething` callback function, which doubles the value. The loop applies this to every element and stores the results in a new array, which is returned.

18. (in part2-question18.js)

19. The output is:

1  
4  
3  
2  

Explanation: 
The function starts by printing `1` right away. Then it schedules two delayed logs using `setTimeout`. The log for `3` is scheduled with a 0-millisecond delay, so it will run after the current code finishes. The log for `2` is scheduled to run after 1000 milliseconds (1 second). Before either of those runs, `4` is printed immediately. After that, the delay for `3` finishes and it runs next, followed by `2` a second later.