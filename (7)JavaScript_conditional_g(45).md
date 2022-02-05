# JavaScript part G (Conditional)

[<- Home](README.md)

### Prettier - Code formatter (off topic)

We could try to install the code formatter to help you to format the code.

Search 'Prettier' in vs code's extension tab.

![Prettier](/resources/images/misc/prettier.png)


### If else if 🕙

- We can also use if else if to check for more conditions

  **Example:**

  ```js
  if (condition) {
    // This code gets executed if the condition it's true
  } else if (otherCondition) {
    // This code gets executed if the otherCondition it's true
  } else {
    // This code gets executed if none of the other conditions where true
  }
  ```

  ```js
  const name = "Marta";

  if (name === "Miriam") {
    console.log("The name is Miriam");
  } else if (nombre === "Felipa") {
    console.log("The name is Felipa");
  } else {
    console.log("The name is not Miriam or Felipa");
  }
  ```

- In this example we ask for different conditions
- We can keep on adding if else if statements to check for more conditions
- Our code might not as easy to read and follow if we use too many if else if statements
- Try to avoid nesting too many if else if statements

#### Practice

[Exercise 58](./exercises/js/ex_58.md)

[Exercise 59](./exercises/js/ex_59.md)

[Exercise 60](./exercises/js/ex_60.md)

### Switch 🕙

- The switch statement evaluates an expression
- Matching the expression's value to a case clause
- Then executes statements associated with that case
- If we don't break it will execute the follow the matching case

  ```js
  const name = "Marta";

  if (name === "Miriam") {
    console.log("The name is Miriam");
  } else if (nombre === "Felipa") {
    console.log("The name is Felipa");
  } else {
    console.log("The name is not Miriam or Felipa");
  }
  ```

- If we keep nesting statements it's going to be difficult to follow this code

  ```js
  const name = "Marta";

  if (name === "Miriam") {
    console.log("The name is Miriam");
  } else if (name === "Felipa") {
    console.log("The name is Felipa");
  } else if (name === "Xime") {
    console.log("The name is Xime");
  } else if (name === "Belu") {
    console.log("The name is Belu");
  } else {
    console.log("The name is not Marta, Felipa, Xime or Belu");
  }
  ```

- We can accomplish the same result using a **switch** statement

  **Example:**

  ```js
  const name = "marta";
  let message = null;

  switch (name) {
    case "Miriam":
      message = "The name is Miriam";
      break;
    case "Felipa":
      message = "The name is Felipa";
      break;
    case "Xime":
      message = "The name is Xime";
      break;
    case "Belu":
      message = "The name is Belu";
      break;
    default:
      message = "The name is not Marta, Felipa, Xime or Belu";
  }

  console.log(message);
  ```

- The optional **break** statement associated with each case label ensures that the program breaks out of switch once the matched statement is executed and continues execution at the statement following switch
- If break is omitted, the program continues execution at the next statement in the switch statement
- [MDN switch doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)

#### Practice

[Exercise 61](./exercises/js/ex_61.md)

[Exercise 62](./exercises/js/ex_62.md)

[Exercise 63](./exercises/js/ex_63.md)

## true and false (truthy and falsy values) 🕙

- In JavaScript we have values that are true and false
- This means that some values might be true and some values might be false
- For true and false values we use boolean
- When using some values as condition they will be evaluated as true (true) or false (false) values depending the value data type
- So, a **true** value is a value that is considered true when evaluated in a Boolean context
- All values are true unless they are defined as false
- A false value is a value that translates to false when evaluated in a Boolean context
- The following values are considered false values:

  - false
  - null
  - undefined
  - 0
  - NaN
  - ''

  **Example:**

  ```js
  if ("") {
    // This code won't get executed as an empty string is a false value
  } else {
    // This code gets executed
  }
  ```

  **Example:**

  ```js
  const name = "";

  if (name === "") {
    console.log("Please input your name");
  } else {
    console.log("Welcome: " + name);
  }
  ```

- We can also try the following condition

  **Example:**

  ```js
  const name = "";

  if (name) {
    console.log("Welcome: " + name);
  } else {
    console.log("Please input your name");
  }
  ```

- If name is empty then it will be evaluated as a false value so in this case we don't need to compare it to an empty string
- true and false values are an easy way to use some conditions
- One special case is using null:

  **Example:**

  ```js
  const name = null;

  if (name) {
    console.log("welcome: " + name);
  } else {
    console.log("Please input your name");
  }

  console.log(typeof name); // object
  ```

- When using null we'll have to add an extra validation

  **Example:**

  ```js
  const name = null;

  if (name && name !== null) {
    console.log("welcome: " + name);
  } else {
    console.log("Please input your name");
  }
  ```

- [MDN false doc](https://developer.mozilla.org/en-US/docs/Glossary/false)
- [MDN true doc](https://developer.mozilla.org/en-US/docs/Glossary/true)
- [MDN Type Conversion doc](https://developer.mozilla.org/en-US/docs/Glossary/Type_Conversion)

#### Practice

[Exercise 64](./exercises/js/ex_64.md)

[Exercise 65](./exercises/js/ex_65.md)
