# Express

1. **Install Express:**
   ```
   npm i express
   ```
   or
   ```
   npm install express
   ```

2. **Change the owner of `~/.npm` folder to yourself:**
   ```
   mkdir ~/.npm-global
   npm config set prefix '~/.npm-global'
   ```

3. **Edit your `~/.profile`:**
   ```
   export PATH=~/.npm-global/bin:$PATH
   ```
   Then invoke it with:
   ```
   source ~/.profile
   ```

4. **Install the Express Application Generator tool globally:**
   ```
   npm install express-generator -g
   ```

5. **Create an Express app:**
   - Using npx (npm not global):
     ```
     npx express-generator <app name>
     ```
   - Or with a specific view template (npm installed earlier with pug view template):
     ```
     express <app name> --view=pug
     ```
   - Template options:
     ```
     express --help
     ```

6. **Install all the dependencies in the app folder:**
   ```
   npm install
   ```

7. **Run the app:**
   - Debug mode (enables console logging/debugging):
     ```
     DEBUG=<app name>:* npm start
     ```
   - Or using a script defined in `package.json`:
     ```
     npm run <scriptname>
     ```
   - Or with nodemon:
     ```
     DEBUG=express-locallibrary-tutorial:* npm run devstart
     ```

8. **Exit running app:**
   ```
   Ctrl + C
   ```

9. **View app in browser at:**
   ```
   http://127.0.0.1:3000/ (127.0.0.1 equals localhost)
   ```

10. **Enable server restart on file changes with nodemon:**
    - In the app folder:
      ```
      npm install --save-dev nodemon
      ```
    - Or globally:
      ```
      npm install -g nodemon
      ```
      Force restart:
      ```
      rs
      ```

# Mongoose

- **Install Mongoose:**
  ```
  npm install mongoose
  ```

- **Install async module:**
  ```
  npm install async
  ```

  (Asynchronous flow, needed by the `populatedb.js` and for the app itself)

- **Populate DB with dummy documents:**
  ```
  node populatedb <mongodb url>
  ```
  Example local URL:
  ```
  node populatedb mongodb://localhost:27017/
  ```

# Other Important Libraries

- **Cors:**
  ```
  npm i cors -S
  ```

- **HTTPS:**
  ```
  npm i https -S
  ```

  - Generate a local digital certificate: [Certificate Generator](https://pt.rakko.tools/tools/46/)
  - Configure HTTPS in a local environment that doesn't require a CA-signed certificate.

- **File System:**
  ```
  npm i fs -S
  ```