# JavaScript part E (String)

[<- Home](README.md)
## String object properties and methods

### Length 🕙

- The **length** property of a **String object** indicates the length of a string
- This property returns the **number** of code units in the string

  **Example:**

  ```js
  const text = "Welcome to JavaScript!!";
  const characterCount = text.length;

  console.log(characterCount); // 24
  ```

  **Example:**

  ```js
  const text = "Welcome to JavaScript!!";

  console.log(text.length);
  ```

  **Example:**

  ```js
  console.log("Welcome to JavaScript!!".length);
  ```

- Strings have a length property that allows us to know the string value length (characters)
- We can use it with string literals
- We can also use it on a string stored in a variable
- Finally we can store the length in a variable too in case we need it
- [MDN length doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)

#### Practice

[Exercise 38](./exercises/js/ex_38.md)

[Exercise 39](./exercises/js/ex_39.md)

## Concat (Optional. We have learnt this in lesson 3)

- Using the **+** operator we can concatenate string values
- The String object has a **concat** method to do the same using methods instead of operators
- [MDN concat doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat)

  **Example:**

  ```js
  const text = "My mom name is "; // Note the trailing space!  It's a common mistake to forget whitespace when using concat
  const name = "Marta";

  // We get one string back as result with both strings concatenated
  const message = text.concat(name);

  console.log(message); // My mom name is Marta

  console.log(text); // My mom name is

  console.log(name); // Marta
  ```

- Some methods might change the object value
- In this case concat only returns a new string without changing the original values
- The concat method also accepts multiple parameters

  **Example:**

  ```js
  const text = "Java"; // Sometimes we don't want that trailing space ;)

  console.log(text.concat("Script", " is the best", " Programming language!!"));
  ```

- The concat method will return the following string: **JavaScript is the best Programming language!!**
- In this example we used concat with many parameters using literal strings
- We can also use variables

#### Practice

[Exercise 40](./exercises/js/ex_40.md)

### Upper and lower case 🕙

- Using the **toUpperCase** & **toLowerCase** we can transform our text to upper and lower case

  **Example:**

  ```js
  const upperCaseText = "HELLO";
  const lowerCaseText = "friends";

  console.log(upperCaseText.toLowerCase()); // hello
  console.log(lowerCaseText.toUpperCase()); // FRIENDS

  console.log(upperCaseText); // HELLO
  console.log(lowerCaseText); // friends
  ```

#### Practice

[Exercise 41](./exercises/js/ex_41.md)

[Exercise 42](./exercises/js/ex_42.md)

### String characters position 🕙

- The **charAt** method returns the character at the specified index
- This method accepts a number parameter to specify the index position
- Index in JavaScript starts in 0
- The first character will be at the 0 index position

  **Example:**

  ```js
  const text = "JavaScript rocks!! right?";
  const firstCharacter = text.charAt(0);

  console.log(firstCharacter); // J

  console.log(text.charAt(0)); // J
  ```

- To know the last string character we can combine charAt and the length property
- As length will return the amount of characters and the index starts at 0 to know the last character we need to substract one from the length value

  **Example:**

  ```js
  const text = "JavaScript rocks!! right?";
  const lastCharacterPosition = text.length - 1;
  const lastCharacter = text.charAt(lastCharacterPosition);

  console.log(lastCharacter); // ?

  console.log(text.charAt(text.length - 1)); // ?
  ```

#### Practice

[Exercise 43](./exercises/js/ex_43.md)

[Exercise 44](./exercises/js/ex_44.md)

### String slice 🕙

- The **slice** method extracts a section of a string and returns it as a new string
- This method accepts two parameters slice(start, end)
- Use 0 index for the beginning of the text
- The end parameter is optional and if we don't pass any value it will return the rest of the text

  **Example:**

  ```js
  const text = "I <3 JavaScript!!";
  const result = text.slice(4, 15);

  console.log(result); // JavaScript
  ```

- Counting from the beginning we have 4 index before the **J** letter
- Then we slice the string until the 15 index
- The final result is the JavaScript word
- Also we can avoid passing the second slice parameter and get the rest of the text from a starting point until the end

  **Example:**

  ```js
  const text = "I <3 JavaScript!!";
  const result = text.slice(4);

  console.log(result); // JavaScript!!
  ```

- The end parameter can be a negative value
- When using negative values it will position at the end of the string and start counting backwards

  **Example:**

  ```js
  const text = "JavaScript and Java are not the same";
  const result = text.slice(0, -25); // JavaScript

  console.log(result);
  ```

#### Practice

[Exercise 45](./exercises/js/ex_45.md)

- The **substr** method returns the part of a string between the start index and a number of characters after it
- We can also use 2 parameters (start and end)
- First parameter is the substring start
- Second parameter is the number of characters

  **Example:**

  ```js
  const text = "I love JavaScript!!";
  const result = text.substr(7, 10);

  console.log(result); // JavaScript
  ```

  **Example:**

  ```js
  const text = "I love JavaScript!!";
  const jsText = "JavaScript";
  const result = text.substr(7, jsText.length);

  console.log(result); // JavaScript
  ```

#### Practice

[Exercise 46](./exercises/js/ex_46.md)

- You can learn more about [slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice) and [substr](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr) reading the MDN guides

### String split 🕙

- The **split** method splits a String object into an array of strings by separating the string into substrings, using a specified separator string to determine where to make each split
- The first method parameter will be the separator value to split the string by (also known as a "delimiter")
- We'll get an **array** object as result
- For now think about an **array** as a list or collection of elements (in this case strings)
- Learn more about the [split](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) method on the MDN guide

  **Example:**

  ```js
  const friends = "tute, mati, pepe, raul, juan, marta, agus, loli";
  const friendsArray = friends.split(",");

  console.log(friendsArray);
  /* 
  [ 
    'tute',
    ' mati',
    ' pepe',
    ' raul',
    ' juan',
    ' marta',
    ' agus',
    ' loli' 
  ]
  */
  ```

#### Practice

[Exercise 47](./exercises/js/ex_47.md)

- The String object has a lot of methods that we can use
- Read about them on the [MDN string guide - methods section](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- Read about:
  - String.prototype.includes()
  - String.prototype.indexOf()
  - String.prototype.repeat()
  - String.prototype.replace()
  - String.prototype.trim()
  - And more
- Try using these methods on your own code!! `it will be 'fun'.toUpperCase()`
- We don't need to memorize all the methods, just know that they exist and what they can do for us :)
