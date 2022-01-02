# JavaScript part J (Array)

[<- Home](README.md)
#### Array Part Two




#### Concat 🕙

- The **concat** method is used to merge two or more arrays
- This method does not change the existing arrays, but instead returns a new array
- [MDN array concat doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)

  **Example:**

  ```js
  const animals = ["dog", "cow", "cat"];
  const mutants = ["Professor X", "Cyclops", "Beast", "Jean Grey"];
  const animalsAndMutants = animals.concat(mutantes);

  console.log(animalsAndMutants);
  /*
  [ 
    'dog',
    'cow',
    'cat',
    'Professor X',
    'Cyclops',
    'Beast',
    'Jean Grey'
  ]
  */
  ```

### IndexOf 🕙

- The **indexOf** method `returns the first index at which a given element can be found` in the array
- This method returns -1 if the element is not present
- [MDN array indexOf doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)

  **Example:**

  ```js
  const mutants = ["Professor X", "Cyclops", "Beast", "Jean Grey"];

  mutants.indexOf("Beast"); // 2

  if (mutants.indexOf("Beast") > -1) {
    console.log("Beast is X-Men team member");
  }

  mutants.indexOf("Logan"); // -1

  if (mutants.indexOf("Logan") > -1) {
    console.log("Logan is X-Men team member");
  } else {
    console.log("Logan is on his own");
  }
  ```

- In the first example we get 2 as return value when asking to know if the value Beast is in the mutants array
- Then the if condition is true and we show the message
- In the second example we ask if the value Logan is in the mutants array
- We get -1 as is not a mutants item (We <3 Logan anyway!)

### toString

- The **toString** method returns a string representing the specified array and its elements
- [MDN array toString doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toString)

  **Example:**

  ```js
  const mutants = ["Professor X", "Cyclops", "Beast", "Jean Grey"];

  console.log(mutants.toString());
  // 'Professor X', 'Cyclops', 'Beast', 'Jean Grey'
  ```

- It's like calling `mutants.join(',');`

#### Practice

[Exercise 125](./exercises/js/ex_125.md)

[Exercise 126](./exercises/js/ex_126.md)

[Exercise 127](./exercises/js/ex_127.md)

[Exercise 128](./exercises/js/ex_128.md)

[Exercise 129](./exercises/js/ex_129.md)

[Exercise 130](./exercises/js/ex_130.md)

[Exercise 131](./exercises/js/ex_131.md)

[Exercise 132](./exercises/js/ex_132.md)

[Exercise 133](./exercises/js/ex_133.md)

[Exercise 134](./exercises/js/ex_134.md)

### ForEach (is a little bit similar to for, while loop)

- The **forEach** method executes a provided function once for each array element

  **Example:**

  ```js
  const students = ["nico", "pedro", "marta", "belen", "emilia"];

  students.forEach(function (student) {
    console.log(student);
  });
  ```

- In this example we use the forEach array method to iterate over each element of the students array
- We pass a function as parameter
- This anonymus function that we pass gets a parameter
- We can use any parameter name
- Only remember that this parameter is each array item

  **Example:**

  ```js
  const pets = ["Amelia", "Ciro", "Ulises", "Carlos"];

  pets.forEach(function (petName) {
    console.log(petName);
  });
  ```

- In this example we iterate each pets item
- The function parameter name is petName as we can name it the way we want
- We can add a second parameter to the function to know the item index

  **Example:**

  ```js
  const pets = ["Amelia", "Ciro", "Ulises", "Carlos"];

  pets.forEach(function (pet, index) {
    console.log("index", index);
    console.log(pet);
  });
  /*
    index 0
    Amelia
    index 1
    Ciro
    index 2
    Ulises
    index 3
    Carlos
  */
  ```

- In this example we can see how the index parameter changes value on each iteration
- [MDN array forEach doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)

#### Practice

[Exercise 135](./exercises/js/ex_135.md) 🕙( ```for``` loop will also work, but you need to use ```forEach``` for this exercise)

[Exercise 136](./exercises/js/ex_136.md)

### Map 

- The **map** method `creates a new array with the results of calling a provided function on every element` in the calling array

  **Example:**

  ```js
  const pets = ["Amelia", "Ciro", "Ulises", "Carlos"];

  const petsNameInUpperCase = pets.map(function (pet) {
    return pet.toUpperCase();
  });

  console.log(petsNameInUpperCase); // [ 'AMELIA', 'CIRO', 'ULISES', 'CARLOS' ] new array with all upper cases value
  console.log(pets); // ['Amelia', 'Ciro', 'Ulises', 'Carlos'] the pets array hastn't been modified
  ```

- In this example we see how to iterate over each pets item
- On each iteration the function is going to be executed and we can return a value
- Each returned value is going to be an item on the array that map will return once is over iterating all items
- As we are returning a value then we can change it
- In this example we transform each pet name into upercase
- The original array is not modified
- [MDN array map doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

#### Practice

[Exercise 137](./exercises/js/ex_137.md) 🕙

[Exercise 138](./exercises/js/ex_138.md)

### Filter 

- The **filter** method creates a new array with all elements that pass the test implemented by the provided function
- The iterated item will be part of the returned array only if the functions return a true value
- If the function returns false then the item doesn't get added to the return array

  **Example:**

  ```js
  const greades = [1, 2, 3, 4, 10, 5];

  const goodGreades = grades.filter(function (grade) {
    return grade === 10;
  });

  console.log(goodGreades); // [10] array with only one item
  console.log(greades); // [1, 2, 3, 4, 10, 5] origina array
  ```

#### Practice

[Exercise 139](./exercises/js/ex_139.md) 🕙

[Exercise 140](./exercises/js/ex_140.md)

### Reduce* (⚠️Optional, not suitable for our class)

- The **reduce** method applies a function against an accumulator and each element in the array (from left to right) to `reduce it to a single value`
- The reduce function that we pass as parameter accepts the following parameters:

  - The first param is the **accumulator**
  - The second value is the **currentValue**

  **Example:**

  ```js
  const numbers = [1, 2, 3, 4, 10, 5];
  const result = numbers.reduce(function (accumulator, currentValue) {
    return accumulator + currentValue;
  });

  console.log(result); // 25 We get only one value as final result
  ```

- [MDN array reduce doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

#### Practice

[Exercise 141](./exercises/js/ex_141.md)

[Exercise 142](./exercises/js/ex_142.md)

- Learn more about array methods on the [MDN array doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
