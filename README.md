# Custom Blockly Build

This repository contains a custom version of [Blockly](https://github.com/google/blockly), a library that adds a visual code editor to web and mobile apps. The following instructions guide you through setting up and linking the custom Blockly build in a Node.js project.

## Getting Started

### 1. Modify Blockly

After cloning and navigating to this fork of Blockly, make the desired changes to the TypeScript code.

### 2. Build Blockly

Compile the TypeScript into JavaScript:

```bash
npm install
npm run build
```

### 3. Linking the Modified Blockly to Your Node.js Project

#### Create a Local npm Link

```bash
cd path/to/your/blockly/build/src
npm link
```

#### Link Blockly to Your Node.js Project

Navigate to your Node.js project directory and run:

```bash
npm link blockly
```

### 4. Using the Linked Blockly in Your Project

Now, you can use Blockly in your Node.js project:

```javascript
const Blockly = require('blockly');
// Use Blockly as you normally would
```

### 5. Keep Your Fork Updated

Keep your fork in sync with the original Blockly repository:

```bash
git remote add upstream https://github.com/google/blockly.git
git fetch upstream
git merge upstream/master
git push origin master
```
