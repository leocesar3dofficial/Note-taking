# Node.js

## Node Console

- **Enter**: `node`
- **Exit**: `.exit`

## Work on Cloned Project with Jest

- **Used for**: JavaScript testing framework for JavaScript TDD
- Install Jest on cloned project folder in terminal: `npm install`
- Check tests: `npm test [your JavaScript filename].spec.js`

## Command Line

### Create package.json inside project folder

```bash
npm init
```

### Install necessary modules

```bash
npm install
npm i <module name>
npm install express mongoose cors --save
```

List installed modules/dependencies: `npm list`

Details about a module: `npm list <package-name>`


### Simple install based on the project's package.js file

```bash
npm install --save
```

- Update modules: `npm update`
- Check for outdated packages: `npm outdated`
- Update package.json to latest versions of each module (dangerous!): `ncu -u`

### Run app

- **Normal**: `node <your app name>.js`
- **Dev mode**: 
  - **Info**: as described in the `package.json` file, like: `"dev": "env-cmd -f ./config/dev.env nodemon src/app.js"`
  - **Command**: `npm run dev`
- **Exit running app**: `Ctrl + C`

### Js file

- **Shebang**: First line in the file
  - Tells the OS which interpreter to use
  - Example
    - `#!/usr/bin/node` (absolute path of the interpreter)
    - `#!/usr/bin/env node` (relative OS environment Node location)

- **Give app executable permission**: `chmod u+x app.js` (must be in the same directory of the app file)

- **Restart the application automatically**
  - Install the nodemon module
    - `npm i -g nodemon` or `npm i --save nodemon` (to include the dependency on the `package.json`)
    - `npm i --save-dev nodemon` (development-dependency)
  - Run the application: `nodemon app.js`

- **Environment variables**
  - Used for databases and sensitive credentials
  - Set variables
    - `USER_ID=239482 USER_KEY=foobar node app.js`
  - Get variables
    ```javascript
    process.env.USER_ID; // "239482"
    process.env.USER_KEY; // "foobar"
    ```
  - Create `.env` file
    - Example
      - **Bash**
        ```bash
        # .env file
        USER_ID="239482"
        USER_KEY="foobar"
        NODE_ENV="development"
        ```
      - **Js file**
        ```javascript
        require('dotenv').config();
        process.env.USER_ID; // "239482"
        process.env.USER_KEY; // "foobar"
        process.env.NODE_ENV; // "development"
        ```
      - Don't import the package in your code
        ```bash
        node -r dotenv/config index.js
        ```

### Install nvm

- **Used for**: Node Version Manager, manages Node versions in the OS
- Install curl: `sudo apt install curl`
- Run the following commands:
  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
  ```

### Install Node

- `nvm install --lts`
- `nvm use --lts` (tell nvm to use the most recent version of Node, expected result: `Now using node vxx.xx.x (npm vx.xx.x)`)
- **npm**: stands for Node Package Manager
- Check installed version: `node -v` or `node --version`
- Check available versions: `nvm ls-remote`
- Install specific version: `nvm install <xx.xx.x>`

### Check-outdated module

- Install: `npm install check-outdated --save-dev`
- Run in the project folder: `npx check-outdated`

### Uninstall a library/module

```bash
npm uninstall library-name
```

## Libraries guide

### MailDev

1. Install globally: `npm install -g maildev`
2. Start: `maildev`
3. Access the Web Interface: http://localhost:1080
4. Configure Your Application:

   ```javascript
   const nodemailer = require('nodemailer');

   const transporter = nodemailer.createTransport({
     host: 'localhost',
     port: 1025,
     ignoreTLS: true // Disable TLS for MailDev
   });
   ```

5. Send Test Emails.
6. Stop MailDev: `Ctrl + C`
