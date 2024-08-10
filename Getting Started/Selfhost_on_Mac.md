# Hosting Artado Search on macOS

This guide provides detailed instructions for hosting the Artado Search application, built with ASP.NET Framework 4.8, on a macOS system using Mono.

## Prerequisites

Before you begin, ensure you have the following:

1. **macOS**: A macOS system (macOS 10.14 Mojave or later recommended).
2. **Mono**: Mono runtime and related tools installed.
3. **Nginx**: Web server for reverse proxy setup (optional but recommended).
4. **SQL Server**: An instance of SQL Server or a compatible database if your application requires one.
5. **Homebrew**: Package manager for macOS (optional but useful).

## Step-by-Step Hosting Instructions

### 1. Install Mono

1. **Install Homebrew** (if not already installed):
   - Open Terminal and run:
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

2. **Install Mono Using Homebrew**:
   - Install Mono by running:
     ```bash
     brew install mono
     ```

3. **Verify Installation**:
   - Check the Mono version to ensure it is installed correctly:
     ```bash
     mono --version
     ```

### 2. Prepare Your Application

1. **Build the Application**:
   - Open your Artado Search solution in Visual Studio.
   - Build the solution to create the deployable files.

2. **Publish the Application**:
   - Right-click on the project in Solution Explorer and select **Publish**.
   - Choose a **Folder** publish target and specify a location on your local machine or network share.
   - Click **Publish** to generate the files for deployment.

3. **Transfer Files**:
   - Transfer the published files to your macOS system. You can use file sharing methods like `scp`, `rsync`, or manually copy the files.

### 3. Set Up Mono to Run the Application

1. **Create a Directory for Your Application**:
   - Open Terminal and create a directory for Artado Search:
     ```bash
     mkdir -p ~/artado
     ```

2. **Move Your Application Files**:
   - Place your application files in the directory:
     ```bash
     mv /path/to/deployment/folder/* ~/artado
     ```

3. **Run the Application**:
   - Navigate to the directory and run your application using Mono:
     ```bash
     cd ~/artado
     mono ArtadoSearch.exe
     ```

   - To keep the application running in the background, consider using `nohup`:
     ```bash
     nohup mono ArtadoSearch.exe &
     ```

### 4. Configure a Web Server (Nginx)

To serve your application over HTTP/HTTPS, configure a web server like Nginx to act as a reverse proxy.

1. **Install Nginx Using Homebrew**:
   - Install Nginx by running:
     ```bash
     brew install nginx
     ```

2. **Configure Nginx**:
   - Create a new configuration file for your site:
     ```bash
     sudo nano /usr/local/etc/nginx/servers/artado.conf
     ```

   - Add the following configuration:
     ```nginx
     server {
         listen 80;
         server_name your_domain_or_ip;

         location / {
             proxy_pass http://localhost:8080;  # Change port to the port Mono is using
             proxy_set_header Host $host;
             proxy_set_header X-Real-IP $remote_addr;
             proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
             proxy_set_header X-Forwarded-Proto $scheme;
         }
     }
     ```

   - Start Nginx:
     ```bash
     sudo nginx
     ```

   - Reload Nginx configuration if necessary:
     ```bash
     sudo nginx -s reload
     ```

### 5. Configure Database (If Required)

1. **Install SQL Server or Connect to an Existing Database**:
   - Install SQL Server on a Windows server or use a compatible database.

2. **Update Connection Strings**:
   - Open the `Web.config` file in your published application.
   - Update the `<connectionStrings>` section to point to your SQL Server instance and database.

### 6. Test the Application

1. **Access the Application**:
   - Open a web browser and navigate to the domain or IP address configured in Nginx.
   - Verify that Artado Search is running correctly and all features are functioning as expected.

2. **Check Logs**:
   - If you encounter issues, check the Mono logs and Nginx logs for errors:
     - **Mono Logs**: Typically in the terminal where you started the application or in `~/Library/Logs/`.
     - **Nginx Logs**: Located in `/usr/local/var/log/nginx/`.

### 7. Configure Security and Maintenance

1. **Set Up HTTPS**:
   - Obtain an SSL certificate and configure Nginx for HTTPS. Use Certbot for free SSL certificates:
     ```bash
     brew install certbot
     sudo certbot --nginx
     ```

2. **Regular Backups**:
   - Implement regular backups for your application and database to prevent data loss.

3. **Monitor Performance**:
   - Use monitoring tools to keep an eye on the health of your application.

## Troubleshooting

- **Application Errors**: Check Mono and application logs for detailed error messages.
- **Permissions Issues**: Ensure the user running Mono has appropriate permissions for the application folder.
- **Database Connectivity**: Verify the connection string and ensure the database is accessible.

## Conclusion

By following these steps, you should have Artado Search running on your macOS system. If you encounter issues or need further assistance, consult the [Mono documentation](https://www.mono-project.com/docs/) or seek help from the Artado community.
