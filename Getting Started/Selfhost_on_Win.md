# Hosting Artado Search on Windows

This guide provides detailed instructions for hosting the Artado Search application, which is built using ASP.NET Framework 4.8, on a Windows server. Follow these steps to set up and deploy your Artado Search application.

## Prerequisites

Before you begin, ensure you have the following:

1. **Windows Server**: A Windows Server 2016 or later instance.
2. **IIS**: Internet Information Services (IIS) installed and configured.
3. **ASP.NET Framework 4.8**: Installed on your server.
4. **SQL Server**: An instance of SQL Server if your application requires a database.
5. **Visual Studio**: (Optional) For development and deployment tasks.

## Step-by-Step Hosting Instructions

### 1. Install Required Components

1. **Install IIS**:
   - Open the **Server Manager**.
   - Go to **Manage** > **Add Roles and Features**.
   - Follow the wizard to install the **Web Server (IIS)** role. Ensure you include features like **ASP.NET 4.7/4.8** and **.NET Extensibility**.

2. **Verify ASP.NET Installation**:
   - Open a Command Prompt as Administrator.
   - Run `aspnet_regiis.exe -i` to ensure ASP.NET is registered with IIS.

### 2. Prepare Your Application

1. **Build the Application**:
   - Open your Artado Search solution in Visual Studio.
   - Build the solution to create the deployable files.

2. **Publish the Application**:
   - Right-click on the project in Solution Explorer and select **Publish**.
   - Choose a **Folder** publish target and specify a location on your local machine or network share.
   - Click **Publish** to generate the files for deployment.

### 3. Set Up IIS for Artado Search

1. **Create a New Website**:
   - Open **Internet Information Services (IIS) Manager**.
   - Right-click on **Sites** and select **Add Website**.
   - Enter the following information:
     - **Site Name**: ArtadoSearch
     - **Physical Path**: Path to the published files from the previous step.
     - **Binding**: Choose the IP address and port (e.g., `http://localhost:80`).
   - Click **OK** to create the website.

2. **Configure Application Pool**:
   - Go to **Application Pools** in IIS Manager.
   - Select the application pool used by your website (or create a new one if needed).
   - Set the .NET Framework version to **.NET Framework 4.8**.
   - Ensure the pipeline mode is set to **Integrated**.
   - Click **OK** to apply changes.

3. **Set Permissions**:
   - Navigate to the physical path of your website.
   - Right-click the folder and select **Properties**.
   - Go to the **Security** tab and add the user account that IIS uses (e.g., `IIS_IUSRS`).
   - Grant **Read & Execute** permissions.

### 4. Configure Database (If Required)

1. **Create a Database**:
   - Open **SQL Server Management Studio (SSMS)**.
   - Create a new database for Artado Search.
   - Set up any required tables and schemas.

2. **Update Connection Strings**:
   - Open the `Web.config` file in your published application.
   - Locate the `<connectionStrings>` section.
   - Update the connection string to point to your SQL Server instance and database.

### 5. Test the Application

1. **Browse the Website**:
   - Open a web browser and navigate to the URL you configured in IIS (e.g., `http://localhost`).
   - Verify that Artado Search is running correctly and all features are functioning as expected.

2. **Check Logs**:
   - If there are any issues, check the IIS logs and the application logs for errors.
   - Logs are typically found in `C:\inetpub\logs\LogFiles` for IIS and the `App_Data` folder for application-specific logs.

### 6. Configure Security and Maintenance

1. **Set Up HTTPS**:
   - Consider configuring HTTPS to secure the communication. Obtain an SSL certificate and bind it to your site in IIS.

2. **Regular Backups**:
   - Implement regular backups for your application and database to prevent data loss.

3. **Monitor Performance**:
   - Use IIS monitoring tools and performance counters to keep an eye on the health of your application.

## Troubleshooting

- **Application Errors**: Check the `Event Viewer` and IIS logs for detailed error messages.
- **Permissions Issues**: Ensure IIS user accounts have appropriate permissions for the application folder and database.
- **Database Connectivity**: Verify the connection string and ensure the SQL Server instance is accessible.

## Conclusion

By following these steps, you should have Artado Search up and running on your Windows server. If you encounter issues or need further assistance, consult the [official documentation](https://docs.microsoft.com/en-us/iis/) or seek help from the Artado community.
