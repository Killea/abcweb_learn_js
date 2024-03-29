# JavaScript part K (Objects)
## Objects

[<- Home](README.md)

- An **object literal** is a list of zero or more pairs of property names and associated values of an object
- To define an object we use curly braces **{}**
- Objects allows us to define more complex values in a easier way

  **Example:**

  ```js
  {
  } // literal object
  const myObject = {}; // object assigned to a variable
  ```

#### Practice 

[Exercise 143](./exercises/js/ex_143.md)🕙

### Properties

- An object can have properties that will describe it
- Properties have a name (just like variables)
- To assign a value to a property we use colon
- Properties are separated using comas
- Properties can be of any type of value

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  console.log(person);
  ```

- We can access an object property using the object name, dot and the property name

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  console.log(person.name);
  console.log(person.age);
  ```

#### Practice

[Exercise 144](./exercises/js/ex_144.md)🕙

[Exercise 145](./exercises/js/ex_145.md)

- We can access a property that doesn't exist on the object and get undefined as value

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  console.log(person.married); // undefined
  ```

- Changing a property value can be done the same way that you would do it for a variable
- To access the property that will receive the value you need to still use the object name, dot and the property name

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  person.name = "Martin";
  person.age = 20;

  console.log(person);
  // { name: 'Martín', age: 20 }
  ```

- The object properties are variables too so we can assign or get their value
- Object properties in JavaScript are dynamic
- This means that if we assign a value to an object property that hasn't been defined it will create it
- We need to make sure we get the variable name wright

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  console.log(person.married); // undefined

  person.married = true;

  console.log(person);
  // { name: 'Nico', age: 38, married: true }

  console.log(person.married); // true
  ```

#### Practice

[Exercise 146](./exercises/js/ex_146.md)🕙

[Exercise 147](./exercises/js/ex_147.md)

[Exercise 148](./exercises/js/ex_148.md)

[Exercise 149](./exercises/js/ex_149.md)

### Methods

- JavaScript objects have methods
- In this language an object method is a property with a function as value

  **Example:**

  ```js
  const person = {
    name: "Nico",
    greet: function () {
      console.log("Hi, how are you?");
    },
  };
  ```

- In this example we define the person object and we assign two properties
  - name: it's just a string value
  - greet: has a function assigned as value
- To call a function without the object we do it the following way:

  **Example:**

  ```js
  const greet = function () {
    console.log("Hi, how are you?");
  };

  greet(); // Hi, how are you?
  ```

- To call a object method we do it in a pretty similar way:

  **Example:**

  ```js
  const person = {
    name: "Nico",
    greet: function () {
      console.log("Hi, how are you?");
    },
  };

  person.greet(); // Hi, how are you?
  ```

- `person.greet` without the parenthesis will return the function definition
- `person.greet()` will execute the greet method (it will execute the function code)

#### Practice

[Exercise 150](./exercises/js/ex_150.md)

[Exercise 151](./exercises/js/ex_151.md)

- We learned about Strings, Numbers and Arrays methods
- When we call a string, number or array literal methods JavaScript will transform the literal value into a object
- So calling `'text'` will transform into a String object and the same will happen with the others values types
- Now we can create our own
- A method can also accept parameters:

  **Example:**

  ```js
  const person = {
    name: "Nico",
    greet: function (name) {
      console.log(`Hi ${name}, how are you?`);
    },
  };

  person.greet("Marta"); // Hi Marta, how are you?
  ```

- In this example we see that calling a method is similar to calling just a function
- And this is because we are actually calling a function that's an object property
- In the methods body we can access the current object properties using the **this** reserved word
- For now we can think about **this** being the object

  **Example:**

  ```js
  const person = {
    name: "Nico",
    greet: function (name) {
      console.log(`Hi my name is: ${this.name}`);
    },
  };
  person.greet(); // Hi my name is: Nico
  ```

#### Practice

[Exercise 152](./exercises/js/ex_152.md)🕙

[Exercise 153](./exercises/js/ex_153.md)

[Exercise 154](./exercises/js/ex_154.md)

[Exercise 155](./exercises/js/ex_155.md)

[Exercise 156](./exercises/js/ex_156.md)

[Exercise 157](./exercises/js/ex_157.md)

[Exercise 158](./exercises/js/ex_158.md)

- Inside an object method we can update an object property value

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
    greet: function (name) {
      console.log(`Hi my name is: ${this.name}`);
    },
    birthday: function () {
      this.age++;
    },
  };

  console.log(person.age); // 38
  person.birthday();
  console.log(person.age); // 39
  ```

### Object dynamic properties

- In some cases we need to access an object property using a string value
- Using **[]** and a string value with the property name we can access the object property value

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
    greet: function (name) {
      console.log(`Hi my name is: ${this.name}`);
    },
    birthday: function () {
      this.age++;
    },
  };

  console.log(person["name"]); // Nico
  console.log(person["age"]); // 38
  ```

- We can also use variables to do the same

  **Example:**

  ```js
  const name = "name";
  const age = "age";

  const person = {
    name: "Nico",
    age: 38,
    greet: function (name) {
      console.log(`Hi my name is: ${this.name}`);
    },
    birthday: function () {
      this.age++;
    },
  };

  console.log(person[name]); // Nico
  console.log(person[age]); // 38
  ```

#### Practice

[Exercise 159](./exercises/js/ex_159.md)

[Exercise 160](./exercises/js/ex_160.md)

- Now that we know how to access dynamic properties from an object we'll learn about objects keys!
- `Object.keys` returns an array value with all the objects properties names (not the value)
- To call this method we need to use the `Object` value
- This method accepts an object as parameter

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  const properties = Object.keys(person);

  console.log(properties); // [ 'name', 'age' ]
  ```

- In this previous example we see that calling the Object keys method and passing the person object we get an array back with the properties names on it
- We can combine this using dynamic properties

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  const properties = Object.keys(person);

  console.log(properties); // [ 'name', 'age' ]

  const name = properties[0];

  console.log(person[name]);
  ```

- In this example we get the first item from the properties array (name)
- Then we use the name variable with the name value on it to access the object person name property
- This is getting gooooood, now we can use all the things that we learned together

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  const properties = Object.keys(person);

  properties.forEach(function (property) {
    console.log(person[property]);
  });
  ```

- We get the properties from the person object using Object keys method
- As we get an array back we can use forEach to iterate over the properties names
- On each iteration we get a property name value (name then age)
- We use the property variable (with the property value on it) to access dynamically to the person object properties
- If we add more properties to the object we can still access them using dynamic properties and iterating over the properties array

  **Example:**

  ```js
  const person = {
    name: "Nico",
    age: 38,
  };

  person.phone = 202123231;
  person.street = "234 My Street";

  const properties = Object.keys(person);

  properties.forEach(function (property) {
    console.log(person[property]);
  });

  /*
    Nico
    38
    202123231
    234 My Street
  */
  ```

- [MDN Object key doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)

#### Practice

[Exercise 161](./exercises/js/ex_161.md)🕙

[Exercise 162](./exercises/js/ex_162.md)
