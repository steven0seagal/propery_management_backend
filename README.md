# Property Management System App

Welcome to the Property Management System (PMS) app repository! This README provides an overview of the project, its setup, and usage instructions.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Local Development](#local-development)
  - [Production Deployment](#production-deployment)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
  - [How to Contribute](#how-to-contribute) 
- [License](#license)

## Introduction

The Property Management System (PMS) app is a web-based application designed to streamline property management tasks. It includes features for property listing, tenant management, rent tracking, and more. This repository contains the Docker Compose setup for running the PMS app locally and in a production environment.

## Features

- Property listing and management
- Tenant information and lease tracking
- Rent payment tracking
- User authentication and authorization
- Dockerized setup for easy deployment

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Docker and Docker Compose installed on your system.

## Getting Started

### Local Development

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/property-management-system.git

    cd property-management-system
    ```
2. Create an .env.local file in the project root and configure your local environment variables. You can use the provided .env.local template as a starting point.

3. Build and start the development containers:

    ```bash
    docker-compose up -d --build
    ```
4. Run the database migrations:

    ```bash
    docker-compose exec web python manage.py migrate --noinput
    ```
5. Create a superuser account:

    ```bash
    docker-compose exec web python manage.py createsuperuser
    ```
6. Visit http://localhost:8000 to view the app.

### Production Deployment

1. Clone this repository to your server:

   ```bash
   git clone https://github.com/steven0seagal/propery_management_backend.git
    
   cd propery_management_backend
   ```
   
2. Create an .env.prod file in the project root and configure your production environment variables. You can use the provided .env.prod template as a starting point.

3. Build and start the production containers:

    ```bash
    docker-compose -f docker-compose.yml -f docker-compose.prod.yml up --build -d

    ```
4. Run the database migrations:

    ```bash
    docker-compose -f docker-compose.yml -f docker-compose.prod.yml exec web python manage.py migrate --noinput
    ```
5. Create a superuser account:

    ```bash
    docker-compose -f docker-compose.yml -f docker-compose.prod.yml exec web python manage.py createsuperuser
    ```
5. Configure your web server (e.g., Nginx) to reverse proxy requests to the Django app as defined in the Nginx configuration.

## Project Structure

- django/: Contains the Django application code and Dockerfile.
- nginx/: Contains Nginx configuration files.

## Contributing

Thank you for considering contributing to the Property Management System (PMS) app! Contributions from the community help improve the project and make it more valuable for everyone. Please take a moment to read these guidelines before getting started.

### How to Contribute

1. Fork the repository to your GitHub account.

2. Clone your fork to your local machine:

   ```bash
    git clone https://github.com/steven0seagal/property-management-system.git
    ```
3. Create a new branch for your contribution:

   ```bash
    git checkout -b your-branch-name
    ```
4. Commit your changes to the new branch:
 
   ```bash
    git commit -m "Add some feature"
    ```
5. Push your changes to your fork:
 
   ```bash
    git push origin your-branch-name
    ```
6. Submit a pull request to the main repository.



## License

This project is licensed under the terms of the [MIT License](LICENSE).
