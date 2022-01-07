# JavaScript part H (Loops)

#### Loops (Iterators)

- It's common that when coding we need to keep repeating the same code execution until a given condition it's true
- For example I might want to show numbers from 0 to 10 to create a list

  **Example:**

  ```js
  console.log(0);
  console.log(1);
  console.log(2);
  console.log(3);
  console.log(4);
  console.log(5);
  console.log(6);
  console.log(7);
  console.log(8);
  console.log(9);
  console.log(10);
  ```

- This code works
- But what about if you need to add more functionality or you need to show more numbers like to a 100 or to a 1000
- We'll go crazy, right?

  **Example:**

  ```js
  console.log("number: ", 0);
  console.log("number: ", 1);
  console.log("number: ", 2);
  console.log("number: ", 3);
  console.log("number: ", 4);
  console.log("number: ", 5);
  console.log("number: ", 6);
  console.log("number: ", 7);
  console.log("number: ", 8);
  console.log("number: ", 9);
  console.log("number: ", 10);
  ```

- Thanks we can use iteration to solve this problem
### While🕙

- The **while statement** creates a loop that executes a specified statement as long as the test condition evaluates to true
- The condition is evaluated before executing the statement

  **Example:**

  ```js
  while (condition) {
    console.log(
      "This code it's goin to be executed until the condition is false"
    );
  }
  ```

- Let refactor the numbers code so it works for 10, 100 or 1000 numbers!

  **Example:**

  ```js
  let number = 0;

  while (number < 11) {
    console.log(number);
    number++;
  }
  ```

- With only a couple of lines of code we can solve the previous feature
- Now we only need one change to show up to 1000 numbers

  **Example:**

  ```js
  let number = 0;

  while (number < 1001) {
    console.log(number);
    number++;
  }
  ```

- Also, if we need to change the code to add more functionality we can do it in a really simple and easy way:

  **Example:**

  ```js
  let number = 0;

  while (number < 1001) {
    console.log("number: ", number);
    number++;
  }
  ```

- Using while we can repeat the block code until the condition is false
- In each iteration we use number++ to increase the number value
- Once we reach 1001 number will no longer be lower than 1001 so the condition will be false
- The code will continue the normal code flow
- We need to be careful as the condition might be always true and this script will continue to execute for ever
- At some point the engine will throw a recursivity exception and we'll get an error
- Always be sure to change the condition so it becomes false at some point

  **Example:**

  ```js
  while (true) {
    console.log("Server will run out after executing this code many times!");
  }

  let number = 0;

  while (number < 10000) {
    console.log("number: ", number);
    // We never changed number value so it's always going to be 0 and then less than 10000 so the condition will always be true :(
  }
  ```

- The while statement will not be executed if the condition is false from the beginning

  **Example:**

  ```js
  while (false) {
    console.log("This code doesn't get executed");
  }

  let number = 1000;

  while (number < 10) {
    console.log("number: ", number);
    number++;
    // All this code won't get executed as the initial condition is false
  }
  ```

- If the condition is false the engine will ignore it
- [MDN while doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)

#### Practice

[Exercise 66](./exercises/js/ex_66.md)

[Exercise 67](./exercises/js/ex_67.md)

[Exercise 68](./exercises/js/ex_68.md)👈 even number

[Exercise 69](./exercises/js/ex_69.md)

[Exercise 70](./exercises/js/ex_70.md)

[Exercise 71](./exercises/js/ex_71.md)

[Exercise 72](./exercises/js/ex_72.md)

[Exercise 73](./exercises/js/ex_73.md)

[Exercise 74](./exercises/js/ex_74.md)

[Exercise 75](./exercises/js/ex_75.md) (advance)

### do/while 🕙

- The **do/while** statement creates a loop that executes a specified statement until the test condition evaluates to false
- The condition is evaluated after executing the statement, resulting in the specified statement executing **at least once**
- In this case the code will be executed once and then ask for a condition
- It's similar to while but the difference it's where we use the condition to evaluate whether it will iterate or not

  **Example:**

  ```js
  do {
    // This code will execute at least once
  } while (condition);
  ```

- It will keep iterating until the condition is false
- If the condition is always true we have the same while true problem

  **Example:**

  ```js
  do {
    // we'll get a exeption or error
  } while (true);
  ```

- We can refactor one of the previous examples using do while:

  **Example:**

  ```js
  let number = 0;

  do {
    console.log('number: ', number);
    number++;
  } while (number < 10000) {
  ```

- In this case we show the message
- Increment the number value
- Then evaluate the condition
- We'll iterate until the condition is false

  **Example:**

  ```js
  let number = 1000;

  do {
    console.log('number: ', number);
    number++;
  } while (number < 10) {
  ```

- In this example we'll only show number 1000 once and then it won't iterate
- Here we can see that even having a false condition do/while gets executed at least once
- [MDN do...while doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)

#### Practice

[Exercise 76](./exercises/js/ex_76.md) 👈 (do while)

[Exercise 77](./exercises/js/ex_77.md)  

[Exercise 78](./exercises/js/ex_78.md)

[Exercise 79](./exercises/js/ex_79.md)

[Exercise 80](./exercises/js/ex_80.md)

[Exercise 81](./exercises/js/ex_81.md)

[Exercise 82](./exercises/js/ex_82.md)

[Exercise 83](./exercises/js/ex_83.md)

[Exercise 84](./exercises/js/ex_84.md)

[Exercise 85](./exercises/js/ex_85.md)

## For 🕙

- The **for** statement creates a loop that consists of three optional expressions
- Enclosed in parentheses and separated by semicolons
- Followed by a statement (usually a block statement) to be executed in the loop

  **Example:**

  ```js
  for (initialization; condition; finalExpression) {
    // statement
  }
  ```

- Initialization: An expression (including assignment expressions) or variable declaration
- Condition: An expression to be evaluated before each loop iteration
- finalExpression: An expression to be evaluated at the end of each loop iteration
- For example to iterate over numbers between 0 and 10 we write the following code:

  **Example:**

  ```js
  for (let number = 0; number <= 10; number++) {
    console.log(number);
  }
  ```

- Initialization: `let number = 0;`
- Condition: `number <= 10;`
- finalExpression: `number++`

- We initialize a number variable with the value 0
- Then the condition it's going to be evaluated
- If the condition is true it will execute the block statements
- After iterating it will execute the final expression, in this case it's to increment one more number value
- It's still pretty easy to refactor code:

  **Example:**

  ```js
  for (let number = 0; number <= 1000; number++) {
    console.log("number: ", number);
  }
  ```

- [MDN for doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)

#### Practice

[Exercise 86](./exercises/js/ex_86.md)

[Exercise 87](./exercises/js/ex_87.md)

[Exercise 88](./exercises/js/ex_88.md)

[Exercise 89](./exercises/js/ex_89.md)

[Exercise 90](./exercises/js/ex_90.md)

[Exercise 91](./exercises/js/ex_91.md)

[Exercise 92](./exercises/js/ex_92.md)

[Exercise 93](./exercises/js/ex_93.md)

[Exercise 94](./exercises/js/ex_94.md)

[Exercise 95](./exercises/js/ex_95.md)

[Exercise 96](./exercises/js/ex_96.md)

[Exercise 97](./exercises/js/ex_97.md)

### Break

- The **break** statement terminates the current loop or switch statement and transfers program control to the statement following the terminated statement

  **Example:**

  ```js
  for (let i = 0; i < 1000; i++) {
    break;
  }
  ```

- In this example we will iterate until index is 10 and then cut the iteration execution
- So we only show numbers from 0 to 9

  **Example:**

  ```js
  for (let index = 0; index < 1000; index++) {
    if (index < 10) {
      console.log(index);
    } else {
      break;
    }
  }
  ```

- [MDN break doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break)

#### Practice

[Exercise 98](./exercises/js/ex_98.md)

[Exercise 99](./exercises/js/ex_99.md)
