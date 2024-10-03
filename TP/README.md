**Azure Data Storage Integration Pipeline**
===========================================

This project demonstrates a simple pipeline for logging user interactions using **Azure Functions** and **Azure Blob Storage**. Logs are sent via HTTP requests to an Azure Function, which then stores these logs in a Blob Storage container.

**Features**
------------

-   Logs HTTP requests and stores the logs as JSON files in Azure Blob Storage.
-   Supports both info and error logs.
-   Simulates log streams with random intervals.

**Tech Stack**
--------------

-   **Node.js** for simulating log generation and sending HTTP requests.
-   **Azure Functions** for receiving logs via HTTP and managing storage.
-   **Azure Blob Storage** for persistent storage of the log files.
