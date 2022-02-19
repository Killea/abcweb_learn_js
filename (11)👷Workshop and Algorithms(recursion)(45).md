# JavaScript part J (Array)

[<- Home](README.md)

ℹ️Review last class' exercise

(1) Be careful about the logic of the **if/else if**

(2) Try to reduce repetition
  You could try to use multiple functions.

  
```js
function validateUser(username, password) {
  if (
    (username == "nacho" && password == "Nerd1979") ||
    (username == "pedro" && password == "Batman2017") ||
    (username == "marta" && password == "mother2312")
  ) {
    console.log("Welcome " + username + " , nice to see you again");
    return;
  } 
  console.log("Please enter valid credidentals");
}
validateUser("a", "Nerd1979");
validateUser("nacho", "Nerd1979");
```

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
      number = number +1; // number++;
      showNumber(number);
    }
  }

  showNumber(0);
  ```

- **showNumber** is a recursive function
- If number is bigger than 10 the **showNumber** function stops calling itself

- [Microsoft - JavaScript recursion](https://docs.microsoft.com/en-us/scripting/javascript/advanced/recursion-javascript)
- [Difference between recursion and iteration](https://techdifferences.com/difference-between-recursion-and-iteration-2.html)


👷Workshop: factorial<sup>/fækˈtɔːriəl/</sup>

What is a factorial?
Factorial Symbol	
The factorial function (symbol: !) says to multiply all whole numbers from our chosen number down to 1.

Examples:

**factorial of 4** means 4 × 3 × 2 × 1 = 24

**factorial of 7** means 7 × 6 × 5 × 4 × 3 × 2 × 1 = 5040


```

function fa( val)
{

    if (val === 0)
    {
        return BigInt(1);
    }
    return BigInt(val)* fa(val-1);
}

console.log(fa(400))
```

Try to run this program in your browser and see what happens!
Question: How do we do that?