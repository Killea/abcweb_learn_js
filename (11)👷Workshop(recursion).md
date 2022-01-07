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


👷Workshop: factorial

What is a factorial?
Factorial Symbol	
The factorial function (symbol: !) says to multiply all whole numbers from our chosen number down to 1.

Examples:

**factorial of 4** means 4 × 3 × 2 × 1 = 24

**factorial of 7** means 7 × 6 × 5 × 4 × 3 × 2 × 1 = 5040


```

function jc( val)
{

    if (val === 0)
    {
        return BigInt(1);
    }
    return BigInt(val)* jc(val-1);
}

console.log(jc(400))
```