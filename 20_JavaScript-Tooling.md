# JavaScript Tooling Overview

<img src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" style="margin-left: 75px; margin-top: 20px; margin-bottom: 20px" width="200"/>

## 1. JavaScript Runtimes

### Overview
JavaScript is an interpreted language and needs a `Host Environment` aka `JavaScript Runtime` to execute the code.

- **JavaScript Runtime**: Includes the JavaScript Engine, Web APIs, Input/Output, File System, and more.
- **JavaScript Engine**: The core component that interprets and executes the JavaScript code.

### Browser

Every browser has a `JavaScript Runtime` which has a `JavaScript Engine` to execute the code:

- **Chrome**: Includes `V8 Engine` as the JavaScript runtime.
- **Firefox**: Includes `Spider Monkey` as the JavaScript runtime.
- **Safari**: Includes `JavaScriptCore` JavaScript runtime.
- **Edge**: Based on `Chromium`, includes `V8 Engine` as the JavaScript runtime.

### Server

On the server-side or on the command line, we have different JavaScript runtimes:

- **Node**: A Runtime built on `Chrome's V8 engine`, enabling JavaScript to run outside the browser.
- **Deno**: A Runtime improving Node, focusing on security and developer experience.
- **Bun**: A Runtime build on `JavaScriptCore Engine`, and all-in-one tool for building, testing, and deploying applications.


## 2. JavaScript Frameworks

<p float="left">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbOFmjGchTMwQriXqezOovYKqXWK3YXUnFlQ&s" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="100"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/440px-React-icon.svg.png" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="100"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/200px-Vue.js_Logo_2.svg.png" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="100"/>
</p>

### Overview

When building bigger web/mobile applications, developers use JavaScript frameworks to manage the complexity.

### Browser

- **React**: Developed by Facebook in 2013.
- **Vue**: Developed by Evan You in 2014.
- **Angular**: Developed by Google in 2010/2016.

### Desktop

- **Electron**: Developed by GitHub in 2013.

### Mobile

- **Ionic**: Developed by Drifty Co. in 2013.

### Cross-Platform

- **React Native**: Developed by Facebook in 2015.


## 3. Install Node

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/7e/Node.js_logo_2015.svg/2560px-Node.js_logo_2015.svg.png" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="200"/>

### Overview
- **Link:** https://nodejs.org/en/
- **Purpose**: Node is a JavaScript runtime that allows you to run JavaScript outside the browser environment.
- **Developed By**: Ryan Dahl in 2009
- **JS Conf 2009**: [Ryan Dahl's Original Node.js Presentation](https://www.youtube.com/watch?v=ztspvPYybIY)

### Key Components
- **Node**: A JavaScript runtime that allows you to run JavaScript outside the browser environment.
- **NPM**: A package manager and CLI for managing dependencies and packages for Node projects.
- **NPX**: A tool to execute Node packages without installing them globally, ideal for one-off command-line uses.

### Installation
* **Install:** https://nodejs.org/en/download
* **Update with npm**: https://www.npmjs.com/package/n

```sh
# Check Node version
node -v

# Check NPM version
npm -v

# Check NPX version
npx -v
```


## 4. Execute JavaScript with Node

We are going to create a simple JavaScript file and run it using Node.

- **Create a directory `my-node-project`**:
```sh
mkdir my-node-project
cd my-node-project
```

- **Create a JavaScript file `main.js`**:
```javascript
const message = "Hello, Node! 😍";
console.log(message);
```

- **Run the JavaScript file `main.js`**:
```sh
node main.js
```

## 5. NPM

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/db/Npm-logo.svg/1200px-Npm-logo.svg.png" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="150"/>

### Overview
- **Link:** https://www.npmjs.com/
- **Purpose**: A package manager and command line tool, for setting up and managing Node based projects.
- **Developed By**: Isaac Z. Schlueter in 2009
- **Acquired By**: GitHub in 2020

### Key Features
- **Standard**: One of the standardized ways to create JavaScript based projects.
- **Manages Project**: Manages project dependencies and metadata in the `package.json` file.
- **Automates Project**: Automates project tasks using scripts defined in the `package.json` file.


## 6. Create NPM Project

We are going to create a simple NPM project and run it using NPM commands.

- **Create a directory `my-npm-project`**:
```sh
# Creates a new directory
mkdir my-npm-project
cd my-npm-project
```

- **Initialize a NPM based project**:

```sh
# Creates a new package.json file
npm init
```

- **Answer the following questions**:
```sh
package name: (my-npm-project) my-npm-project
version: (1.0.0)
description: The greatest app ever
entry point: (index.js) main.js
test command:
git repository:
keywords:
author: Your Name
license: (ISC)
```

- **package.json**:

Go to the `package.json` file and adjust the script `start` to run the `main.js` file.
```json
{
  "name": "my-npm-project",
  "version": "1.0.0",
  "description": "The greatest app ever",
  "main": "main.js",
  "scripts": {
    "start": "node main.js"
  },
  "author": "Your Name",
  "license": "ISC"
}
```

- **Create a JavaScript file `main.js`**:
```javascript
const message = "Hello, NPM! 🚀";
console.log(message);
```

- **Run the script `start` in package.json**:
```sh
npm start
```

## 7. Vite

<img src="https://vitejs.dev/logo.svg" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="100"/>

### Overview
- **Link:** https://vitejs.dev/
- **Purpose**: A fast build tool for modern JavaScript projects with a built-in development server.
- **Developed By**: Evan You, creator of Vue.js

### Key Features
- **Modern Build Tool**: A fast, modern frontend build tool with a built-in development server.
- **Live-Reload**: Instant live-reload (e.g., changes in the code are instantly reflected in the browser).
- **Bundler**: Bundler optimized for production builds (e.g., smaller, fewer files)
- **Plugins**: Rich plugin ecosystem (e.g., React, Angular, Vue, TypeScript, etc.)

## 8. Create Vite Project

We are going to create a simple Vite project and run it using NPM commands.

- **Create a directory `my-vite-project`**:
```sh
mkdir my-vite-project
cd my-vite-project
```

- **Initialize a Vite project**:

Creates a new Vite project in the current directory `./`.
```sh
npm init vite@latest ./
```

- **Answer the following questions**:
```sh
✔ Select a framework: › Vanilla
✔ Select a variant: › JavaScript
```

- **Install dependencies**:
```sh
npm install
```

- **Start the development server**:
```sh
npm run dev
```

- **Project Structure**:

Delete the unnecessary files and folders. The final project structure should look like this:

```sh
my-vite-project/
├── node_modules/     # NPM dependencies folder
├── public/           # Static files folder
│   ├── vite.svg
├── src/              # Source files folder
│   ├── styles.css
│   └── main.js
├── index.html        # Main HTML file
├── package.json      # NPM package file
└── vite.config.js    # Vite configuration file
```

- **`styles.css` file**:

Delete the content of the `styles.css` file but keep the file.

- **`main.js` file**:

Delete the content of the `main.js` file and add the following code:

```javascript
// Define a message
const message = "Hello, Vite! 🚀";

// Output a message to the Browser Console
console.log(message);

// Output a message to the Browser DOM
const app = document.getElementById("app");
app.innerHTML = "<h1>" + message + "</h1>";
```

## 9. Summary

### Concepts
- **JavaScript Runtimes**: Includes the JavaScript Engine, Web APIs, Input/Output, File System, and more.
- **JavaScript Frameworks**: Used to manage the complexity of bigger web/mobile applications (React, Angular, etc.).
- **Node**: A JavaScript runtime, that allows you to run JavaScript outside the browser environment.
- **NPM**: A package manager and command line tool, for setting up and managing Node based projects.
- **Vite**: A fast, modern frontend build tool with a built-in development server.

### NPM
- **Standard**: One of the standardized ways to create JavaScript based projects.
- **Manages Project**: Manages project dependencies and metadata in the `package.json` file.
- **Automates Project**: Automates project tasks using scripts defined in the `package.json` file.

### Vite
- **Modern Build Tool**: A fast, modern frontend build tool with a built-in development server.
- **Live-Reload**: Instant live-reload (e.g., changes in the code are instantly reflected in the browser).
- **Bundler**: Bundler optimized for production builds (e.g., smaller, fewer files)
- **Plugins**: Rich plugin ecosystem (e.g., React, Angular, Vue, TypeScript, etc.)

