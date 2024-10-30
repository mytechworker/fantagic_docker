# How to Start the Project 

## Prerequisites

Make sure you have the following installed:
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Project Structure
The project is organized as follows:

```
├── salesPhase1-admin/
│   ├── Dockerfile
│   ├── README.md
│   ├── .env (if needed)
│   └── src/ (Admin project files)
├── salesPhase1-backend/
│   ├── Dockerfile
│   ├── README.md
│   ├── .env (if needed)
│   └── src/ (Backend project files)
├── salesPhase1-webapp/
│   ├── Dockerfile
│   ├── README.md
│   ├── .env (if needed)
│   └── src/ (Webapp project files)
├── docker-compose.yml
├── nginx.conf
```

# Project Setup Guide

## Step 1: Clone Repositories
First, clone all three repositories and place them in the root directory alongside the docker-compose.yml and nginx.conf files.

## Step 2: Insert Environment Variables
Add the necessary environment variables for each repository in their respective .env files.

salesPhase1-admin .env

```bash
VITE_API_URL="http://localhost:8080"
```

salesPhase1-backend .env

```bash
PORT=
MONGODB_URI=
JWT_SECRET_ACCESSTOKEN=
JWT_SECRET_REFRESHTOKEN=
EMAIL_USER=
EMAIL_PASS=
CRYPTO_SECRET_KEY=
JWT_ACCESSTOKEN_EXPIRE=""
JWT_REFRESHTOKEN_EXPIRE=""
STRIPE_SECRET_KEY=""
STRIPE_WEBHOOK_KEY=""
```
salesPhase1-webapp .env

```bash
VITE_BASE_URL="http://localhost:3000"
VITE_API_URL="http://localhost:8080"
VITE_STRIPE_PUBLIC_KEY=""
VITE_CRYPTO_SECRET_KEY=

```
Step 3: Start Docker

Start Docker on your local machine and run the following command to start all services:
```bash
docker compose up -d
```

Then,Accessing the Project
Once the project is running, you can access each service via the following URLs:

- Frontend (SalesPhase1 Web App): http://localhost:8080/
- Admin Panel: http://localhost:8080/admin
- Backend API: http://localhost:8080/api



This command will:

- Build and start each service in detached mode.
- Set up the network and link all containers based on `docker-compose.yml`.

### Notes
- Verify that each service is up and running by checking the logs with:

```bash
docker compose logs -f
```

- To stop all running containers, use:

```bash
docker compose down 
```
This will stop and remove containers, networks, and any volumes created by docker compose up.

- Remove specific Images for Docker

```
docker rmi <imageid>
```

- Remove All Images

To remove all images, use:
```
docker rmi $(docker images -q)
```

also you can see video Here
[Watch the video](https://www.awesomescreenshot.com/video/33101520?key=97a35451ff88607c075bfaf4cbc0487e)