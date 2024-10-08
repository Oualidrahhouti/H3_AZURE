Lab 1: Creating and Managing Azure Virtual Machines
---------------------------------------------------

### VM Creation and SSH Connection with Private Key

1.  **Deploy a Linux Virtual Machine:**

    -   Go to the Azure portal and create a new Virtual Machine (VM).
    -   Choose Linux as the operating system (e.g., Ubuntu).
    -   Configure the VM size and storage based on your needs.
    -   In the "Administrator Account" section, select SSH public key for authentication and upload your public key (or generate a new one).
2.  **Networking Configuration:**

    -   Ensure SSH (port 22) is allowed in the network security group.
    -   Assign a public IP address to the VM for remote access.
3.  **Connect via SSH Using a Private Key:**

    -   After deploying the VM, use the following command to connect via SSH:

        bash

        Copier le code

        `ssh -i <path-to-private-key> <username>@<public-ip>`

    -   Replace `<path-to-private-key>` with the path to your private key file, `<username>` with the username you configured, and `<public-ip>` with the VM's public IP address.

    -   Enter the private key passphrase if prompted, to establish the connection.


Lab 2: Implementing Azure Virtual Networks
------------------------------------------

### Key Steps:

1.  **Address Space:**

    -   Create a Virtual Network (VNet) with the address space `10.0.0.0/16`.
2.  **Subnets:**

    -   Inside the VNet, create two subnets:
        -   Subnet 1: `10.0.1.0/24`
   
3.  **Virtual Network 2:**

    -   Create a second VNet with different address spaces, such as `10.1.0.0/16`.
4.  **VNet Peering:**

    -   Set up VNet peering between the two VNets (`10.0.0.0/16` and `10.1.0.0/16`) to enable communication between them.


Lab 3: Deploying Azure App Service Web Apps
-------------------------------------------

### Key Steps:

1.  **Create an Azure App Service Plan:**

    -   In the **Azure portal**, create an **App Service Plan**.
    -   Choose the **Free** or **Basic** tier for the plan.
    -   Select your region and resource group.
2.  **Deploy a Web Application:**

    -   Create a new **Web App** under the App Service Plan you just created.
    -   Choose your preferred runtime stack (e.g., Node.js, .NET, Python).
    -   Once deployed, access the web app using the provided default Azure URL.
3.  **SSL Certificate and Custom Domain:**

    -   Due to limitations of the chosen App Service Plan, implementing an SSL certificate and custom domain setup is not possible.
    -   Upgrading to a higher-tier plan (e.g., Standard or Premium) would be required to enable these features.

Lab 4: Managing Azure Storage Accounts and Blobs
------------------------------------------------

### Key Steps:

1.  **Create a Storage Account:**

    -   In the **Azure portal**, create a new **Storage Account**.
    -   Choose the resource group, region, and select a replication option (e.g., **Locally Redundant Storage (LRS)**).
    -   Review and create the storage account.
2.  **Upload a Blob:**

    -   Navigate to the storage account and go to the **Containers** section.
    -   Create a new container and upload your first blob (file) into the container using the **Azure Portal**.
3.  **Generate a Shared Access Signature (SAS) Token:**

    -   In the storage account, go to the **Shared Access Signature** section.
    -   Configure the permissions (e.g., read, write) and set an expiration date for the token.
    -   Generate the SAS token and use it to provide secure access to your blob without exposing your account key.
4.  **Add a Delete Rule via Lifecycle Management Policies:**

    -   Go to the **Lifecycle Management** section of the storage account.
    -   Add a rule to automatically delete blobs older than a specified number of days (e.g., 30 days).
    -   Save the rule, and Azure will enforce this policy to manage blob retention automatically.

Lab 5: Implementing Azure SQL Databases
---------------------------------------

### Key Steps:

1.  **Deploy an Azure SQL Database:**

    -   In the **Azure portal**, create a new **Azure SQL Database**.
    -   Choose your resource group, set a database name, and select a **SQL Server** (create a new one if necessary).
    -   Configure the pricing tier and performance level according to your needs.
    -   Review and create the database.
2.  **Configure Firewall Settings:**

    -   After the database is created, navigate to **Firewall and Virtual Networks** under the database settings.
    -   Add your client IP address to allow access to the SQL database.
    -   Save the firewall rules to enable external connections.
3.  **Import Data into the Database:**

    -   Use **SQL Server Management Studio (SSMS)** or **Azure Data Studio** to connect to the database using the server name, username, and password.
    -   Once connected, import a dataset or run SQL scripts to populate the database with data.
4.  **Implement Geo-Replication for High Availability:**

    -   In the **Azure portal**, navigate to your SQL database and select **Geo-replication** under the **Settings** section.
    -   Choose a secondary region for replication and configure the settings to enable high availability.
    -   Monitor the replication status, ensuring the database is continuously synced across regions for disaster recovery.

Lab 7: Implementing Azure Functions
-----------------------------------

### Key Steps:

1.  **Create an Azure Function App:**

    -   In the **Azure portal**, navigate to **Function App** and click **+ Create**.
    -   Choose your resource group, provide a name for the function app, select the runtime stack (e.g., .NET, Python, or Node.js), and choose your hosting options (e.g., consumption plan).
    -   Review and create the function app.
2.  **Develop a Serverless Function Triggered by an HTTP Request:**

    -   Once the Function App is created, go to the **Functions** section and click **+ Add** to create a new function.
    -   Select **HTTP Trigger** as the function template.
    -   Write the function code that will respond to HTTP requests. For example, a simple function that returns "Hello, World!".
    -   Test the function by accessing the HTTP endpoint provided in the **Azure portal**.
3.  **Integrate the Function with Azure Storage or Azure Queue:**

    -   In the **Function App**, navigate to the **Integrate** tab.
    -   Configure input or output bindings for **Azure Storage** (e.g., Blob Storage) or **Azure Queue** to interact with other services.
    -   For example, you can configure the function to process messages from a storage queue or upload data to blob storage.
4.  **Monitor Function Performance and Logs:**

    -   In the **Azure portal**, go to **Monitor** for the function app.
    -   View real-time metrics such as execution count, errors, and latency.
    -   Access detailed logs to troubleshoot issues or verify the function's behavior.

Lab 8: Using Azure Cognitive Services
-------------------------------------

### Key Steps:

1.  **Create an Azure Cognitive Services Resource:**

    -   In the **Azure portal**, navigate to **Cognitive Services** and click **+ Create**.
    -   Choose the appropriate subscription and resource group.
    -   Select the **Cognitive Service** type you need (e.g., Text Analytics, Computer Vision, or Speech).
    -   Provide a name for the resource and select the region where it will be deployed.
    -   Choose the **Pricing Tier** based on your requirements and review the other settings.
    -   Click **Review + Create** to finalize the creation of the service.
2.  **Retrieve API Keys and Endpoints:**

    -   Once the Cognitive Services resource is created, go to the **Keys and Endpoint** section.
    -   Copy the **API keys** and **endpoint URL** that will be used for authentication in your applications.

Lab 9: Implementing Azure Load Balancer and Traffic Manager
-----------------------------------------------------------

### Key Steps:

1.  **Deploy an Azure Load Balancer:**

    -   In the **Azure portal**, navigate to **Load Balancers** and click **+ Create**.
    -   Choose a **Public** or **Internal** load balancer, depending on your needs.
    -   Assign the load balancer to a resource group, select the region, and configure the front-end IP address.
2.  **Configure Load Balancing Rules:**

    -   Go to the **Load Balancing Rules** section within the load balancer.
    -   Add a new rule:
        -   Select the front-end IP configuration (public or internal).
        -   Define the back-end pool, which contains the VMs or resources that will receive traffic.
        -   Set the protocol (TCP or UDP), define the port (e.g., port 80 for HTTP), and specify the distribution rule (e.g., round-robin).
    -   This rule ensures that incoming traffic is evenly distributed across the back-end VMs.
3.  **Set Up Health Probes:**

    -   In the **Health Probes** section, add a new health probe:
        -   Choose **TCP** or **HTTP** as the protocol.
        -   Set the port number for the health check (e.g., 80 for HTTP).
        -   Configure the interval and the number of failures before marking a VM as unhealthy.
    -   Health probes are used to monitor the availability of VMs and route traffic only to healthy instances.
4.  **Deploy Azure Traffic Manager:**

    -   In the **Azure portal**, navigate to **Traffic Manager Profiles** and click **+ Create**.
    -   Choose a name for the profile, select the routing method (e.g., performance, priority, or geographic), and assign it to a resource group.
    -   Once created, add **Endpoints** (e.g., the load balancers or web apps) that the Traffic Manager will direct traffic to based on the configured rules.
5.  **Test Failover and Traffic Routing:**

    -   To test the configuration, simulate a failure in one of the back-end VMs or regions.
    -   Ensure that traffic is rerouted to the healthy back-end resources as configured by the load balancer and Traffic Manager.

Lab 10: Configuring Azure Backup and Recovery Services
------------------------------------------------------

### Key Steps:

1.  **Create a Recovery Services Vault:**

    -   In the **Azure portal**, navigate to **Recovery Services Vaults** and click **+ Create**.
    -   Choose your resource group, provide a name for the vault, and select a region.
    -   Review and create the Recovery Services Vault.
2.  **Configure Backup for Resources:**

    -   Note: It is required to have resources (such as VMs or file shares) available to configure backups.
    -   In the **Recovery Services Vault**, navigate to **Backup**.
    -   Select the resource type you want to back up (e.g., **Azure Virtual Machines** or **Azure Files**).
    -   Choose the resources from the list and configure the backup policy (set the backup frequency and retention period).
3.  **Perform a Backup Operation:**

    -   Once the backup policy is configured, initiate a backup by going to the **Backup Items** section.
    -   Select the resource you want to back up, then click **Backup Now** to manually trigger a backup.
    -   The status of the backup operation can be monitored in the **Backup Jobs** section.
4.  **Configure Backup Policies and Retention:**

    -   Under the **Backup Policies** section in the Recovery Services Vault, create or modify a backup policy.
    -   Set the frequency of backups (e.g., daily or weekly) and configure the retention policy to define how long backups should be kept.
    -   Apply the policy to your backup resources to automate the process.
5.  **Perform a Restore Operation:**

    -   To restore a resource, go to the **Backup Items** section and select the resource you want to restore.
    -   Choose a recovery point from the available backups and initiate the restore process.


Lab 14: Configuring Azure DNS and Custom Domains
------------------------------------------------

### Key Steps:

1.  **Create an Azure DNS Zone:**

    -   In the **Azure portal**, navigate to **DNS Zones** and click **+ Create**.
    -   Select your subscription and resource group, then provide a unique **domain name** for the DNS zone (e.g., `mydomain.com`).
    -   Click **Review + Create** to deploy the DNS zone.
2.  **Manage DNS Records for Custom Domain:**

    -   After the DNS zone is created, go to the **DNS Zone** page and click **+ Record set** to add DNS records.
    -   Set up different DNS record types:
        -   **A Record**: Maps the domain name to an IP address.
        -   **CNAME Record**: Maps a domain to another domain (useful for subdomains like `www`).
        -   **TXT Record**: Used for domain verification or security purposes.
3.  **Configure Domain Verification and Mapping for Azure Services:**

    -   If using custom domains with Azure services (e.g., App Service), navigate to the service settings and add your custom domain.
    -   Follow the provided instructions to verify the domain ownership by adding specific DNS records (e.g., a **TXT** record).
    -   Once verified, you can map the custom domain to your Azure service.
4.  **Implement DNS Aliases (CNAME) and Record Sets:**

    -   Set up **CNAME** records to point subdomains (like `www.mydomain.com`) to the primary domain or another service.
    -   Use record sets to group multiple DNS records under the same domain, making it easier to manage DNS entries.
