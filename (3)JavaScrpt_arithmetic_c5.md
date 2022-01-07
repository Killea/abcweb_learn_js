# JavaScript part C (Arithmetic operators and practice)

[<- Home](README.md)


## Arithmetic <sup>/əˈrɪθmətɪk/</sup> operators 

It's all about math!

- Arithmetic operators take numerical values (either literals or variables) as their operands and return a single numerical value
- The standard arithmetic operators are `addition (+), subtraction (-), multiplication (*), & division (/)`

### Addition✖️ 🕙

- The addition operator **(+)** produces the sum of numeric operands or string concatenation

  **Example:**

  ```js
  2 + 2;
  ```

- In this example we add two literal numbers

  **Example:**

  ```js
  const myAge = 20;
  const myBrotherAge = 15;

  console.log(myAge + myBrotherAge);
  ```

- We can add two or more values using variables

  **Example:**

  ```js
  const myAge = 20;
  const myBrotherAge = 15;
  const result = myAge + myBrotherAge;

  console.log(result);
  ```

- In this example we store the result of adding two values into the result variable

  **Example:**

  ```js
  const myAge = 20;
  const myBrotherAge = 15;
  const result = myAge + myBrotherAge;

  console.log(result + 2);
  ```

- Also we can add variables values and literal numbers too

### Subtraction➖ 🕙

- The subtraction operator **(-)** subtracts the two number operands, producing their difference

  **Example:**

  ```js
  2 - 2; // We get 0 as result

  const myAge = 20;
  const myBrotherAge = 15;

  // We show the difference between myAge and myBrotherAge
  console.log(myAge - myBrotherAge);

  // Also we can use a variable to store the subtraction result
  const result = myAge - myBrotherAge;

  console.log(result);
  ```

- Also we can combine operations

  **Example:**

  ```js
  10 + 2 - 2;

  const myAge = 20;
  const myBrotherAge = 15;

  // Use variables, literal number and different arithmetic operators
  console.log(myAge - myBrotherAge + 10);

  const result = myAge - myBrotherAge + 10;

  console.log("Result: " + result);
  ```

  ### Multiplication❌ 🕙

  - The multiplication operator **(\*)** produces the product of the operands

  **Example:**.

  ```js
  2 * 2; // Returns 4 as result

  const firstNumber = 10;
  const secondNumber = 5;

  console.log(firstNumber * secondNumber);

  const result = firstNumber * secondNumber;

  console.log(result);
  ```

- In some cases we can use grouping **(operation)** to let the engine know that it need to resolve this operation first
- Read the [MND operator precedence doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) to know more about this subject

  **Example:**

  ```js
  2 + 2 * 4; // 10
  (2 + 2) * 4; // 16
  ```

- In the first example it will multiply 2 times 4 and then add 2 to the result
- In the second example as we are grouping 2 plus 2 it will resolve this operation first and then multiply by 4
- This concept works with variables too

  **Example:**

  ```js
  const two = 2;
  const four = 4;

  console.log(two + two * four); // 10
  console.log((two + two) * four); // 16
  ```

### Division➗ 🕙

- The division operator **(/)** produces the quotient of its operands where the left operand is the dividend and the right operand is the divisor

  **Example:**

  ```js
  20 / 2; // 10

  const firstNumber = 20;
  const secondNumber = 2;

  console.log(firstNumber / secondNumber); // 10

  const result = firstNumber / secondNumber;

  console.log(result); // 10
  ```

- With code we can have the same problem that we can have in math when we divide by 0
- JavaScript has a special number type called **Infinity**
- We get **Infinity** if we try to divide by 0
- [MDN Infinity doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)

### Remainder 󠀥 <sup>/rɪˈmeɪndə/</sup>  % 🕙

- The remainder operator **(%)** returns the remainder left over when one operand <sup>/'ɔpә,rænd/</sup> is divided by a second operand

  **Example:**

  ```js
  20 % 2; // 0

  const firstNumber = 20;
  const secondNumber = 2;

  console.log(firstNumber % secondNumber); // 0

  const result = firstNumber % secondNumber;

  console.log(result); // 0
  ```

- We can use this operator to find out if a number is even or odd
  [Freecodecamp - Finding a remainder in JavaScript](https://www.freecodecamp.org/challenges/finding-a-remainder-in-javascript)

#### Practice

[Exercise 27](./exercises/js/ex_27.md)👈 ( all +-*/%)

[Exercise 28](./exercises/js/ex_28.md)

[Exercise 29](./exercises/js/ex_29.md)

[Exercise 30](./exercises/js/ex_30.md)

[Exercise 31](./exercises/js/ex_31.md)

[Exercise 32](./exercises/js/ex_32.md)
