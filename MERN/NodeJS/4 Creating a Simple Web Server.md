# Creating a Simple Web Server

## Simple Web Server Code Without URL Parsing

```javascript
const http = require("http");

const server = http.createServer((req, res) => {
  res.end("Hello from the Server!");
});

server.listen(8000, "127.0.0.1");
```

When you run the code, you will see the following output in the webpage:

```bash
Hello from the Server!
```

## Routing

```javascript
const server = http.createServer((req, res) => {
  const pathName = req.url;

  if (pathName === "/overview") {
    res.end("This is the overview");
  } else if (pathName === "/product") {
    res.end("This is the product");
  } else {
    // 404 Message
    res.writeHead(404, {
      "Content-type": "text/html",
      "my-own-header": "hello-world",
    });
    res.end("<h1>Error 404: Page not found</h1>");
  }
});
```

- `req.url` is the URL that the user is requesting.
- `res.writeHead()` is used to send a status code and headers to the client.
- `res.end()` is used to send the response body to the client.

## JSON

```javascript
if (pathName === "/api") {
  fs.readFile(`${__dirname}/dev-data/data.json`, "utf-8", (err, data) => {
    const productData = JSON.parse(data);

    res.writeHead(200, { "Content-type": "application/json" });
    res.end(data);
  });
}
```

- `fs.readFile()` is used to read a file from the file system.
- `JSON.parse()` is used to parse a JSON string into a JavaScript object.
- `res.writeHead()` is used to send a status code and headers to the client.
- `res.end()` is used to send the response body to the client.
- `__dirname` is a global variable that contains the directory name of the current module.

## Building the template html

...

## Filling the template html

Reffering to the code.
