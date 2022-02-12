# JavaScript part I (Functions)
[<- Home](README.md)
## Functions 

- In JavaScript **function** is a value
- We use functions to group functionality
- Using functions allows us to avoid repeating code
- Use the **function** reserved word to define a function
- We need to define the function before executing it
- Use the function name and () to call the given function

  **Example:**

  ```js
  function greeting() {
    console.log("Hello");
  }

  greeting(); // Shows Hello as output
  greeting(); // Shows Hello as output
  ```

- In this example we define a greeting function
- Then we call the greeting function using ()
- Each time we call the greeting function it will execute the function block code
- That's why we output 2 times hello as the greeting function only has a console.log('Hello');
- Now we can use this function many times without having to repeat the code
- We can also use functions to test our code too

#### Practice

[Exercise 100](./exercises/js/ex_100.md)  (you could check your index68.js)

[Exercise 101](./exercises/js/ex_101.md)

- In JavaScript functions are a type of value so we can assign
- We can assign a function to a variable
- When we assign a function to a variable we don't need to name our function as we have the variable for
- Functions without a name are considered anonymous

  **Example:**

  ```js
  // Look how we don't name our function, we just assign it
  const greeting = function () {
    console.log("Hello");
  };

  greeting(); // Shows Hello as output
  greeting(); // Shows Hello as output
  ```

- In this example we define a **greeting** and then assign a **function** value
- Assigning the variable works the same way that any other data type (string, number, boolean)
- This is because a function is a JavaScript data type!! :)

#### Practice

[Exercise 102](./exercises/js/ex_102.md) 🕙

[Exercise 103](./exercises/js/ex_103.md)

[Exercise 104](./exercises/js/ex_104.md)

- A function might return a value
- When a function doesn't explicit return a value it will return a **undefined** value
- To explicit return a value from a function we use the **return** reserved keyword

  **Example:**

  ```js
  function getGreetingMessage() {
    return "Hello";
  }

  getGreetingMessage();
  ```

- The first time we call the getGreetingMessage() the function gets executed, returns a string value with the word Hello
- We are not doing anything with the returned value

  **Example:**

  ```js
  function getGreetingMessage() {
    return "Hello";
  }

  console.log(getGreetingMessage());
  ```

- In this example we call the function getGreetingMessage() we get a string back
- Then we get that returned string value and print it using console.log()
- We can use the returned value for anything for example we can assign it to a variable

  **Example:**

  ```js
  function getGreetingMessage() {
    return "Hello";
  }

  const greeting = getGreetingMessage();
  console.log(greeting);
  ```

- This example shows how to call the getGreetingMessage() function, get the string back and then assign it to a variable
- Once we have the value in a variable we can do anything like console.log(greeting)
- A function can also return any data type

  **Example:**

  ```js
  function getUserAge() {
    return 30;
  }

  function isUserLoggedIn() {
    return true;
  }
  ```

- In this example both functions return a different data type
- The getUserAge function returns a number
- The isUserLoggedIn function returns a boolean
- We can also use the returned value as conditionals

  **Example:**

  ```js
  function getUserAge() {
    return 30;
  }

  function isUserLoggedIn() {
    return true;
  }

  if (getUserAge() >= 18) {
    console.log("The user is older than 18");
  }

  if (isUserLoggedIn()) {
    console.log("welcome to the site");
  }
  ```

- In the first if statement we call the getUserAge function and get a number back (30)
- Then we compare that to know if the returned valur is bigger or equal to 18
- In the second if statement we call the isUserLoggedIn, get a boolean value back
- If the returned value is true then we show the message to the user
- If it's false then the if statement block won't be executed

#### Practice

[Exercise 105](./exercises/js/ex_105.md)🕙 (meaning of life return 42)

[Exercise 106](./exercises/js/ex_106.md)

- Functions can accept none, one or many parameters
- We can have more flexible functions using parameters
- Also we can reuse the function functionality for different parameters values
- Define the amount of functions parameters while defining the function
- Also we can name each parameter so it has more context inside the function
- We can use the functions parameters inside the function block content

  **Example:**

  ```js
  function(firstParameter, secondParameter, thirdParameter) {
    console.log(firstParameter, secondParameter, thirdParameter);
  }
  ```

- We can use parameter the following way:

  **Example:**

  ```js
  function greeting(username) {
    console.log("Hi " + username + "!!!");
  }

  greeting("Marta"); // Hi Marta!!!
  greeting("Xime"); // Hi Xime!!!
  greeting("Raul"); // Hi Raul!!!
  ```

- There's a lot going on in this example:

  - Define the **greeting** named function
  - The greeting function accepts a **username** parameter
  - **username** works as an function internal variable
  - The **username** param will get the value that we pass calling the function
  - The first time we call the greeting function we pass 'Marta' as parameter and it will become the username in the greeting block content
  - We can pass a function different parameters values (example: Marta, Xime, Raul)

  **Example:**

  ```js
  const greeting = function (username) {
    console.log("Hi " + username + "!!!");
  };

  greeting("Marta"); // Hi Marta!!!
  greeting("Xime"); // Hi Xime!!!
  greeting("Raul"); // Hi Raul!!!
  ```

- We can also use parameters using anonymous functions and using them as variables values
- Refactor the code so the function returns a value instead of showing it as output

  **Example:**

  ```js
  const getGreetingMessage = function (username) {
    return "Hi " + username + "!!!";
  };

  console.log(getGreetingMessage("Marta")); // Hi Marta!!!
  console.log(getGreetingMessage("Xime")); // Hi Xime!!!
  console.log(getGreetingMessage("Raúl")); // Hi Raul!!!
  ```

- In this case we define a **getGreetingMessage** variable and assing a function as value
- The assigned function accepts a **username** parameter
- Now we can call the function the same way as before **getGreetingMessage()**
- To pass the parameter we just add the value this way: **getGreetingMessage('Marta')**
- The **getGreetingMessage** returns a string with the message hi and concatenates the username value
- Then we call the **getGreetingMessage('Marta')** and get the following string in return: Hi Marta!!!
- Changing the function parameters changes the returned value
- Also, a function can accept more parameters
- It's important to pass the parameters in the same order when we define and call the function

  **Example:**

  ```js
  const greeting = function(username, age) {
    console.log('The user: ' + username + ' has ' + age + ' years!!!';
  }

  greeting('Nico', 39); // The user: Nico has 39 years!!!
  greeting(18, 'Marta'); // The user: 18 has Marta years!!!
  ```

- The first call has the right parameters order, so we get the expected result
- In the second call we get we pass the parameters order in the wrong way so we get an unexpected result back

#### Practice

[Exercise 107](./exercises/js/ex_107.md)

[Exercise 108](./exercises/js/ex_108.md)

r[Exercise 109](./exercises/js/ex_109.md)🕙 (review if condition )

[Exercise 110](./exercises/js/ex_110.md)

[Exercise 111](./exercises/js/ex_111.md) 👈 (Optional! challenge yourself if 109 is done, ```even number, if condition```)

[Exercise 112](./exercises/js/ex_112.md)

[Exercise 113](./exercises/js/ex_113.md)

[Exercise 114](./exercises/js/ex_114.md)

[Exercise 115](./exercises/js/ex_115.md)

[Exercise 116](./exercises/js/ex_116.md)