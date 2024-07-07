# Frontend - ReactJS with ChakraUI

This directory contains the frontend of the application built with ReactJS and ChakraUI.

## Setting up manually
### Prerequisites

- Node.js (version 14.x or higher)
- npm (version 6.x or higher)

### Setup Instructions

1. **Navigate to the frontend directory**:
    ```sh
    cd frontend
    ```

2. **Install dependencies**:
    ```sh
    npm install
    ```

3. **Run the development server**:
    ```sh
    npm run dev --host 
    ```

4. **Configure API URL**:
   Ensure the API URL is correctly set in the `.env` file.

   __**Note**__: Update the API URL to your AWS public IP if you're running in an EC2 instance

## Setting up with Docker

### For deploying the frontend using Docker:  
1. Build the app by running:
```bash
   sudo docker build  -t frontend:1.0 .
``` 
2. Run the container based on this image:
```bash
   sudo docker run -d -p 80:80 frontend:1.0
