# JavaScript Calculator Walkthrough

## 1. Setup Calculator Project

<img src="https://vitejs.dev/logo.svg" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="100"/>


We are going to create a simple Vite project and run it using NPM commands.

- **Create a directory `calculator-app`**:
```sh
mkdir calculator-app
cd calculator-app
```

- **Initialize a Vite project**:
  Creates a new Vite project in the current directory.
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
calculater-app/
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

Delete the content of the `main.js` file but keep the file.

## 2. Create Basic Calculator Functions

<img src="https://cdn.vox-cdn.com/thumbor/IehwTKigu5kUc9EIMdiHES_XNOU=/0x0:2752x2064/1400x1050/filters:focal(1921x1693:1922x1694)/cdn.vox-cdn.com/uploads/chorus_asset/file/25522223/IMG_CF7B8A1AD79A_1.jpeg" style="margin-left: 50px; margin-top: 20px; margin-bottom: 20px" width="200"/>

### Add Function


We are going to create the basic calculator functions that will be used to perform the calculations.


- **Add Function - Simple**:

Our first add function has two parameters `num1` and `num2` of type `number` and returns the sum of the two numbers.

```javascript
export function add(num1, num2) {
  return num1 + num2;
}
```

- **Add Function - Improved by Type Checking**:

We can improve the function by adding some validation to check if the parameters are numbers.

```javascript
export function add(num1, num2) {
  if (typeof num1 == 'number' && typeof num2 == 'number') {
    return num1 + num2;
  } else {
    console.error('Invalid parameters. Please provide numbers.');
  }
}
```

