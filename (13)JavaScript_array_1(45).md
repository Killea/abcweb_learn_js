# JavaScript part J (Array)

[<- Home](README.md)
#### Array 

- An **array** literal is a list of zero or more expressions
- Each value represents an array element
- The values are closed in square brackets **[]**
- Creating an array using an array literal, it's initialized with the specified values as its elements, and its length is set to the number of arguments specified
- This type of value allows us to store more than one value into a variable
- We create an array literal in the following way:

  **Example:**

  ```js
  ["nico", "pedro", "juan", "marta", "belen", "emilia", "xime"];
  ```

- In this example we have an array literal of names
- We have an array of string values
- The values look like people names
- This array has 7 items

  **Example:**

  ```js
  const people = ["nico", "pedro", "juan", "marta", "belen", "emilia", "xime"];

  // We can also write it in his way:
  const people = ["nico", "pedro", "juan", "marta", "belen", "emilia", "xime"];
  ```

- To assign an empty array we just assign the **[]** to a variable like this:

  **Example:**

  ```js
  const people = [];
  ```

- In JavaScript arrays can have mixed types of values

  **Example:**

  ```js
  const data = [
    "hello",
    42,
    false,
    null,
    function () {
      console.log("hi");
    },
  ];
  ```

- We can retrieve any array item using the item index
- In JavaScript array index starts in 0
- So the first array item index is 0

  **Example:**

  ```js
  const people = ["nico", "pedro", "juan", "marta", "belen", "emilia", "xime"];

  people[0]; // this will return the value 'nico'

  console.log(people[0]); // This will output nico that's the value we get from the array

  const name = people[0];

  console.log(name);
  ```

- Also, we can get any array item increasing the index value

  **Example:**

  ```js
  const data = [
    "hi",
    42,
    false,
    null,
    function () {
      console.log("hi");
    },
  ];

  const message = data[0];
  const lifeMeaning = data[1];
  const single = data[2];
  const nullValue = data[3];
  const greeting = data[4];

  console.log(message);
  console.log(lifeMeaning);
  console.log("single?:", single);
  console.log(greeting);

  // Ready to have your mind blown?
  greeting(); // This will show hi on the console
  ```

- In this example we see how to get different array items using different item index
- We can store many different items in an array
- The last example is kind of difficult so we'll see it again:

  **Example:**

  ```js
  // The data array has only one item and it's an anonymus function
  const data = [
    function () {
      console.log("hi");
    },
  ];

  // We ge the first element from the data index
  const greeting = data[0];

  // this would be the same, is it easier to see it this way?
  const greeting = function () {
    console.log("hi");
  };

  // In both cases we can call the greeting function
  greeting(); // hi
  ```

#### Practice

[Exercise 117](./exercises/js/ex_117.md) 

[Exercise 118](./exercises/js/ex_118.md)

[Exercise 119](./exercises/js/ex_119.md)

- Using index we can also assign new values to the array

  **Example:**

  ```js
  const students = [
    "nico",
    "pedro",
    "juan",
    "marta",
    "belen",
    "emilia",
    "xime",
  ];

  students[0] = "Pana"; // We replace nico by Pana

  students[3] = "Jorge"; // We replace marta by Jorge

  console.log(students);
  // ['Pana', 'pedro', 'juan', 'Jorge', 'belen', 'emilia', 'xime']
  ```

- We have to be careful using indexes
- If the array doesn't have assigned values in the given index it will create empty items

  **Example:**

  ```js
  const students = ["nico", "pedro", "marta", "belen", "emilia"];

  // We assign Paola as value in the 9th place (remember arrays start in 0 index)
  students[8] = "Paola";

  // As the original array only has 5 items it will create empty array items
  console.log(students);
  // [ 'nico', 'pedro', 'marta', 'belen', 'emilia', , , , 'Paola' ]
  ```

- JavaScript has dynamic memory so it's already reserving the spaces

  **Example:**

  ```js
  const students = ["nico", "pedro", "marta", "belen", "emilia"];

  // We assing a value to an index that it doesn't exists
  students[8] = "Paola";

  // We add more values to the empty items
  students[5] = "Lucas";
  students[6] = "Lucy";
  students[7] = "Andy";

  // We see that all items have a student name
  console.log(students);
  /*
  [ 
    'nico',
    'pedro',
    'marta',
    'belen',
    'emilia',
        'Lucas',
        'Lucy',
        'Andy',
    'Paola' 
  ]
  */
  ```

- In this example we don't leave any empty array items

#### Practice

[Exercise 120](./exercises/js/ex_120.md)  (you could try to use ```for``` loop)

[Exercise 121](./exercises/js/ex_121.md)

[Exercise 122](./exercises/js/ex_122.md)

## Array methods

### Length

- The **length** property of an object which `is an instance of type Array` sets or returns the number of elements in that array
- This property works in the same way as the string length property

  **Example:**

  ```js
  const students = ["nico", "pedro", "marta", "belen", "emilia"];

  console.log(students.length); // 5
  ```

- We can use this property to get the last item from an array
- Array index in JavaScript starts in 0
- The length property will return the number of elements
- To get the last element index we can subtract one from the array lenght

  **Example:**

  ```js
  const students = ["nico", "pedro", "marta", "belen", "emilia"];
  const studentCount = students.length;
  const studentsLastIndex = studentCount - 1;

  console.log(students[studentsLastIndex]); // emilia
  ```

- We can do in a different way:

  **Example:**

  ```js
  const students = ["nico", "pedro", "marta", "belen", "emilia"];

  console.log(students[students.length - 1]); // emilia
  ```

- In this example we use the students array to get the length
- Then we subtract one from the students array length
- Then we get a number as result and use it as students index
- [MDN array length doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length)

#### Practice

[Exercise 123](./exercises/js/ex_123.md)  ```"to upper case".toUpperCase()```

[Exercise 124](./exercises/js/ex_124.md)

### Push, unshift, shift & pop methods

- We can change an array element using the following methods **push, unshift, shift & pop**

#### Push 🕙

- The **push** method adds one or more elements to the `end of an array`
- This method returns the new length of the array
- [MDN array push doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

  **Example:**

  ```js
  const animals = ["dog", "duck", "cow"];
  let animalCount = animals.push("cat");

  console.log(animals);
  // [ 'dog', 'duck', 'cow', 'cat' ]

  console.log(animalCount); // 4

  animalCount = animals.push("elephant", "dolphin");

  console.log(animals);
  // [ 'dog', 'duck', 'cow', 'cat', 'elephant', 'dolphin' ];

  console.log(animalCount); // 6
  ```

- In this example we see how the **push** insert element at the array
- Also, we get the length number as return value
- We can pass one ('cat') or many items ('elephant', 'dolphin') to be added to the array
- The animals array gets updated on each **push** call
- Using const with array allows us to change the array items but we can't assign a new value to the variable
- More about [const and updating values in JavaScript](https://mathiasbynens.be/notes/es6-const)

#### Unshift (Optional)

- The **unshift** method adds one or more elements to the `beginning of an array`
- This method returns the new length of the array
- [MDN array unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)

  **Example:**

  ```js
  const animals = ["dog", "duck", "cow"];
  let animalCount = animals.unshift("cat");

  console.log(animals);
  // [ 'cat', 'dog', 'duck', 'cow' ]

  console.log(animalCount); // 4

  animalCount = animals.unshift("elephant", "dolphin");

  console.log(animals);
  // [ 'elephant', 'dolphin', 'dog', 'duck', 'cow', 'cat' ];

  console.log(animalCount); // 6
  ```

#### Shift  (Optional)

- The **shift** method `removes the first element` from an array and `returns that removed element`
- This method **changes the length** of the array
- [MDN array shift doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)

  **Example:**

  ```js
  const animals = ["dog", "duck", "cow"];
  const dog = animals.shift();

  console.log(animals);
  // ['duck', 'cow']

  console.log(animals.length); // 2

  const duck = animals.shift();

  console.log(animals);
  // ['cow']

  console.log(animals.length);
  // 1

  const cow = animals.shift();

  console.log(animals);
  // []

  console.log(animals.length);
  // 0

  console.log(dog); // dog
  console.log(duck); // duck
  console.log(cow); // cow
  ```

- Using the **shift** we can remove the first array element and get it as returned value
- The length array property changes as it has less elements

#### Pop 🕙 

- The **pop** method `removes the last element from an array`returns that element
- This method changes the length of the array
- [MDN array pop doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)

  **Example:**

  ```js
  const animals = ["dog", "duck", "cow"];
  const cow = animals.pop();

  console.log(animals);
  // ['dog', 'duck']

  console.log(animals.length);
  // 2

  const duck = animals.pop();

  console.log(animals);
  // ['dog']

  console.log(animals.length);
  // 1

  const dog = animals.pop();

  console.log(animals);
  // []

  console.log(animals.length);
  // 0

  console.log(cow); // cow
  console.log(duck); // duck
  console.log(dog); // dog
  ```

- We can see that some of the array methods works in the same way
- They might change the length property
- Some return the element from the begining or the end and return the element
- Some adds a new element to the begining or end and return the new array length

### Sort and reverse

#### Sort 🕙

- The **sort** method sorts the elements of an array in place and `returns the array`
- The sort is not necessarily stable
- The default sort order is according to string Unicode code points
- The time and space complexity of the sort cannot be guaranteed as it is implementation dependent
- [MDN array sort doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

  **Example:**

  ```js
  const numbers = [1, 4, 2, 5, 3, 8, 9];
  const sortedNumbers = numbers.sort();

  console.log(sortedNumbers);
  // [ 1, 2, 3, 4, 5, 8, 9 ]
  ```

- This method accepts a function as parameter to be executed to change the way it will sort the elements

#### Reverse 🕙

- The **reverse** method reverses an array in place
- The first array element becomes the last, and the last array element becomes the first
- [MDN array reverse doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)

  **Example:**

  ```js
  let numbers = [1, 4, 2, 5, 3, 8, 9];
  const reversedNumbers = numbers.reverse();

  console.log(reversedNumbers);
  // [ 9, 8, 3, 5, 2, 4, 1 ]
  ```

### Concat & join 

#### Join🕙

- The **join** method joins all elements of an array into a string and returns this string
- This method accepts a string value to join by
- [MDN array join doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

  **Example:**

  ```js
  const numbers = [1, 4, 2, 5, 3, 8, 9];

  const joinedNumbersByDash = numbers.join(" - ");

  console.log(joinedNumbersByDash);
  // 1 - 4 - 2 - 5 - 3 - 8 - 9

  const joinedNumbersByComma = numbers.join(", ");

  console.log(joinedNumbersByComma);
  // 1, 4, 2, 5, 3, 8, 9
  ```

- We can choose any string to join array items