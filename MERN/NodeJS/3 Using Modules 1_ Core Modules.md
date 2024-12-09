# Using Moudules 1 - Core Modules

## Reading and Writing Files

```javascript
const fs = require("fs");

const textIn = fs.readFileSync("./txt/input.txt", "utf-8");
console.log(textIn);

const textOut = `This is what we know about the avocado: ${textIn}.\nCreated on ${Date.now()}`;
fs.writeFileSync("./txt/output.txt", textOut);
console.log("File has been written");
```

## Blocking vs Non-Blocking

| Syncronous |                                      Asyncronous                                      |
| :--------: | :-----------------------------------------------------------------------------------: |
|  blocking  | non-blocking code, it will not stop the execution of the code until the task is done. |

## Node.js Process

| Single Thread | Muti-Thread  |
| :-----------: | :----------: |
|   Blocking    | non-blocking |

It's wise to use **non-blocking code** in Node.js because it's single-threaded.

**Callback function** is a function that is passed as an argument to another function and is executed after some operation has been completed.

## Reading and Writing Files Asynchronously

```javascript
const fs = require("fs");

fs.readFile("./txt/start.txt", "utf-8", (err, data) => {
  console.log(data);
});
console.log("Will read file");
```

The output will be:

```text
Will read file
read-this
```
