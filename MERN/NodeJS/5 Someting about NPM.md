# Someting about NPM

NPM is a package manager for Node.js.

## `package.json`

NPM uses a JSON file called `package.json` to store information about your project.

Two types of information are stored in `package.json`:

1. **Dependencies**: These are the packages that your project uses.
2. **Dev Dependencies**: These are the packages that your project uses for development.

```json
{
    "name": "my-app",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1"
    },
    "author": "",
    "license": "ISC",
    "dependencies": {
        "express": "^4.17.1"
    },
    "devDependencies": {
        "nodemon": "^2.0.4"
    }
}
```