<h1 align="center">
    Microservices Assembly with Docker Compose
</h1>

<center>
    Jose Daniel Sarmiento , Manuel Ayala  | { jose2192232, jose2195529 } @correo.uis.edu.co
</center>


## Resume

This repository contains two microservices orchestrated using Docker Compose:
- User & Client Service: Manages user authentication, client profiles, and related data.
- Routine Maintenance Service: Handles business logic related to routine maintenance tasks.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Architecture Overview](#architecture-overview)
- [Getting Started](#getting-started)
    - [Clone the Repository](#getting-started)
- [Environment Variables](#environment-variables)
- [Docker Compose Up](#docker-compose-up)
- [Services Overview](#services-overview)
- [Common Commands](#common-commands)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)


## Prerequisites

Before you begin, ensure you have met the following requirements:
Docker & Docker Compose installed on your machine.
(Optional) make installed for easier commands execution.

## Architecture Overview

The system consists of two microservices:
User & Client Service: Responsible for managing user authentication, authorization, and client data.
Routine Maintenance Service: Handles all the business logic and rules for managing maintenance routines.
Both services communicate through HTTP and share common environment variables defined in the .env file.

## Getting Started

### Clone the Repository

```
    git clone https://github.com/DanielSarmiento04/microservice_management
    cd microservice_management
```

## Environment Variables

Copy the .env.example file to .env and modify the values as needed:

```
    cp .env.example .env
```

Update the following variables in .env:
USER_DB_URI: Connection string for the User & Client database.
ROUTINE_DB_URI: Connection string for the Routine Maintenance database.
JWT_SECRET: Secret key for JWT tokens.

## Docker Compose Up

Build and start the services:
```
    docker-compose up --build
```

``The services will be available at``:

- User & Client Service: http://localhost:8000
- Routine Maintenance Service: http://localhost:8001

## Services Overview

### User & Client Service

> Description: Handles all user and client-related operations.
> Technologies: FastAPI, MongoDB.


- User & Client Service: http://localhost:8000/docs
- Routine Maintenance Service: http://localhost:8001/docs

## Common Commands

- Build & Start Services:

```
    docker-compose up --build
```

- Stop Services:

```
    docker-compose down
```

- Rebuild Specific Service:

```
    docker-compose up --build service_name
```

- View Logs:

```
    docker-compose logs -f
```

## Troubleshooting

### Database Connection Issues:
Verify that the database URIs in the .env file are correct.
Ensure that the database containers are running.

### Service Not Responding:
Check the logs using docker-compose logs -f.
Ensure that the ports are not being used by another process.

## Contributing

If you have suggestions or find a bug, feel free to create an issue or submit a pull request. Please ensure your contributions align with the project's coding guidelines.
