# JavaScript part D (Comparison operators)

[<- Home](README.md)

It's getting harder now!🪨
## Comparison operators

### Equality operators 🕙

- We can compare two values using the equality operators **==**
- Using the equality operators we get a **boolean** value as result (true or false)
- This type of equality only compares values (or the current values of variables) by value
- For example using this operator we can compare a number value and string value with a number
- If both values are equal we get **true** as result
- In case they are not the same value we'll get **false** as result

  **Example:**

  ```js
  let firstNumber = 20;
  let secondNumber = 20;
  let thirdNumber = 10;

  console.log(firstNumber == secondNumber); // true 
  console.log(firstNumber == thirdNumber); // false
  ```

- As we only compare by value:

  **Example:**

  ```js
  console.log(10 == "10"); // This is true even though the variables have different value type
  ```

- Also we can know if the values are different using the inequality operator **!=**

  **Example:**

  ```js
  let firstNumber = 20;
  let secondNumber = 20;
  let thirdNumber = 10;

  console.log(firstNumber != secondNumber); // false
  console.log(firstNumber != thirdNumber); // true
  ```

- Other way to compare values is to know if a value is greater than the other
- The greater than operator **>** returns true if the left operand is greater than the right operand

  **Example:**

  ```js
  let firstNumber = 20;
  let secondNumber = 10;

  console.log(firstNumber > secondNumber); // true

  console.log(secondNumber > firstNumber); // false
  ```

- Also we can compare values by using the less than operator
- The less than operator **<** returns true if the left operand is less than the right operand

  **Example:**

  ```js
  let firstNumber = 20;
  let secondNumber = 10;

  console.log(secondNumber < firstNumber); // true

  console.log(firstNumber < secondNumber); // false
  ```

- We can use the greater than or equal operator
- The greater than or equal operator >= returns true if the left operand is greater than or equal to the right operand

  **Example:**

  ```js
  let firstNumber = 20;
  let secondNumber = 10;
  let thirdNumber = 20;

  console.log(firstNumber >= secondNumber); // true

  console.log(firstNumber >= thirdNumber); // true
  ```

- We can do the same using less than or equal
- The less than or equal operator **<=** returns true if the left operand is less than or equal to the right operand

  **Example:**

  ```js
  let firstNumber = 20;
  let secondNumber = 10;
  let thirdNumber = 10;

  console.log(secondNumber <= firstNumber); // true
  console.log(secondNumber <= thirdNumber); // true
  ```

### Strict Equality Comparison 🕙

- The strict equality operators **===** and **!==** use the Strict Equality Comparison Algorithm and are intended for performing equality comparisons on operands of the **same type**

  **Example:**

  ```js
  console.log(10 === "10"); // false

  console.log(10 !== "10"); // true
  ```

- Read more about the [comparison operators on MDN site](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)

#### Practice

[Exercise 34](./exercises/js/ex_34.md)

[Exercise 35](./exercises/js/ex_35.md)

## Logical Operators 🕙

- Logical operators are typically used with Boolean (logical) values
- When they are, they return a **Boolean** value
- We can use the **`&&`** **"Boolean AND" operator** to know if both expressions are true
- We can know if the user age is greater than 18 and the password is equal to another value
- In this case we'll get a true value if both expressions are true
- If one of the expressions is **false**, we get false as the return value too

  **Example:**

  ```js
  let age = 20;
  let password = "js1234";
  let result = age >= 18 && password === "js1234";
  console.log("Result: ", result); // We get true as both expressions are true
  ```

- In this example we get **true** as both expressions are **true**
- We also have the **`||`** **"Boolean OR" operator** to check if at least one of the expressions is true
- Using this operator we only need one of the expressions to be true
- If the first expression is true the following one is not evaluated
- If the first expression is false then the following one is evaluated
- At least one of the expressions needs to be true to get a true value
- If not we'll get false as the result

  **Example:**

  ```js
  let age = 20;
  let password = "js12345";
  let result = age >= 18 || password === "js1234";
  console.log("Result: ", result); // true
  ```

- In this case the condition is **true** as the user age is greater than 18 (first expression)
- It doesn't matter if the password is the same or not as the first expression is true

  **Example:**

  ```js
  let age = 10;
  let password = "js1234";
  let result = age >= 18 || password === "js1234";
  console.log("Result: ", result); // true
  ```

- In this case the condition is **true** as the password is correct
- It doesn't matter if the age is not greater than or equal to 18

  **Example:**

  ```js
  let age = 10;
  let password = "js12345";
  let result = age >= 18 || password === "js1234";
  console.log("Result: ", result); // false
  ```

- In this case we get **false** as both expressions are false
- [MDN logical operators doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)

## Negation /nɪˈɡeɪʃən/  🕙

- Using the not operator **!** we can negate a condition
- If we have a **true** value and we use the not operator we get **false**
- If we have a **false** value and we use the not operator we get **true**

  **Example:**

  ```js
  console.log(!true); // false
  console.log(!false); // true
  ```

- We can use the not operator like this:

  **Example:**

  ```js
  let age = 21;
  let result = age < 18;

  console.log("User age greater than or equal to 18?: ", !result);
  ```

- The age condition is **false** but as we use the not operator it will be **true**

#### Practice

[Exercise 36](./exercises/js/ex_36.md)

[Exercise 37](./exercises/js/ex_37.md)

## String special characters

- Strings support some special characters that will provide extra functionality
- \n New Line
- \t Tab
- \r Carriage Return

  **Example:**

  ```js
  let message = "Multiline \n text";

  console.log(message); // two lines text

  message = "\t \t tab text";

  console.log(message); // tab text
  ```

- Special characters need to be "escaped" :
- \' Single quote
- \" Double quote
- \\ Backslash

  **Example:**

  ```js
  let message = "Escaping backslash \\ as string content";
  console.log(message); // we show \ as string content

  message = "I love to have coffee at Gianu's";

  console.log(message);

  message = 'Riders are "the" best CFL team';

  console.log(message);
  ```

#### Practice

- Open a browser console or node repl and try all the examples to see the output

