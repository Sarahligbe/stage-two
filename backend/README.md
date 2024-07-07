# Backend - FastAPI with PostgreSQL

This directory contains the backend of the application built with FastAPI and a PostgreSQL database.

## Setting up manually
## Prerequisites

- Python 3.8 or higher
- Poetry (for dependency management)
- PostgreSQL (ensure the database server is running)

### Installing Poetry

To install Poetry, follow these steps:

```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Add Poetry to your PATH (if not automatically added):

### Setup Instructions

1. **Navigate to the backend directory**:
    ```sh
    cd backend
    ```

2. **Install dependencies using Poetry**:
    ```sh
    poetry install
    ```

3. **Set up the database with the necessary tables**:
    ```sh
    poetry run bash ./prestart.sh
    ```

4. **Run the backend server**:
    ```sh
    poetry run uvicorn app.main:app --reload
    ```
    If you’re running on an AWS instance run this command below instead:
    ```sh
       poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
    ```

5. **Update configuration**:
   Ensure you update the necessary configurations in the `.env` file, particularly the database configuration.  

    __**Note**__: Update the BACKEND_CORS to include your AWS public IP if you're running in an EC2 instance

## Setting up with Docker
### Prerequisites 
- PostgreSQL (ensure the database server is running)

### For deploying the backend using Docker:  
1. Build the app by running:
```bash
   sudo docker build  -t backend:1.0 .
``` 
2. Run the container based on this image (ensure that the postgres db is running locally or in a container before runing this command):
```bash
   sudo docker run -d -p 8000:8000 backend:1.0
```