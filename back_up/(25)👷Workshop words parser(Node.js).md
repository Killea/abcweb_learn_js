The Adventures of Sherlock Holmes by Arthur Conan Doyle
https://www.gutenberg.org/ebooks/1661

We will develop a program that count words in this book.


const fs = require("fs");


```js
fs.readFile("C:\\Users\\hankw\\Downloads\\1661-0.txt", "utf8", (err, data) => {
  if (err) {
    console.error(err);
    return;
  }

  const wordsArray = data
    .split(" ")
    .filter((i) => i !== "")
    .map((i) => i.trim().toLowerCase());
  const result = [];
  for (let i = 0; i < wordsArray.length; i++) {
    const currentWord = wordsArray[i].trim();
    if (result.map((item) => item.word).includes(currentWord)) {
      const lookedObj = result.find((item) => item.word === currentWord);
      lookedObj.count = lookedObj.count + 1;
    } else {
      result.push({ word: currentWord, count: 1 });
    }
  }

  sorted = result.sort((a, b) => b.count - a.count);

  fs.writeFile("sorted.txt", JSON.stringify(sorted, null, 2), (err) => {
    if (err) {
      console.error(err);
      return;
    }
    //file written successfully
  });
});
```