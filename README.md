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
