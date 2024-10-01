Lab 1: Creating and Managing Azure Virtual Machines
---------------------------------------------------

### VM Creation and SSH Connection

1.  **Deploy a Linux Virtual Machine:**

    -   Go to the Azure portal and create a new Virtual Machine (VM).
    -   Choose Linux as the operating system (e.g., Ubuntu).
    -   Configure the VM size and storage according to your needs.
2.  **Networking Configuration:**

    -   Ensure SSH (port 22) is allowed in the network security group.
    -   Assign a public IP address to the VM for remote access.
3.  **Connect via SSH:**

    -   Once the VM is deployed, use the public IP to connect via SSH:

        bash

        Copier le code

        `ssh <username>@<public-ip>`

    -   Enter your credentials to access the VM.
