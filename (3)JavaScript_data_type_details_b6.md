
# JavaScript part A (string)

[<- Home](README.md)
### String concatenation (connect 2 or more strings)

- The `+` operator allows us to concat two or more strings together

  **Example:**

  ```js
  const name = "Juan";
  const space = " ";
  const lastName = "Perez";

  console.log(name + space + lastName);
  ```

- In this example we concat all values using the `+` operator
- We might not need to use a variable for the space and we can use a string literal instead

  **Example:**

  ```js
  const name = "Juan";
  const lastName = "Perez";

  console.log(name + " " + lastName);
  ```
- In this example we see how to use a literal value without being assigned to a variable

#### Practice

[Exercise 12](./exercises/js/ex_12.md) 

[Exercise 13](./exercises/js/ex_13.md)

[Exercise 14](./exercises/js/ex_14.md)

### Template literals

- In ES6 we have `template literals` that will help us write better string templates
- To write a template literal we use **``** (back-tick)
- Then we use the following syntax to add template values `${variable}`
- Once the code gets executed the JavaScript engine will replace the variable value inside the string one
- Take a look at the following example to better understand this concept
- [MDN template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

  **Example:**

  ```js
  const name = "Pedro";
  const template = `Welcome ${name} to this great site`;

  console.log(template);
  ```

  - We can get the same result using templates or string concat
- Using templates looks like an easier way to do it!!

#### Practice

[Exercise 15](./exercises/js/ex_15.md) 🕙
<details>
<summary><b>Exercise 15</b></summary>

# Exercise 15

* Create a new index15.js file
* Define a **best student name** variable (camel case)
* Assign the variable the class best student name (string)
* Use console.log to show the following message: The best student is: %bestStudentName%
* Use Template literals and interpolate the bestStudentName variable value

The result should be like:
```
The best student is Kevin
```

</details>

[Exercise 16](./exercises/js/ex_16.md)

[Exercise 17](./exercises/js/ex_17.md)


### Numbers🕙

- JavaScript also supports number type
- This type of value doesn't use quotes

  **Example:**

  ```js
  const age = 38;
  const capacity = 50;

  console.log(age);
  console.log(capacity);
  ```

#### Practice

[Exercise 20](./exercises/js/ex_20.md)

<details>
<summary><b>Exercise 15</b></summary>

# Exercise 20

* Create a new index20.js file
* Define a **day** variable and assign todays day number (number)
* Define a **month** variable and assign todays month number (number) (from 1 to 12)
* Define a **year** variable and assign todays year (number) (4 digits)
* Use a template variable to show the date with the following format: d/m/yyyy
</details>

[Exercise 21](./exercises/js/ex_21.md)

- A common mistake is to code numbers as strings

  **Example:**

  ```js
  const age = 38;
  const capacity = "50";
  ```

  > In this example we have two variables that it looks like we are assigning number values.
  > Age has a number type and capacity has a string value with the representation of a number.
  > Having different types allows us to do different types of operations, for example we can add or subtract numbers but not strings

- We'll talk later about doing math using number type values

### Boolean🕙

- This type of value only accepts `true or false` as value

  **Example:**

  ```js
  const on = true;
  const voted = false;
  const married = false;

  console.log(on);
  console.log(voted);
  console.log(married);
  ```

#### Practice

[Exercise 22](./exercises/js/ex_22.md)


### Undefined🕙

- A variable that has not been assigned a value is of type **undefined**
- A method or statement also returns undefined if the variable that is being evaluated does not have an assigned value
- A function returns undefined if a value was not returned
- Also we can assign it as a value to a variable

  **Example:**

  ```js
  const variableWithoutDefinition = undefined;

  console.log(variableWithoutDefinition);
  ```

- We might need to assign **undefined** in some special cases, most of the time we don't need to do this

#### Practice

[Exercise 23](./exercises/js/ex_23.md)


### Null🕙

- In JavaScript we also have a **null** value
- We can assign a variable a null value

  **Example:**

  ```js
  const nullVariable = null;

  console.log(nullVariable);
  ```
#### Practice

[Exercise 24](./exercises/js/ex_24.md)

### typeof🕙

- The **typeof** operator returns a string indicating the type of the unevaluated operand

  **Example:**

  ```js
  const name = "Marta";
  const age = 30;
  const married = false;
  const undefinedVar = undefined;
  const nullVar = null;

  console.log(typeof name); // string
  console.log(typeof age); // number
  console.log(typeof married); // boolean
  console.log(typeof undefinedVar); // undefined
  console.log(typeof nullVar); // object
  ```

- In this example we can see that typeof will return different values for different data types
- For **null** it will return `object`! Now that was unexpected...
- Object is a different type of JavaScript data value and we'll talk more about it in a different section

#### Practice

[Exercise 25](./exercises/js/ex_25.md)

[Exercise 26](./exercises/js/ex_26.md)