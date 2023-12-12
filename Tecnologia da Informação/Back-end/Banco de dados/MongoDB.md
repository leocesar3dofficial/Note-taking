# MongoDB

## Shell

- **Enter:**
  ```
  mongosh
  ```
- **Exit:**
  ```
  exit
  ```

### Connect

- **Atlas cloud DB:**

  ```
  mongo "mongodb+srv://cluster0.yaeyt.mongodb.net/myFirstDatabase" --username student
  ```

- **Local in app using Mongoose:**

  ```javascript
  import mongoose from "mongoose";
  export const connectDb = async () => {
    try {
      await mongoose.connect("mongodb://localhost:27017/<DB name>", {
        useNewUrlParser: true,
        useUnifiedTopology: true,
        useCreateIndex: true,
      });
    } catch (error) {
      console.log(error.message);
    }
  };
  ```

- **Normal connect:**

  ```
  mongodb://admin:password@External-IP:27017/database
  ```

- **Local:**

  ```
  mongo
  ```

- **Switch to db admin in shell:**

  ```
  use admin
  ```

- **Create a root user in shell:**

  ```javascript
  db.createUser({
    user: "admin",
    pwd: "password",
    roles: [{ role: "root", db: "admin" }],
  });
  ```

- **Exit the shell and connect to the DB:**

  ```
  mongo -u admin -p password --authenticationDatabase admin
  ```

- **List all available databases in shell:**

  ```
  show dbs
  ```

- **List collections:**
  ```
  show collections
  ```

### Create DB

- **Use DB:**

  ```
  use <DB name>
  ```

- **It only lists the DB after the first inserted document with:**

  ```
  db.user.insert({name: "Ada Lovelace", age: 205})
  ```

- **Delete DB:**

  ```
  db.dropDatabase()
  ```

- **Create collection:**
  ```
  db.createCollection( <DB name>, <optional options> )
  ```

## Install

1. **Install Required Packages:**

   ```
   sudo apt-get install gnupg curl
   ```

2. **Import the MongoDB public GPG key:**

   ```bash
   curl -fsSL https://pgp.mongodb.com/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
   ```

3. **Create a list file:**

   ```bash
   echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
   ```

4. **Reload local package database:**

   ```
   sudo apt-get update
   ```

5. **Install the MongoDB packages (latest version):**

   ```
   sudo apt-get install -y mongodb-org
   ```

6. **Start service:**

   ```
   sudo systemctl start mongod
   ```

7. **See installed version:**

   ```
   mongod --version
   ```

8. **Restart service:**

   ```
   sudo systemctl restart mongodb
   sudo systemctl restart mongod
   ```

9. **Stop service:**

   ```
   sudo systemctl stop mongodb
   ```

10. **Check if service is running:**

    ```
    sudo systemctl status mongod
    ```

    If the service is loaded but not running (Error: `connect ECONNREFUSED 127.0.0.1:27017`), delete this file:

    ```
    sudo rm -rf /tmp/mongodb-27017.sock
    ```

    Restart the service.

11. **Enable service at OS boot:**

    ```
    sudo systemctl enable mongod
    ```

12. **Disable service at OS boot:**
    ```
    sudo systemctl disable mongodb
    ```

## Configure

### Secure

- **Edit MongoDB config file:**

  ```
  sudo nano /etc/mongod.conf
  ```

  Add:

  ```
  security:
    authorization: enabled
  ```

- **Enable Remote Connections on config file:**
  ```
  net:
    port: 27017
    bindIp: 127.0.0.1,<your IP>
  ```

## Compass tool

- GUI tool to explore and manipulate your database

### Installation

- **Download:**

  ```
  wget https://downloads.mongodb.com/compass/mongodb-compass_1.40.4_amd64.deb
  ```

- **Install:**

  ```
  sudo dpkg -i mongodb-compass_1.40.4_amd64.deb
  ```

- **Run:**
  ```
  mongodb-compass
  ```

### Uninstall

1. **Stop MongoDB Service:**

   ```
   sudo service mongod stop
   ```

2. **Remove MongoDB Packages:**

   ```
   sudo apt-get purge mongodb-org*
   ```

3. **Remove Configuration and Log Files:**

   ```
   sudo rm -r /var/log/mongodb
   sudo rm -r /var/lib/mongodb
   ```

4. **Remove MongoDB User and Group:**

   ```
   sudo userdel mongodb
   sudo groupdel mongodb
   ```

5. **Remove MongoDB Binaries:**

   ```
   sudo rm -r /usr/bin/mongod
   sudo rm -r /usr/bin/mongo
   ```

6. **Remove MongoDB Data Directory (if not removed by the purge command):**

   ```
   sudo rm -r /data/db
   ```

7. **Remove MongoDB Configuration File:**

   ```
   sudo rm /etc/mongod.conf
   ```

8. **Remove MongoDB Repository (if added manually):**
   ```
   sudo rm /etc/apt/sources.list.d/mongodb-org-*
   ```
