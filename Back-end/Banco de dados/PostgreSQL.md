# PostgreSQL

## 1. Install PostgreSQL

```bash
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install postgresql
```

## 2. Install Desktop Admin (GUI)

```bash
sudo apt install curl
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
sudo apt install pgadmin4-desktop
```

## 3. Confirm PostgreSQL Service Status

```bash
sudo systemctl is-active postgresql
sudo systemctl is-enabled postgresql
sudo systemctl status postgresql

# Is accepting connections?
sudo pg_isready

# Start service if needed
sudo systemctl start postgresql.service

# Enable the service to run at OS start
systemctl enable postgresql.service; service postgresql start
```

## 3. Create a Database

1. Switch to the postgres system user account

```bash
sudo su - postgres
```

_Alternatives_

- Switch over: `sudo -i -u postgres`
- No switch over: `sudo -u postgres psql`

2. Enter the database shell (postgres=#)

```bash
psql
```

3. Create the user

```sql
CREATE USER admin WITH PASSWORD 'admin';
```

4. Create the database

```sql
CREATE DATABASE mydatabase;
ALTER DATABASE mydatabase OWNER TO admin;
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO admin;
```

5. Exit shell

```sql
\q and exit
```

## 4. Configure Client Authentication

1. Edit the config file

```bash
sudo vim /etc/postgresql/12/main/pg_hba.conf
```

2. Check if lines match (default)

```plaintext
# IPv4 local connections:
host    all             all             127.0.0.1/32            md5
# IPv6 local connections:
host    all             all             ::1/128                md5
```

3. Exit Vim

```plaintext
Shift + : (enter command line)
q (to quit or exit Vim without saving) or x (save changes and exit)
```

4. Restart the service

```bash
sudo systemctl restart postgresql
```

## 5. pgAdmin GUI Client

### Add New Server

1.  General tab

    - Name: myServer
    - Server group: Servers
    - Connect now?: true

2.  Connection tab

    - Host name/address: localhost
    - Port: 5432 (default)
    - Maintenance database: postgres (default)
    - Username: admin
    - Password: admin

3.  Press the save button

    pgAdmin4 should successfully connect to the database server
