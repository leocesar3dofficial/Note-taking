# Deploy a Node.js application to the intranet

## 1. Prepare the Application

- Verify that all dependencies are listed in `package.json`.
- Make sure the application is tested and stable.

## 2. Set Up the Server

1. **Install Node.js**:
   ```sh
   sudo apt update
   sudo apt install nodejs npm
   ```

2. **Clone the Application**:
   ```sh
   git clone https://the-repo-url.git
   cd the-repo-directory
   ```

3. **Install Dependencies**:
   ```sh
   npm install
   ```

## 3. Configure the Application

Ensure the application is configured to run on a specific port and that this port is accessible within the intranet.

## 4. Start the Application

Use a process manager like `PM2` to keep it running and handle restarts.

### With PM2

1. **Install PM2**:
   ```sh
   npm install -g pm2
   ```

2. **Start the Application**:
   ```sh
   pm2 start app.js
   ```

3. **Save the PM2 Process List** (to restart on system reboot):
   ```sh
   pm2 save
   ```

4. **Set PM2 to Start on Boot**:
   ```sh
   pm2 startup
   ```

### 5. Configure Network Settings

Ensure that the server’s firewall and network settings allow traffic on the port the Node.js application is using.

```sh
sudo ufw allow 3000
```

## 6. Accessing the Application

Within the intranet, you can access the Node.js application using the server's IP address and the specified port, like `http://server-ip:port`.

### Optional: Use a Reverse Proxy

Using a reverse proxy like Nginx or Apache can provide benefits like load balancing, SSL termination, and better performance.

#### With Nginx

1. **Install Nginx**:
   ```sh
   sudo apt update
   sudo apt install nginx
   ```

2. **Configure Nginx**:
   Edit the Nginx configuration file, typically found at `/etc/nginx/sites-available/default` or create a new site configuration file in the `/etc/nginx/sites-available/` directory. Here is an example configuration:

   ```nginx
	server {
		listen 80;
		server_name your-domain.com;

		location / {
			proxy_pass http://localhost:3000;  # Node.js app running on port 3000
			proxy_http_version 1.1;
			proxy_set_header Upgrade $http_upgrade;
			proxy_set_header Connection 'upgrade';
			proxy_set_header Host $host;
			proxy_cache_bypass $http_upgrade;

			# Enable caching
			proxy_cache my_cache;
			proxy_cache_valid 200 302 10m;  # Cache 200 and 302 responses for 10 minutes
			proxy_cache_valid 404 1m;       # Cache 404 responses for 1 minute
			add_header X-Cache-Status $upstream_cache_status;
		}
	}

	# Define cache settings
	proxy_cache_path /var/cache/nginx levels=1:2 keys_zone=my_cache:10m inactive=60m use_temp_path=off;

   ```

   - Create a symbolic link to enable the site if you created a new configuration file:
     ```sh
     sudo ln -s /etc/nginx/sites-available/your-config-file /etc/nginx/sites-enabled/
     ```
   - Test the Nginx configuration:
     ```sh
     sudo nginx -t
     ```
   - Restart Nginx to apply the changes:
     ```sh
     sudo systemctl restart nginx
     ```

3. **Access Your Application**

Open a browser and navigate to the domain or IP address you configured in the Nginx server block. For example, `http://your-domain.com` or `http://server-ip`.