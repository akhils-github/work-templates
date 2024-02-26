Certainly! Here's the script in Markdown format:

```javascript
const fs = require('fs');
const path = require('path');

const baseDir = './project';

const folders = [
  'config',
  'src',
  'public',
  'src/api',
  'src/api/controllers',
  'src/api/middlewares',
  'src/api/models',
  'src/api/routes',
  'src/api/services',
  'src/api/utils',
  'src/api/validations'
];

function createFolders() {
  folders.forEach(folder => {
    const folderPath = path.join(baseDir, folder);
    if (!fs.existsSync(folderPath)) {
      fs.mkdirSync(folderPath, { recursive: true });
      console.log(`Created folder: ${folderPath}`);
    } else {
      console.log(`Folder already exists: ${folderPath}`);
    }
  });
}

function createAppJs() {
  const appJsPath = path.join(baseDir, 'src/api/app.js');
  const content = `const express = require('express');
const cors = require('cors');
const port = 3000;

const app = express();
app.use(cors());

app.listen(port, async () => {
    try {
        console.log(\`Listening on port \${port}\`);
    } catch (error) {
        console.log(error);
    }
});`;

  fs.writeFileSync(appJsPath, content);
  console.log(`Created file: ${appJsPath}`);
}

function main() {
  createFolders();
  createAppJs();
}

main();
```