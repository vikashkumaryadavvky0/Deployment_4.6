# Module 4.6: Nginx Reverse Proxy Setup

## Overview
This directory contains the Nginx reverse proxy configuration for the HireGen AI infrastructure (Team 4). The proxy is containerized using Docker and is configured to route HTTP requests to the appropriate backend microservices, currently serving the system's health-check endpoint.

## Prerequisites
Ensure the following are installed on your local machine before proceeding:
* Docker
* Docker Compose

## Core Files
* `nginx.conf`: The main Nginx configuration file defining worker processes and global HTTP settings.
* `default.conf`: The server block configurations dictating how incoming traffic is routed to internal Docker network services.
* `Dockerfile`: The instructions for building the custom Nginx image.

## Running the Proxy
To build and start the Nginx proxy alongside the backend services, execute the following command from the project root:

```bash
docker-compose up -d --build