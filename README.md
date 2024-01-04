# Custom Blockly Build

This repository contains a custom version of [Blockly](https://github.com/google/blockly), a library that adds a visual code editor to web and mobile apps. The following instructions guide you through setting up and linking the custom Blockly build in a Node.js project.

## Getting Started

### 1. Modify Blockly

After cloning and navigating to this fork of Blockly, make the desired changes to the TypeScript code.

### 2. Build Blockly

Compile the TypeScript files in the `core` folder into JavaScript files located in the `build` folder with:

```bash
npm install
npm run build
```

### 3. Linking the Modified Blockly to Your Node.js Project

#### Create a Local npm Link and Link Blockly to Your Node.js Project

First, create a local npm link to the modified Blockly build:
```bash
cd build/src
npm link
```
Then navigate to your Node.js project directory and run:

```bash
npm link blockly
```

### 4. Use the Compressed Version

Use the files in the `dist` folder to replace the files in your project. For example, copy `dist/blockly_compressed.js`, `dist/blocks_compressed.js`, and `dist/python_compressed.js` to your project's `lib` folder with:

```bash
project_path="path/to/your/project/lib"

cp dist/blockly_compressed.js $project_path
cp dist/blocks_compressed.js $project_path
cp dist/python_compressed.js $project_path
```

### 5. Using the Linked Blockly in Your Project

Now, you can use Blockly in your Node.js project:

```javascript
const Blockly = require('blockly');
// Use Blockly as you normally would
```

### 6. Keep This Fork Updated with the Original Blockly Repository

Keep your fork in sync with the original Blockly repository:

```bash
git remote add upstream https://github.com/google/blockly.git
git fetch upstream
git merge upstream/master
git push origin master
```
