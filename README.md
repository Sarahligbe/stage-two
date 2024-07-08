# Full-Stack FastAPI and React Template

Welcome to the Full-Stack FastAPI and React template repository. This repository serves as a demo application for interns, showcasing how to set up and run a full-stack application with a FastAPI backend and a ReactJS frontend using ChakraUI.

## Project Structure

The repository is organized into two main directories:

- **frontend**: Contains the ReactJS application.
- **backend**: Contains the FastAPI application and PostgreSQL database integration.

Each directory has its own README file with detailed instructions specific to that part of the application.

## Getting Started

To get started with this template, please follow the instructions in the respective directories:

- [Frontend README](./frontend/README.md)
- [Backend README](./backend/README.md). 

## Running the project
### Pre-requisites
- A domain name with `db` and `proxy` subdomains setup

### Running the project in prod - with ssl
1. Edit the .env file to include your domain name, email for letsencrypt, and database credentials
2. Run
```bash
   docker compose up -d
```

 __**Note**__:   
 
 - Update the API URL to your domain name in the `frontend/.env.prod` file
 - Update the BACKEND_CORS to include your domain name in the `backend/.env.prod` file  

 ### Running the project in a dev environment - without ssl
 - Update the API_URL to include your domain url and your domain name in the `./frontend/.env` file  
 - Update your domain name and include your domain url in the BACKEND_CORS environment variable in the `./backend/.env` file  
 - Run
 ```bash
    docker compose -f docker-compose-dev.yaml up -d
```
