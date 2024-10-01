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
