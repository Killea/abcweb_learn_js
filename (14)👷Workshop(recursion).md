# JavaScript part J (Array)

[<- Home](README.md)

### Recursion 🕙

- Recursion is an act of a function calling itself
- Is used to solve problems that contain smaller sub-problems
- In JavaScript we can call a function inside that same function
- It's really important when using recursion to add a way to break to avoid recursion for ever

  **Example:**

  ```js
  function showNumber(number) {
    if (number <= 10) {
      console.log(number);
      number = number +1;
      // number++;
      showNumber(number);
    }
  }

  showNumber(0);
  ```

- **showNumber** is a recursive function
- If number is bigger than 10 the **showNumber** function stops calling itself

- [Microsoft - JavaScript recursion](https://docs.microsoft.com/en-us/scripting/javascript/advanced/recursion-javascript)
- [Difference between recursion and iteration](https://techdifferences.com/difference-between-recursion-and-iteration-2.html)
